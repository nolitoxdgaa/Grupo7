# Módulos del Prototipo

El prototipo **3D PC Builder** está estructurado en módulos que permiten una implementación ordenada y escalable.  
Cada módulo cumple una función específica dentro del flujo del sistema, y todos están integrados mediante el patrón **MVC (Modelo–Vista–Controlador)** adoptado en la fase anterior.

## 1. Módulo de Gestión de Componentes
- **Objetivo:** Controlar la carga, almacenamiento y representación 3D de los componentes de hardware.  
- **Funciones principales:**
  - Cargar modelos 3D desde la carpeta “Assets/Models”.
  - Asociar atributos técnicos (tipo, nombre, precio, socket, etc.) a cada componente.
  - Permitir la rotación, zoom y manipulación visual dentro de Unity.
- **Entradas:** Datos de componentes (archivos `.obj` o `.fbx`, precios y descripciones).  
- **Salidas:** Objetos 3D interactivos visibles en el entorno virtual.

## 2. Módulo de Ensamblaje Virtual
- **Objetivo:** Permitir al usuario armar una PC simulando el proceso real de montaje.  
- **Funciones:**
  - Validación automática de compatibilidad.
  - Indicadores visuales (colores o mensajes) que guían al usuario.
- **Interacción:** Directamente desde la cámara principal de Unity con eventos del mouse o teclado.

## 3. Módulo de Compatibilidad y Validación
- **Objetivo:** Comprobar que los componentes seleccionados funcionen entre sí.  
- **Lógica de negocio:**
  - Comparación de sockets, tipo de memoria, fuente de poder y conectores.
  - Muestra alertas visuales y sonoras ante incompatibilidades.
- **Ejemplo:** CPU con socket AM5 sólo puede conectarse con una placa base AM5.

## 4. Módulo de Cálculo de Precio
- **Objetivo:** Mostrar el costo total de la configuración en tiempo real.  
- **Funciones:**
  - Sumar los precios de los componentes seleccionados.
  - Actualizar la interfaz automáticamente al agregar o eliminar un elemento.
  - Mostrar desglose por componente y total general.

## 56. Módulo de Interfaz de Usuario (UI)
- **Objetivo:** Facilitar la navegación y comprensión de las funciones del sistema.  
- **Características:**
  - Panel lateral con categorías de componentes.
  - Ventanas emergentes (pop-ups) con detalles técnicos.
  - Botones para guardar, reiniciar y salir.
