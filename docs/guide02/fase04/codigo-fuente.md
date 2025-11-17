# Código Fuente del Prototipo

A continuación se muestran fragmentos del código más relevante del sistema **3D PC Builder**, desarrollado en **C#** dentro del entorno **Unity**.  
El código sigue principios de orientación a objetos y estructura modular, priorizando la mantenibilidad y claridad.

---
Eliminar ejemplo y colocar código de la carpeta scripts del otro repositorio

## Ejemplo 1: Carga dinámica de componentes
```csharp
using UnityEngine;
using System.Collections.Generic;

public class ComponentLoader : MonoBehaviour {
    public List<GameObject> components;
    public Transform spawnPoint;

    void Start() {
        foreach (GameObject comp in components) {
            Instantiate(comp, spawnPoint.position, Quaternion.identity);
        }
    }
}
