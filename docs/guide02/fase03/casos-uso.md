# Diagrama de Casos de Uso

El siguiente diagrama representa las interacciones principales entre el **usuario** (actor) y el sistema **3D PC Builder**.  
Los casos de uso modelan las funcionalidades esenciales del prototipo y su comportamiento esperado.

## Casos de uso principales

1. **Visualizar Componentes**  
   Permite al usuario examinar cada componente de hardware (CPU, GPU, etc.) con su información técnica.

2. **Verificar Compatibilidad**  
   El sistema analiza las relaciones entre los componentes y genera mensajes visuales cuando se detectan incompatibilidades.

3. **Calcular Precio Total**  
   Se suman los valores de cada componente y se muestra el costo final actualizado dinámicamente.

4. **Exportar Reporte (opcional)**  
   Permite exportar la lista de componentes y precios a un archivo PDF o CSV.

## Descripción de los elementos del diagrama

- **Actor principal:** Usuario  
- **Relaciones:**  
  - `include`: Calcular Precio Total incluye la selección de componentes.  
  - `extend`: Verificar Compatibilidad se extiende del proceso de ensamblaje.  
- **Reglas de negocio:**  
  - No se permite guardar configuraciones con componentes incompatibles.  
  - El sistema debe validar la existencia de un componente esencial (placa base, procesador, fuente de poder) antes de finalizar el ensamblaje.

![Imagen de WhatsApp 2025-11-02 a las 01 54 31_badb82a8](https://github.com/user-attachments/assets/6c552186-2872-4670-9908-150515ffc577)

