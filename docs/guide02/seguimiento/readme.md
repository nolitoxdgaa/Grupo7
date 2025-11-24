# Seguimiento del Proyecto
---

## Plan del proyecto y ejecución real (cierre al 24/11/2025)

De manera general, el proyecto se organizó en cuatro grandes bloques de trabajo, coherentes con la metodología **evolutiva–exploratoria** adoptada:

1. **Planificación y definición del alcance (inicio del ciclo)**  
   - **Programado:** Definir la idea del prototipo, la pregunta de investigación, el alcance del proyecto, la metodología y los requisitos iniciales.  
   - **Ejecución real:** Se cumplió según lo previsto. Se definió el uso de Unity para el simulador 3D, se formuló la pregunta de investigación y se estableció el **MVP** (validación de compatibilidad y retroalimentación al usuario como núcleo del sistema).  

2. **Diseño del prototipo y estructura del sistema (primer tramo de desarrollo)**  
   - **Programado:** Diseñar la arquitectura (MVC), la organización del repositorio, las escenas principales y los requisitos funcionales/no funcionales.  
   - **Ejecución real:** Se ejecutó con ligeros ajustes. Se adoptó el patrón MVC adaptado a Unity, se elaboró la ERS y el RTM, y se definieron las escenas básicas (selector de componentes, ensamblaje, reporte, biblioteca). Algunos detalles de la interfaz cambiaron respecto a la idea inicial, pero se mantuvo la estructura general.

3. **Implementación del MVP y funcionalidades críticas (mitad del proyecto)**  
   - **Programado:** Implementar el ensamblaje guiado, la validación de compatibilidad, los mensajes de error/advertencias y la biblioteca de componentes.  
   - **Ejecución real:** Se logró implementar el **núcleo del MVP** de acuerdo con lo planificado:
     - Ensamblaje en 3D guiado.
     - Módulo de validación de compatibilidad.
     - Mensajes de error, advertencias y tips de seguridad.
     - Consulta de biblioteca de componentes.  
     Durante esta etapa se decidió descartar ciertas interacciones 3D avanzadas con el mouse, por complejidad técnica y tiempo, ajustando así el alcance inicial.

4. **Pruebas, corrección de errores y refinamiento final (tramo final del proyecto)**  
   - **Programado:** Realizar pruebas, corregir errores, refinar la interfaz y alinear la documentación con la versión final del prototipo.  
   - **Ejecución real:**  
     - Se registraron y corrigieron varios defectos relacionados con navegación, visualización 3D, compatibilidad y generación de reportes.  
     - La mayoría de los errores se encuentran corregidos y solo queda un defecto en proceso (relacionado con la generación del archivo `.txt` del reporte), sin impedir la demostración del prototipo.  
     - Se actualizaron la **ERS**, el **RTM**, los requisitos, el apartado de metodología y la organización del equipo para que reflejen fielmente la versión actual del sistema.

---

## Evaluación comparativa entre planificación inicial y ejecución real

Al comparar la versión inicial de la planificación con la ejecución real, se pueden destacar los siguientes puntos:

- **Cumplimiento del objetivo principal:**  
  El objetivo central del proyecto —desarrollar un prototipo funcional que apoye el aprendizaje del ensamblaje y la compatibilidad de hardware mediante un entorno 3D— sí se cumplió, respetando el enfoque de MVP definido en la planificación.

- **Ajustes de alcance por viabilidad técnica y tiempo:**  
  Se realizaron ajustes razonables al alcance inicial, principalmente:
  - Se priorizó la estabilidad del ensamblaje 3D, la validación de compatibilidad y la retroalimentación al usuario.  
  - Se descartaron funcionalidades secundarias, como ciertas interacciones 3D avanzadas, para no comprometer la calidad del núcleo del sistema.  
  Estos cambios son coherentes con la metodología evolutiva–exploratoria, que permite ajustar requisitos según la experiencia obtenida en cada iteración.

- **Gestión de errores y maduración del prototipo:**  
  El registro de defectos y su corrección progresiva muestran un seguimiento activo del estado del prototipo. La mayoría de los errores críticos fueron solucionados antes del cierre, lo que permitió consolidar una versión estable para la entrega y la exposición.

- **Coherencia entre desarrollo y documentación:**  
  A lo largo del proyecto se fueron actualizando la planificación, los requisitos y la documentación técnica (ERS, RTM, patrón de software, metodología, análisis de errores), de modo que la versión final del repositorio refleja de forma fiel lo que realmente se implementó.

En síntesis, aunque hubo ajustes respecto a la planificación inicial —principalmente por restricciones de tiempo y complejidad técnica—, el seguimiento realizado permitió mantener el proyecto bajo control, cumplir con el propósito del prototipo y cerrar el trabajo con una versión consistente tanto a nivel técnico como documental.
