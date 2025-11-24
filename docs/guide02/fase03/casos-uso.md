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

4. **Guardar Reporte**  
   Permite exportar la lista de componentes y precios a un archivo Txt.

5. **Selecionar y Ensamblar Componentes**  
   Permite realizar el ensamble con los componenetes seleccionados.

5. **Visualizar Consejos de Seguridad**  
   Se irán mostrando consejos de seguridad en el programa.

## Descripción de los elementos del diagrama

- **Actor principal:** Usuario  
- **Relaciones:**  
  - `include`: Calcular Precio Total incluye la selección de componentes.  
  - `include`: Verificar Compatibilidad se extiende del proceso de ensamblaje.  
- **Reglas de negocio:**  
  - No se permite ensamblar configuraciones con componentes incompatibles.  
  - El sistema debe validar la existencia de un componente esencial (placa base, procesador, fuente de poder) antes de finalizar el ensamblaje.

<img width="1129" height="583" alt="image" src="https://github.com/user-attachments/assets/55b1c7d8-e03a-4ee2-a4d9-51afe44e0aae" />



