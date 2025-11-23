# Metodología

El desarrollo del prototipo 3D PC Builder se llevó a cabo utilizando una metodología evolutiva–exploratoria, enfocada en construir el sistema a partir de versiones tempranas y sencillas, que luego fueron probadas, analizadas y mejoradas de manera iterativa.  

Este enfoque fue seleccionado porque se adapta bien a un proyecto educativo donde:
- El equipo aprende progresivamente herramientas como Unity y el manejo de modelos 3D.
- Los requisitos se van ajustando en función de lo que es técnicamente viable y del tiempo disponible.
- Se prioriza un MVP funcional (validación de compatibilidad y retroalimentación al usuario) antes de intentar funcionalidades más avanzadas.

---

## Enfoque evolutivo–exploratorio aplicado

En el contexto del proyecto 3D PC Builder, la metodología evolutiva–exploratoria se aplicó mediante las siguientes etapas:

1. **Exploración inicial y definición del MVP**  
   - Revisión de las ideas iniciales del proyecto y de las capacidades de Unity para el manejo de modelos 3D.  
   - Identificación de las funcionalidades mínimas críticas para el prototipo:
     - Ensamblaje guiado de una PC en 3D.
     - Validación de compatibilidad entre componentes.
     - Mensajes de error, advertencias y tips de seguridad.
     - Generación de un reporte básico del ensamblaje.
     - Consulta de una biblioteca de componentes.  
   - Definición del MVP (Producto Mínimo Viable), priorizando la validación de compatibilidad y la retroalimentación al usuario, dejando fuera funciones más complejas o no viables en el tiempo disponible.

2. **Diseño y construcción de prototipos evolutivos**  
   - Elaboración de una primera versión del prototipo centrada en la interfaz base y la estructura general del proyecto en Unity.  
   - Desarrollo incremental de funcionalidades:
     - Versión inicial del flujo de ensamblaje de componentes en 3D (sin interacción avanzada).  
     - Implementación del módulo de validación de compatibilidad entre componentes.  
     - Incorporación de mensajes de error y advertencias para guiar al usuario.  
     - Generación de un reporte sencillo con el listado de componentes y el resultado de la validación.  
   - Cada versión se construyó sobre la anterior, ajustando o sustituyendo elementos que no funcionaban adecuadamente.

3. **Evaluación exploratoria y retroalimentación**  
   - Pruebas internas realizadas por los integrantes del equipo para:
     - Verificar el comportamiento del ensamblaje guiado.  
     - Comprobar que la validación de compatibilidad responde según los requisitos definidos.  
     - Evaluar la claridad de los mensajes de error, advertencias y tips de seguridad.  
   - Revisión periódica del avance frente al RTM (matriz de trazabilidad de requisitos) y a las expectativas del curso.  
   - Ajustes sobre la interfaz y sobre la lógica de compatibilidad según los resultados observados en las pruebas.

4. **Refinamiento y consolidación del prototipo**  
   - Corrección de errores detectados durante las pruebas exploratorias.  
   - Optimización de la experiencia de usuario en las pantallas principales:
     - Ensamblaje 3D guiado.  
     - Visualización de compatibilidades/incompatibilidades.  
     - Biblioteca de componentes y reporte.  
   - Revisión y alineación de la documentación (ERS, RTM, organización, requisitos) con la versión final del prototipo desarrollado.

---

## Ciclo de trabajo y seguimiento

La metodología evolutiva–exploratoria se apoyó en ciclos cortos de trabajo donde se repetían las siguientes actividades:

- **Planificación de iteraciones:**  
  - Definir qué funcionalidad o mejora se abordaría en cada ciclo (por ejemplo, primero ensamblaje básico, luego validación, luego mensajes de feedback, etc.).  

- **Implementación y prueba inmediata:**  
  - Desarrollar los cambios en el proyecto Unity.  
  - Probar de forma temprana la funcionalidad agregada antes de avanzar a la siguiente.  

- **Revisión conjunta del equipo:**  
  - Evaluar si lo implementado cumplía con los requisitos mínimos.  
  - Ajustar o simplificar funcionalidades cuando la complejidad o el tiempo lo exigían.  

- **Actualización de documentación:**  
  - Registrar los cambios relevantes en la ERS y el RTM, manteniendo la trazabilidad entre requisitos y funcionalidades implementadas.

Este ciclo permitió mantener un seguimiento continuo del estado del prototipo y tomar decisiones informadas sobre qué mejorar, qué mantener y qué descartar según la viabilidad técnica y el tiempo disponible.

---

## Beneficios obtenidos

La aplicación de una metodología evolutiva–exploratoria permitió:

- **Adaptar el proyecto a las capacidades reales del equipo**, ajustando requisitos cuando ciertas funcionalidades (como interacciones 3D avanzadas) resultaban poco viables.  
- **Concentrar esfuerzos en un MVP funcional**, asegurando que las características centrales (ensamblaje guiado, validación de compatibilidad, feedback al usuario y reporte) estuvieran operativas.  
- **Aprender progresivamente** el uso de herramientas como Unity y el manejo de modelos 3D, incorporando mejoras a medida que se comprendían mejor sus posibilidades y limitaciones.  
- **Reducir el riesgo de fracaso técnico**, al probar continuamente versiones parciales del prototipo y corregir problemas antes de avanzar a etapas más complejas. 
- **Mantener una visión clara de avance**, gracias a las iteraciones y a la revisión constante respecto a los requisitos definidos en el RTM.

---

## Referencias bibliográficas

- Fernández, E. S., & Alfaro, D. P. (2020). *El modelo iterativo e incremental para el desarrollo de la aplicación de realidad aumentada Amón_RA.* Tecnología en marcha, 33(8), 165-177.  
- Lemus, C. R., et al. (2022). *Aplicación de modelos iterativos para desarrollo de prototipos web durante la pandemia de COVID-19.* Pistas Educativas, 43(141).
