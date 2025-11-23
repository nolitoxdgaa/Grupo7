# Pruebas de Caja Negra

La técnica de prueba de **caja negra** se utilizó para evaluar los requisitos funcionales sin considerar el código fuente interno del sistema.  
Cada prueba se centró en la entrada y salida esperadas del sistema, comparando los resultados obtenidos con los previstos.

---

## Plan de pruebas

### Requisitos evaluados:
- Ensamblaje de PC en 3D paso a paso.
- Validación automática de compatibilidad entre componentes.
- Notificación de errores, advertencias y tips de seguridad.
- Generación de reporte del ensamblaje.
- Acceso a una biblioteca de componentes.
### Metodología:
Se definieron casos de prueba representativos que cubren los flujos principales y alternativos del sistema.  
Cada caso se ejecutó en Unity, registrando los resultados mediante capturas de pantalla y bitácoras de ejecución.

---

## Matriz de trazabilidad de pruebas de caja negra

| ID Prueba | Requisito Evaluado | Entrada | Resultado Esperado | Resultado Obtenido |Evidencia| Estado |
|------------|--------------------|----------|--------------------|--------------------|--------|---------|
| P01 | RF-01 Ensamblaje de PC en 3D | Cargar modelo CPU junto con Motherboard | Se muestra modelo correctamente | Se muestra correctamente || Aprobado |
| P02 | RF-02 Validación del ensamblaje | Componente se presenta en la pantalla | CPU se fija en posición correcta | CPU colocado con éxito || Aprobado |
| P03 | RF-03 Notificación de errores, advertencias y tips de seguridad. | CPU Socket LGA1700 - Mtoherboard | Mostrar alerta de incompatibilidad | Alerta visible || Aprobado |
| P04 | RF-04 Generar reporte | Presionar la tecla "P" dentro del apartado de Setup para generar un reporte | txt generado correctametne | No se encontro el archivo en la ruta|| Fail |
| P05 | RF-05 Acceder a biblioteca | Seleccionar Biblioteca en Menu | Cargar informacion general de componentes | Informacion cargada correctamente || Aprobado |

---


## Conclusiones de las pruebas

