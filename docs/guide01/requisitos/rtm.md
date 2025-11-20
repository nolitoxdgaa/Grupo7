``# Especificación de Requisitos de Software (ERS)

---

## 1. Requisitos Funcionales

Los requisitos funcionales se derivan de los objetivos del proyecto y definen las acciones que el sistema debe realizar.

### 1.1 Tabla de requisitos funcionales

| ID  | Requisito Funcional           | Descripción |
|-----|-------------------------------|-------------|
| RF1 | Ensamblaje de PC en 3D        | El sistema debe ensamblar una computadora paso a paso. |
| RF2 | Validación del ensamblaje     | El sistema debe validar si los componentes ensamblados son compatibles. |
| RF3 | Retroalimentación al usuario  | El sistema debe mostrar advertencias y mensajes de error en caso de incompatibilidades. |
| RF4 | Generar reporte               | El sistema debe permitir generar un reporte con el detalle del ensamblaje realizado por el usuario. |
| RF5 | Acceder a biblioteca          | El sistema debe permitir al usuario acceder a una biblioteca de componentes con información adicional. |

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

---

### 1.5 Interfaz de Usuario (GUI)

<img width="1032" height="577" alt="image" src="https://github.com/user-attachments/assets/ff733bd9-eafd-46ad-b5ba-c1093037c3ee" />

<img width="1034" height="575" alt="image" src="https://github.com/user-attachments/assets/085cbf12-877f-4879-9821-ea1e10f5a866" />

<img width="1031" height="575" alt="image" src="https://github.com/user-attachments/assets/cc34f8b9-0548-46b4-ad96-72c5bef83686" />




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
- Validar compatibilidad (RF2).
- Retroalimentación con errores/advertencias (RF3).

Funcionalidades como guardar/cargar ensambles o explorar componentes sin ensamblar no se desarrollarán en esta primera fase.

El alcance y las restricciones fueron definidos tomando en cuenta el tiempo disponible (3 meses), el nivel básico del equipo y la disponibilidad de recursos propios.
