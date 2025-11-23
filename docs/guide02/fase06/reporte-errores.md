# Reporte de Errores

Durante el proceso de validación se registraron defectos menores que fueron corregidos o están en seguimiento para versiones futuras.

---

## Anexo 2: Informe de errores encontrados

| ID Defecto | Descripción | Pasos para reproducir | Fecha | Detectado por | Estado | Asignado a | Prioridad |
|-------------|--------------|-----------------------|--------|----------------|----------|----------------|-------------|
| E01 | Escenas simulador 3D no presentaba el boton "volver" por ende no se podia agregar entre los menus | Ingresar a la escena simulador 3D | 07/11/2025 | Josue Cordoba | Corregido | Josue Cordoba | Media |
| E02 | Al momento de seleccionar un componente, su modelo 3D no se muestra en pantalla | Seleccionar el tipo de componente y dentro de la escena "Selector componentes", seleccionar cualquiera de estos | 12/11/2025 | Josue Cordoba | Corregido | Josue Cordoba | Alta |
| E03 | A pesar de seleccionar dos componentes incompatibles, los modelos se generaban dentro del apartado visual | Seleccionar dos componenetes incompatibles como: "Procesador con socket LGA700" y "Motherboard con socket AM4" | 15/11/2025 | Josue Cordoba | Corregido | Josue Cordoba | Alta |
|E04| No se encontró conección del script para la biblioteca de componentes | Se creo un apartado nuevo de Script solo para la bibliteca | 19/11/2025 | Wilmer Sanchez  | Corregido | Wilmer Sanchez | Media |  
|E05| Al eliminar un componente de los seleccionados cuando ya estan combinados, no se actualiza el modelo 3D | Eliminar cualquier componente seleccionado dentro de un conjunto de 2 o mas componentes| 22/11/2025 | Josue Cordoba | En proceso | Josue Cordoba | Alta |  
---

## Análisis de resultados

- **Porcentaje de defectos corregidos:** 80% (4 de 5 defectos registrados han sido resueltos satisfactoriamente).
- **Defectos pendientes:** 1 defecto pendiente, correspondiente a la generación del reporte en archivo `.txt`, actualmente en proceso de corrección.
- **Conclusión:**  El proyecto presenta una gestión de errores mayormente efectiva: se han corregido los defectos más críticos relacionados con la validación de compatibilidad y la visualización 3D, así como problemas de navegación e integración de la biblioteca de componentes. Sin embargo, aún queda por solucionar el problema de generación del reporte en `.txt`, que imp
