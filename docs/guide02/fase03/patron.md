# Patrón de Software

El diseño del sistema **3D PC Builder** se fundamenta en la arquitectura **Modelo–Vista–Controlador (MVC)**, adaptada al entorno de desarrollo **Unity 3D**.  
La elección de este patrón permite organizar el código en capas bien definidas, facilitando la mantenibilidad, escalabilidad y reutilización del software.

## Estructura general del patrón

- **Modelo (Model):**  
  Encapsula la lógica de negocio y los datos principales del sistema.  
  Contiene clases que representan los componentes de hardware (CPU, GPU, RAM, etc.) y sus relaciones de compatibilidad, además de métodos para cálculos de precios, almacenamiento de configuraciones y control de inventario.

- **Vista (View):**  
  Responsable de la presentación visual y la interacción con el usuario.  
  Se compone de las interfaces gráficas diseñadas en Unity y los modelos 3D creados en Blender, permitiendo que el usuario explore y manipule los componentes en tiempo real.

- **Controlador (Controller):**  
  Actúa como intermediario entre el modelo y la vista.  
  Gestiona los eventos de usuario (por ejemplo, clics, arrastre o selección de componentes) y actualiza tanto la vista como los datos internos según las acciones realizadas.

## Justificación del patrón

El patrón **MVC** fue seleccionado porque:
- Permite una clara separación entre la lógica del sistema y la interfaz 3D.  
- Facilita las pruebas unitarias del código en C# sin afectar la vista.  
- Promueve el trabajo colaborativo: diseñadores pueden modificar la interfaz sin alterar la lógica del programa.  
- Acelera futuras mejoras o integraciones, como una versión web o una base de datos en línea.

## Representación gráfica del patrón

*(Insertar diagrama conceptual del patrón MVC implementado en Unity, con resolución 300 dpi.)*
