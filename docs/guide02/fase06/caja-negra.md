# Pruebas de Caja Negra

La técnica de prueba de **caja negra** se utilizó para evaluar los requisitos funcionales sin considerar el código fuente interno del sistema.  
Cada prueba se centró en la entrada y salida esperadas del sistema, comparando los resultados obtenidos con los previstos.

---

## Plan de pruebas

### Requisitos evaluados:
- Visualización 3D de componentes.  
- Ensamblaje interactivo.  
- Validación de compatibilidad.  
- Cálculo de precios.  
- Guardado de configuraciones.

### Metodología:
Se definieron casos de prueba representativos que cubren los flujos principales y alternativos del sistema.  
Cada caso se ejecutó en Unity, registrando los resultados mediante capturas de pantalla y bitácoras de ejecución.

---

## Matriz de trazabilidad de pruebas de caja negra

| ID Prueba | Requisito Evaluado | Entrada | Resultado Esperado | Resultado Obtenido | Estado |
|------------|--------------------|----------|--------------------|--------------------|---------|
| P01 | RF-01 Visualización 3D | Cargar modelo GPU | Se muestra modelo correctamente | Se muestra correctamente | Aprobado |
| P02 | RF-02 Ensamblaje | Arrastrar CPU al gabinete | CPU se fija en posición correcta | CPU colocado con éxito | Aprobado |
| P03 | RF-03 Compatibilidad | CPU AM5 + Placa AM4 | Mostrar alerta de incompatibilidad | Alerta visible | Aprobado |
| P04 | RF-04 Precio Total | Agregar 3 componentes | Precio total actualizado | Valor correcto mostrado | Aprobado |
| P05 | RF-05 Guardar Configuración | Presionar botón Guardar | Archivo JSON creado | Archivo generado correctamente | Aprobado |

---

## Evidencias

Las capturas de las pruebas (en formato .png o .jpg, resolución 300 dpi) muestran el correcto funcionamiento del sistema en los casos exitosos y las observaciones en las iteraciones iniciales.

---

## Conclusiones de las pruebas

El sistema **3D PC Builder** cumple con los requisitos funcionales mandatorios establecidos.  
Las pruebas demostraron estabilidad en el renderizado 3D, validación lógica de compatibilidad y persistencia de datos en configuraciones guardadas.
