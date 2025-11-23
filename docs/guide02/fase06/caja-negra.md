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
| P01 | RF-01 Ensamblaje de PC en 3D | Cargar modelo CPU junto con Motherboard | Se muestra modelo correctamente | Se muestra correctamente |Anexo 1| Aprobado |
| P02 | RF-02 Validación del ensamblaje | Varios componentes seleccionados | Varios componentes compatibles ensamblados  | Componentes ensamblados con exito |Anexo 2| Aprobado |
| P03 | RF-03 Notificación de errores, advertencias y tips de seguridad. | CPU Socket LGA1700 - Mtoherboard socket LG1150 | Mostrar alerta de incompatibilidad | Alerta visible |Anexo3| Aprobado |
| P04 | RF-03 Notificación de errores, advertencias y tips de seguridad. | Ingresar al Simulador de ensamblaje | Mostrar tips de seguridad aleatorios | Tips de seguridad visibles |Anexo4| Aprobado |
| P05| RF-04 Generar reporte | Presionar la tecla "P" dentro del apartado de Setup para generar un reporte | txt generado correctametne | Archivo encontrao en ruta|anexo 5| Aprobado |
| P06 | RF-05 Acceder a biblioteca | Seleccionar Biblioteca en Menu | Cargar informacion general de componentes | Informacion cargada correctamente |Anexo6| Aprobado |

---


## Conclusiones de las pruebas

---

## Anexos:
    Anexo1.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8cf10e9c-901c-4237-8264-c0ac1b06de5c" />

    Anexo2.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8fcba22b-559b-4f06-b632-b130c5a957ae" />

    Anexo3.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9bbac092-9cfb-4b1c-a415-eb64c7faa794" />

    Anexo4.
<img width="1102" height="421" alt="image" src="https://github.com/user-attachments/assets/63c1c924-8a10-47e3-b183-614cd9838533" />

    Anexo5.
<img width="1280" height="719" alt="image" src="https://github.com/user-attachments/assets/b21c5ff6-21b8-4a1f-8636-f893dcb8ce58" />

    Anexo6.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/82389d1c-1ecf-4403-ad29-597003e693a6" />

