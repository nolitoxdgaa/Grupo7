# Formato de las Interfaces de Usuario (Mockups)

Las siguientes interfaces fueron diseñadas como **mockups de referencia** para la etapa de desarrollo del sistema **3D PC Builder**.  
Fueron elaboradas en **Figma** y adaptadas posteriormente en Unity durante la implementación del entorno 3D.

##  Interfaz 1 — Menú Principal

### Descripción
La interfaz inicial del sistema ofrece un menú de navegación sencillo y organizado.  
Aquí el usuario puede elegir entre distintas opciones que lo dirigirán a las secciones principales de la aplicación:
- **Componentes:** para acceder al listado de piezas del computador y revisar sus características.  
- **Armado:** para ingresar al entorno donde se realiza la simulación del ensamble.  
- **Salir:** para cerrar la aplicación.

El diseño se mantiene limpio y estructurado, con botones grandes y etiquetas claras que facilitan su uso incluso para usuarios sin experiencia previa en simuladores 3D.

### Objetivo
Proporcionar un punto de entrada visualmente atractivo y funcional, que permita al usuario orientarse rápidamente dentro del sistema.  
Esta interfaz marca el inicio del flujo lógico de interacción: **Inicio → Exploración → Ensamblaje.**

---

##  Interfaz 2 — Información de Componentes

### Descripción
En esta sección, el usuario puede explorar en detalle cada componente del hardware que conforma una PC.  
La interfaz presenta un diseño dividido por categorías (CPU, GPU, Placa Madre, RAM, Fuente de Poder, entre otros), donde cada elemento incluye:
- Una breve **descripción funcional** que explica para qué sirve el componente.  
- Datos **técnicos relevantes**, como compatibilidad de socket, potencia, frecuencia o consumo.  
- Imágenes o íconos representativos que facilitan la identificación visual.

### Objetivo
Esta interfaz busca **informar y educar** al usuario sobre los distintos elementos que intervienen en el armado de una computadora.  
Antes de proceder con la simulación del ensamble, el usuario puede comprender cómo interactúan los componentes entre sí y tomar decisiones correctas sobre compatibilidad.

Además, esta sección fortalece el enfoque pedagógico del proyecto, aportando un valor didáctico más allá de la simulación visual.

---

##  Interfaz 3 — Armado de la PC

### Descripción
Esta es la vista principal y más interactiva del sistema.  
En ella, el usuario puede **simular el proceso real de ensamblaje de una PC** en un entorno tridimensional.  
El espacio de trabajo incluye:
- Un **modelo 3D del gabinete** y los componentes internos.
- Opciones para **agregar o quitar piezas**, verificando su compatibilidad.  
- Indicadores visuales y mensajes de advertencia en caso de incompatibilidad entre componentes.
- Información resumida de cada componente seleccionado.
- Visualización en tiempo real del **precio total** o estado del armado completo.

El diseño está enfocado en brindar una experiencia práctica e inmersiva, fomentando la comprensión visual del proceso de ensamblaje y reforzando el aprendizaje sobre la estructura interna del hardware.

### Objetivo
Ofrecer al usuario una experiencia interactiva que combine **aprendizaje y simulación realista**.  
La interfaz busca representar de manera clara cómo se integran los distintos componentes en una PC funcional, resaltando la importancia de la compatibilidad y el orden en el montaje.

---

##  Flujo de Uso del Sistema

El recorrido del usuario dentro de **3D PC Builder** sigue una secuencia lógica e intuitiva:
1. **Inicio (Menú Principal):** el usuario selecciona la acción que desea realizar.  
2. **Consulta (Información de Componentes):** aprende sobre las partes que integran un computador.  
3. **Simulación (Armado de PC):** ensambla visualmente su equipo y verifica compatibilidades.

Este flujo garantiza una experiencia progresiva, educativa y fácil de comprender, cumpliendo con los criterios de diseño, usabilidad y funcionalidad requeridos por el proyecto.

---


<img width="1032" height="577" alt="497609067-ff733bd9-eafd-46ad-b5ba-c1093037c3ee" src="https://github.com/user-attachments/assets/9d73636b-8b85-4a89-850a-24d6801d4234" />
<img width="1034" height="575" alt="497609146-085cbf12-877f-4879-9821-ea1e10f5a866" src="https://github.com/user-attachments/assets/1b869c79-1f9a-44e8-ae88-1773b2baa613" />
<img width="1031" height="575" alt="497609277-cc34f8b9-0548-46b4-ad96-72c5bef83686" src="https://github.com/user-attachments/assets/dfc31f2d-de81-4f57-9575-23788bf4972b" />

---

## Consideraciones de diseño
---

- El diseño de las interfaces se basó en principios de **claridad, coherencia y usabilidad**.  
- Se mantuvo una paleta de colores neutra y moderna, con botones visibles y tipografía legible para facilitar la navegación.  
- Cada pantalla sigue una **estructura jerárquica** que guía al usuario desde la información teórica hasta la interacción práctica.  
- Además, se priorizó la **simplicidad visual** para evitar distracciones y mantener el enfoque en el objetivo del sistema: aprender y simular el armado de una PC de manera intuitiva y didáctica.
