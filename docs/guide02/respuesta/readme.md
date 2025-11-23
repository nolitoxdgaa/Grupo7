# Respuesta a la pregunta de investigación

Se responde de manera abierta a la pregunta de investigación formulada en la sección de lineamientos generales del proyecto:

> ¿Las herramientas 3D interactivas pueden mejorar el aprendizaje práctico de los estudiantes de ingeniería en el proceso de ensamblaje de computadoras?

En términos generales, **sí**: el desarrollo e implementación del prototipo **“3D PC Builder”**, basado en Unity y modelos 3D, muestran que el uso de entornos tridimensionales interactivos **favorece la comprensión del ensamblaje y la compatibilidad de hardware** en un contexto educativo.

---

## Fundamentación de la respuesta

La conclusión anterior se sustenta en varios aspectos observados durante el desarrollo del prototipo:

- **Visualización clara de los componentes y su ubicación**  
  El entorno 3D permite que el estudiante vea cada pieza (CPU, GPU, RAM, placa base, fuente de poder, etc.) en un gabinete virtual, entendiendo mejor **cómo se relacionan física y funcionalmente**.

- **Refuerzo del concepto de compatibilidad**  
  El sistema integra un módulo de **validación de compatibilidad** y notificación de errores, que señala cuando una combinación de componentes es incorrecta (por ejemplo, sockets incompatibles o fuente insuficiente). Esto transforma el error en una **oportunidad directa de aprendizaje**.

- **Aprendizaje sin riesgo ni costo de material**  
  El prototipo permite **experimentar libremente** con diferentes configuraciones sin dañar componentes reales ni incurrir en gastos, lo que favorece la práctica y el ensayo–error de forma segura.

- **Integración de teoría y práctica en un mismo entorno**  
  Los estudiantes no solo “leen” sobre ensamblaje; también **simulan el proceso paso a paso**, observando los efectos de sus decisiones dentro del simulador.

---

## Relación con el prototipo 3D PC Builder

En el caso específico del proyecto **3D PC Builder**, se implementaron funcionalidades clave que apoyan el aprendizaje:

- **Ensamblaje guiado en 3D**  
  Permite comprender la secuencia lógica del montaje de una PC.

- **Validación automática de compatibilidad**  
  Refuerza conceptos técnicos (sockets, TDP, interfaces de almacenamiento, etc.) al marcar combinaciones inadecuadas.

- **Mensajes de error, advertencias y tips de seguridad**  
  Añaden una capa pedagógica al indicar **por qué** una configuración es problemática y cómo corregirla.

- **Biblioteca de componentes**  
  Facilita el acceso a información técnica básica, integrando teoría con la práctica de selección de hardware.

Aunque el prototipo se desarrolló en un contexto de tiempo limitado y con alcance de **MVP**, las pruebas internas y el uso del sistema durante su construcción evidencian que los estudiantes logran **una comprensión más tangible y estructurada** del armado de PCs que con materiales puramente teóricos.

---

# Mejora del proyecto en base a MVC y a la metodología evolutiva–exploratoria

A partir de la arquitectura aplicada (**MVC** en Unity) y de la **metodología evolutiva–exploratoria** utilizada durante el desarrollo del prototipo, se identifican varias oportunidades de mejora que pueden orientar futuras versiones del sistema **3D PC Builder**.

---

## Posibles mejoras en base al patrón MVC

1. **Separar aún más la lógica del Controlador y la Vista**  
   Aunque el proyecto aplica MVC, en Unity es común que parte de la lógica termine mezclada en los scripts de la interfaz (botones, eventos de UI). Como mejora futura se podría:
   - Centralizar la lógica principal de ensamblaje, validación y reporte en **clases Controlador** específicas.
   - Dejar en la Vista únicamente:
     - Referencias a botones, textos y modelos 3D.
     - Llamadas simples a métodos del Controlador.

