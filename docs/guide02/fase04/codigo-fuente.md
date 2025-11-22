# Código Fuente del Prototipo

A continuación se muestran fragmentos del código más relevante del sistema **3D PC Builder**, desarrollado en **C#** dentro del entorno **Unity**.  
El código sigue principios de orientación a objetos y estructura modular, priorizando la mantenibilidad y claridad.

---
## GameManager: columna vertebral del sistema
```csharp
using System.Collections.Generic;
using UnityEngine;

public class GameManager : MonoBehaviour
{
    public static GameManager Instancia { get; private set; }

    [HideInInspector]
    public GestorComponentes gestor;

    private Dictionary<string, ComponenteBase> buildActual = new Dictionary<string, ComponenteBase>();

    private void Awake()
    {
        if (Instancia != null && Instancia != this)
        {
            Destroy(gameObject);
            return;
        }

        Instancia = this;
        DontDestroyOnLoad(gameObject);

        gestor = FindFirstObjectByType<GestorComponentes>();
        if (gestor == null)
        {
            Debug.LogError("GameManager: No se encontró GestorComponentes en la escena.");
        }
    }

    private void Start()
    {
        if (gestor == null || gestor.componentes == null || gestor.componentes.Count == 0)
            Debug.LogWarning("GestorComponentes vacío. ¿Los JSON están dentro de Resources/Componentes?");
        else
            Debug.Log($"Componentes disponibles: {gestor.componentes.Count}");
    }

    // ============================================================
    // LISTA POR TIPO
    // ============================================================
    public List<ComponenteBase> ObtenerListaPorTipo(string tipo)
    {
        var lista = new List<ComponenteBase>();

        foreach (var comp in gestor.componentes.Values)
        {
            if (!string.IsNullOrEmpty(comp.tipo) &&
                comp.tipo.ToLower() == tipo.ToLower())
            {
                lista.Add(comp);
            }
        }

        return lista;
    }

    // ============================================================
    // SELECCIONAR COMPONENTE
    // ============================================================
    public bool SeleccionarComponente(string tipo, string nombreComponente)
    {
        var componente = gestor.ObtenerComponente(nombreComponente);

        if (componente == null)
        {
            Debug.LogWarning($"No existe el componente '{nombreComponente}'");
            return false;
        }

        buildActual[tipo] = componente;

        PlayerPrefs.SetString("UltimoTipoAgregado", tipo);
        PlayerPrefs.SetString("UltimoNombreAgregado", componente.nombre);

        string resultado = ValidadorCompatibilidad.Verificar(buildActual);

        bool tieneErrores =
            resultado.Contains("no es compatible") ||
            resultado.Contains("no compatible") ||
            resultado.Contains("insuficiente") ||
            resultado.Contains("excede") ||
            resultado.Contains("no cubre");

        return !tieneErrores;
    }


    // ============================================================
    // INFORMACIÓN DEL SISTEMA
    // ============================================================
    public float ObtenerPrecioTotal()
    {
        float total = 0f;

        foreach (var c in buildActual.Values)
            total += c.precio;

        return total;
    }

    public string VerificarCompatibilidadTexto()
    {
        return ValidadorCompatibilidad.Verificar(buildActual);
    }

    public ComponenteBase ObtenerSeleccionado(string tipo)
    {
        if (buildActual.ContainsKey(tipo))
            return buildActual[tipo];

        return null;
    }

    public void QuitarComponente(string tipo)
    {
        if (buildActual.ContainsKey(tipo))
        {
            buildActual.Remove(tipo);
            Debug.Log($"{tipo} quitado del build.");
        }
    }

    public Dictionary<string, ComponenteBase> ObtenerBuildActual()
    {
        return buildActual;
    }
}
```
---
## GestorComponentes: cargado de todos los componentes a traves de JSON
```csharp
using System.Collections.Generic;
using UnityEngine;

public class GestorComponentes : MonoBehaviour
{
    public static GestorComponentes Instancia { get; private set; }

    // Diccionario general con todos los componentes (CPU, GPU, etc.)
    public Dictionary<string, ComponenteBase> componentes = new Dictionary<string, ComponenteBase>();

    private void Awake()
    {
        // Asegura que solo haya una instancia
        if (Instancia != null && Instancia != this)
        {
            Destroy(gameObject);
            return;
        }

        Instancia = this;
        DontDestroyOnLoad(gameObject);

        CargarComponentes();
    }

    /// 
    /// Carga todos los componentes desde la carpeta Resources/Componentes.
    /// 
    private void CargarComponentes()
    {
        TextAsset[] archivos = Resources.LoadAll<TextAsset>("Componentes");
        Debug.Log($" Cargando {archivos.Length} archivos JSON de componentes...");

        foreach (TextAsset archivo in archivos)
        {
            try
            {
                string nombreArchivo = archivo.name.ToLower();
                List<ComponenteBase> lista = new List<ComponenteBase>();

                // Detección automática por tipo de archivo
                if (nombreArchivo.Contains("cpu"))
                {
                    var data = JsonUtility.FromJson<ComponenteLista<CPU>>(archivo.text);
                    lista.AddRange(data.Items);
                }
                else if (nombreArchivo.Contains("gpu"))
                {
                    var data = JsonUtility.FromJson<ComponenteLista<GPU>>(archivo.text);
                    lista.AddRange(data.Items);
                }
                else if (nombreArchivo.Contains("ram"))
                {
                    var data = JsonUtility.FromJson<ComponenteLista<RAM>>(archivo.text);
                    lista.AddRange(data.Items);
                }
                else if (nombreArchivo.Contains("ssd"))
                {
                    var data = JsonUtility.FromJson<ComponenteLista<SSD>>(archivo.text);
                    lista.AddRange(data.Items);
                }
                else if (nombreArchivo.Contains("psu"))
                {
                    var data = JsonUtility.FromJson<ComponenteLista<PSU>>(archivo.text);
                    lista.AddRange(data.Items);
                }
                else if (nombreArchivo.Contains("motherboard"))
                {
                    var data = JsonUtility.FromJson<ComponenteLista<Motherboard>>(archivo.text);
                    lista.AddRange(data.Items);
                }
                else if (nombreArchivo.Contains("case"))
                {
                    var data = JsonUtility.FromJson<ComponenteLista<Case>>(archivo.text);
                    lista.AddRange(data.Items);
                }
                else
                {
                    Debug.LogWarning($" Archivo desconocido o tipo no reconocido: {archivo.name}");
                    continue;
                }

                // Registrar cada componente en el diccionario
                foreach (var componente in lista)
                {
                    if (componente == null)
                    {
                        Debug.LogError($" Un componente en {archivo.name} vino nulo.");
                        continue;
                    }

                    if (string.IsNullOrEmpty(componente.nombre))
                    {
                        Debug.LogError($" El componente del archivo {archivo.name} no tiene campo 'nombre' definido.");
                        continue;
                    }

                    if (!componentes.ContainsKey(componente.nombre))
                    {
                        componentes.Add(componente.nombre, componente);
                        Debug.Log($" Cargado: {componente.nombre}");
                    }
                    else
                    {
                        Debug.LogWarning($" Duplicado ignorado: {componente.nombre}");
                    }
                }
            }
            catch (System.Exception ex)
            {
                Debug.LogError($" Error al cargar {archivo.name}: {ex.Message}");
            }
        }

        Debug.Log($" Total componentes cargados: {componentes.Count}");
    }

    // Obtiene un componente por su nombre.
    public ComponenteBase ObtenerComponente(string nombre)
    {
        if (componentes.ContainsKey(nombre))
            return componentes[nombre];
        else
        {
            Debug.LogWarning($" No se encontró el componente: {nombre}");
            return null;
        }
    }
}

```
---
## ValidadorComptabilidad: Encargado de verificar si los componentes son compatibles entre si.
```csharp
using System.Collections.Generic;
using System.Text;


public static class ValidadorCompatibilidad
{
    public static string Verificar(Dictionary<string, ComponenteBase> build)
    {
        StringBuilder resultado = new StringBuilder();
        resultado.AppendLine(" Verificando compatibilidad de componentes...\n");

        // Recuperar componentes del diccionario
        build.TryGetValue("CPU", out ComponenteBase cpuBase);
        build.TryGetValue("Motherboard", out ComponenteBase mbBase);
        build.TryGetValue("RAM", out ComponenteBase ramBase);
        build.TryGetValue("GPU", out ComponenteBase gpuBase);
        build.TryGetValue("PSU", out ComponenteBase psuBase);
        build.TryGetValue("Case", out ComponenteBase caseBase);

        bool todoOK = true;

        // --- CPU ↔ Motherboard ---
        if (cpuBase is CPU cpu && mbBase is Motherboard mb)
        {
            if (cpu.socketCompatible != mb.socketCompatible)
            {
                resultado.AppendLine($" CPU ({cpu.socketCompatible}) no es compatible con la Motherboard ({mb.socketCompatible}).");
                todoOK = false;
            }
            else
                resultado.AppendLine($" CPU y Motherboard compatibles (Socket {cpu.socketCompatible}).");
        }

        // --- RAM ↔ Motherboard ---
        if (ramBase is RAM ram && mbBase is Motherboard mb2)
        {
            if (!string.Equals(ram.tipoMemoria, mb2.tipoMemoria, System.StringComparison.OrdinalIgnoreCase))
            {
                resultado.AppendLine($" RAM ({ram.tipoMemoria}) no compatible con Motherboard ({mb2.tipoMemoria}).");
                todoOK = false;
            }
            else
                resultado.AppendLine($" RAM y Motherboard compatibles ({ram.tipoMemoria}).");
        }

        // --- GPU ↔ PSU ---
        if (gpuBase is GPU gpu && psuBase is PSU psu)
        {
            if (gpu.consumoEnergia > psu.potencia)
            {
                resultado.AppendLine(
                    $" PSU insuficiente ({psu.potencia}W < {gpu.consumoEnergia}W requeridos por GPU)."
                );
                todoOK = false;
            }
            else
                resultado.AppendLine(
                    $" PSU tiene suficiente potencia para la GPU ({psu.potencia}W)."
                );
        }


        // --- PSU ↔ Consumo total del sistema ---
        if (psuBase is PSU psu2)
        {
            float consumoTotal = 0f;

            if (cpuBase is CPU c) consumoTotal += c.consumoEnergia;
            if (gpuBase is GPU g) consumoTotal += g.consumoEnergia;
            if (ramBase is RAM r) consumoTotal += r.consumoEnergia;
            if (mbBase is Motherboard m) consumoTotal += m.consumoEnergia;

            if (consumoTotal > psu2.potencia)
            {
                resultado.AppendLine(
                    $" PSU no cubre el consumo total ({consumoTotal}W > {psu2.potencia}W)."
                );
                todoOK = false;
            }
            else
                resultado.AppendLine(
                    $" PSU cubre el consumo total del sistema ({consumoTotal}W de {psu2.potencia}W disponibles)."
                );
        }


        // --- Case ↔ Motherboard ---
        if (caseBase is Case caja && mbBase is Motherboard mb3)
        {
            if (!caja.factorFormaCompatible.ToLower().Contains(mb3.factorForma.ToLower()))
            {
                resultado.AppendLine($" Case ({caja.factorFormaCompatible}) no soporta la Motherboard ({mb3.factorForma}).");
                todoOK = false;
            }
            else
                resultado.AppendLine($" Case y Motherboard compatibles ({mb3.factorForma}).");
        }

        // --- RAM ↔ Capacidad de la Motherboard ---
        if (ramBase is RAM ram2 && mbBase is Motherboard mb4)
        {
            if (ram2.capacidadGB > mb4.maxRAM)
            {
                resultado.AppendLine($" La RAM ({ram2.capacidadGB}GB) excede la capacidad máxima de la Motherboard ({mb4.maxRAM}GB).");
                todoOK = false;
            }
        }

        // Resultado final
        if (build.Count == 0)
            return " No hay componentes seleccionados.";

        if (todoOK)
            resultado.AppendLine("\n Todos los componentes son compatibles.");
        else
            resultado.AppendLine("\n Se detectaron incompatibilidades en la configuración.");

        return resultado.ToString();
    }
}

```
