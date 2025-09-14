# Especificación de Requisitos de Software (ERS)

---

## 1. Requisitos Funcionales

Los requisitos funcionales se derivan de los objetivos del proyecto y definen las acciones que el sistema debe realizar.

### 1.1 Tabla de requisitos funcionales

| ID  | Requisito Funcional             | Descripción |
|-----|---------------------------------|-------------|
| RF1 | Interacción con componentes     | El usuario podrá seleccionar, arrastrar y colocar piezas dentro del entorno 3D. |
| RF2 | Ensamblaje de PC en 3D          | El sistema debe permitir al usuario ensamblar una computadora paso a paso. |
| RF3 | Validación del ensamblaje       | El sistema debe validar si los componentes ensamblados son compatibles. |
| RF4 | Retroalimentación al usuario    | El sistema debe mostrar advertencias y mensajes de error en caso de incompatibilidades. |
| RF5 | Interfaz intuitiva              | El sistema contará con una interfaz gráfica que permita acceder al modo ensamblado y opciones básicas. |

---

### 1.2 Pseudocódigo en POO (vista general)

```pseudo
Clase Componente {
    atributos: id, nombre, tipo, compatibilidad
    método mostrarInfo()
}

Clase Ensamble {
    atributos: listaComponentes
    método agregarComponente(componente)
    método validarCompatibilidad()
    método mostrarResultado()
}

Clase Usuario {
    atributos: nombre, progreso
    método iniciarSesion()
    método seleccionarComponente()
    método ensamblar()
}
```
###1.3 Ejemplos de funciones clave en pseudocódigo

Validación de error al agregar un componente incompatible
```pseudo
método agregarComponente(componente):
    si validarCompatibilidad(componente) == falso:
        mostrarError("El componente no es compatible con el ensamble actual.")
    sino:
        listaComponentes.agregar(componente)
```

Tip de seguridad (ejemplo fuente de poder insuficiente)
```pseudo
método validarCompatibilidad():
    si consumoTotal > capacidadFuente:
        mostrarAdvertencia("La fuente de poder seleccionada no cubre el consumo.")
        retornar falso
    retornar verdadero
```

Retroalimentación visual (ejemplo en GUI)
```pseudo
método mostrarError(mensaje):
    GUI.mostrarPopup(colorRojo, mensaje)
```

---

### 1.4 Ejemplos de fórmulas matemáticas utilizadas

* **Consumo energético total del ensamble**

    $$ConsumoTotal = \sum_{i=1}^{n} TDP_{componente_{i}}$$

* **Compatibilidad de memoria RAM y placa base**

    $$Compatibilidad = (TipoRAM_{seleccionada} == TipoRAM_{placaBase})$$

* **Relación de potencia de fuente**

    $$CapacidadFuente \ge ConsumoTotal \times 1.2$$

Claro, aquí tienes el texto que proporcionaste en formato Markdown, ideal para su uso en GitHub.

---

### 1.5 Interfaz de Usuario (GUI)

La propuesta inicial de la interfaz gráfica (GUI) se incluirá en el Anexo A.

Se recomienda utilizar herramientas de wireframing gratuitas como Figma o Balsamiq.

**Pantallas previstas:**

- **Menú principal:** botones `Explorar componentes` y `Armar PC`.
- **Pantalla de ensamblaje:** zona 3D a la izquierda, catálogo de componentes a la derecha, mensajes en la parte inferior.
- **Pantalla de validaciones/advertencias.**

---

### 2. Requisitos No Funcionales

Los requisitos no funcionales definen criterios de calidad, limitaciones técnicas y condiciones de uso.

| Categoría | Especificación |
| :--- | :--- |
| **Portabilidad** | El sistema debe ejecutarse en laptops con Windows 10 o superior, con GPU dedicada (RTX 3060 o similar). |
| **Mantenibilidad** | El código será modular en C# (Unity) y Python, con control de versiones en GitHub y documentación en README. |
| **Usabilidad** | La interfaz debe ser intuitiva y accesible para usuarios principiantes, con mensajes de error claros. |
| **Velocidad de procesamiento** | La aplicación debe mantener una tasa mínima de 30 FPS en simulación 3D para asegurar una experiencia fluida. |
| **Restricciones técnicas** | El desarrollo estará limitado a herramientas de libre acceso: Unity (C#), Blender, Python. Sistema operativo Windows 10+. No habrá integración con sistemas externos en el MVP. |

---

### 3. Observaciones Generales

El MVP se enfocará únicamente en:
- Ensamblar PC en 3D (RF2).
- Validar compatibilidad (RF3).
- Retroalimentación con errores/advertencias (RF4).

Funcionalidades como guardar/cargar ensambles o explorar componentes sin ensamblar no se desarrollarán en esta primera fase.

El alcance y las restricciones fueron definidos tomando en cuenta el tiempo disponible (3 meses), el nivel básico del equipo y la disponibilidad de recursos propios.