2. **Definir modelos de dominio más explícitos**  
   Actualmente ya se usan conceptos como CPU, GPU, RAM, placa base, etc. Se puede reforzar el Modelo:
   - Creando clases bien definidas para cada tipo de componente (por ejemplo, `CPU`, `Motherboard`, `GPU`, etc.) con sus atributos clave.
   - Encapsulando en el Modelo la lógica de compatibilidad (sockets, TDP, interfaces), para no duplicarla en varios scripts.

3. **Controladores especializados por módulo**  
   Para mantener la arquitectura escalable, se puede:
   - Tener un **controlador para el ensamblaje**, otro para la **biblioteca de componentes** y otro para la **generación de reporte**.
   - Evitar que un solo script “haga todo” (God Controller), mejorando así la mantenibilidad y las pruebas.

4. **Mayor preparación para futuras vistas**  
   Si más adelante se quiere una versión web o una interfaz distinta:
   - Mantener el Modelo y parte del Controlador independientes de Unity.
   - Diseñar la lógica de negocio de forma que pueda reutilizarse sin depender de la escena 3D.

---

## Posibles mejoras en base a la metodología evolutiva–exploratoria

1. **Formalizar mejor las iteraciones**  
   En la práctica se trabajó por versiones (interfaz, ensamblaje, validación, reporte), pero puede mejorarse:
   - Definiendo explícitamente cada **iteración** (Iteración 1: interfaz base, Iteración 2: ensamblaje + compatibilidad, etc.).
   - Asociando a cada iteración:
     - Objetivos claros.
     - Requisitos del RTM que se cubren.
     - Errores detectados y corregidos.

2. **Registrar ciclos “Construir–Probar–Ajustar” de forma más sistemática**  
   Como la metodología es exploratoria, tiene sentido:
   - Documentar brevemente, por iteración:
     - Qué se construyó.
     - Qué se probó (escenas, casos de compatibilidad, reporte).
     - Qué se decidió ajustar o descartar (por ejemplo, la interacción 3D avanzada con el mouse).

3. **Ampliar las pruebas más allá del equipo**  
   Hasta ahora, las pruebas son principalmente internas. Como mejora futura:
   - Realizar pequeñas sesiones de prueba con otros estudiantes (usuarios finales).
   - Registrar comentarios sobre:
     - Claridad de la interfaz.
     - Comprensión de los mensajes de error y tips.
     - Facilidad para completar el ensamblaje.

4. **Conectar aún más el RTM con las decisiones de diseño**  
   El RTM ya está bien planteado, pero se puede reforzar:
   - Indicando, por cada requisito funcional importante, **en qué iteración** se implementó y **qué errores** se relacionaron con él.
   - Esto ayuda a mostrar cómo la metodología evolutiva–exploratoria realmente guió el desarrollo.

5. **Planificar mejoras futuras con base en lo aprendido**  
   A partir de las limitaciones actuales (por ejemplo, no implementar aún ciertas interacciones 3D avanzadas o algunas mejoras de UX):
   - Definir una pequeña **hoja de ruta** con:
     - Funciones que quedaron fuera del MVP.
     - Mejoras de arquitectura (más modularidad, más pruebas).
     - Posible integración con bases de datos o precios reales en el futuro.


## Conclusión

En síntesis, la experiencia con el prototipo **3D PC Builder** muestra que **el uso de herramientas 3D interactivas sí contribuye positivamente al aprendizaje práctico del ensamblaje de computadoras**.  

Estas tecnologías:

- Facilitan la comprensión de la estructura interna del equipo.
- Refuerzan conceptos de compatibilidad y buenas prácticas.
- Permiten aprender mediante la exploración y el error sin riesgo físico ni económico.

Por tanto, se concluye que **las herramientas 3D interactivas responden favorablemente a la hipótesis planteada** y constituyen un recurso didáctico válido que puede ampliarse a otros contenidos técnicos dentro de la formación en ingeniería.
