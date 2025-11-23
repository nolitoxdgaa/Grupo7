# Requisitos Funcionales Mandatorios

Los requisitos funcionales mandatorios definen las **funcionalidades esenciales que el sistema 3D PC Builder debe implementar obligatoriamente** para cumplir su propósito principal: permitir al usuario simular, visualizar y construir una computadora de manera virtual.  
Sin el cumplimiento de estos requisitos, el software no podría considerarse funcional ni alineado a sus objetivos de diseño.

---

## Lista de requisitos mandatorios

1. **Ensamblaje de PC en 3D paso a paso.**  
   El sistema debe permitir el **ensamblaje de una computadora en 3D de forma guiada**, mostrando cómo se van agregando los componentes dentro del gabinete virtual en una secuencia lógica (corresponde a **RF1** del RTM).
---
   @startuml
title Ensamblaje de PC en 3D paso a paso (RF1)

|Usuario|
start
:Abre módulo de ensamblaje 3D;

|Sistema|
:Mostrar gabinete / área de trabajo;
:Mostrar categorías de componentes disponibles;

|Usuario|
:Seleccionar categoría de componente
(CPU, RAM, GPU, etc.);

|Sistema|
:Listar componentes de la categoría seleccionada;

|Usuario|
:Seleccionar componente;

|Sistema|
:Agregar componente al ensamblaje 3D;
:Actualizar vista del gabinete con el nuevo componente;

|Usuario|
if (¿Desea agregar más componentes?) then (Sí)
  :Seleccionar nueva categoría
  o componente;
  -[#black]-> |Sistema|
  :Listar componentes de la nueva categoría;
  -down-> |Usuario|
  :Seleccionar componente;
  -down-> |Sistema|
  :Agregar componente y actualizar vista 3D;
  -up-> |Usuario|
else (No)
  :Finalizar proceso de ensamblaje;
endif

|Sistema|
:Marcar estado del ensamblaje como "completo" (o "parcial");
stop
@enduml

---
3. **Validación automática de compatibilidad entre componentes.**  
   El sistema debe implementar un módulo de **validación de compatibilidad** que compruebe las relaciones entre los diferentes componentes del PC virtual (corresponde a **RF2** del RTM).  
   Esto incluye, entre otros aspectos:
   - Compatibilidad CPU – placa base.  
   - Compatibilidad RAM – placa base.  
   - Relación entre consumo total de energía y capacidad de la fuente de poder.  
   - Compatibilidad de almacenamiento con la interfaz disponible.  

4. **Notificación de errores, advertencias y tips de seguridad.**  
   Cuando se detecte una incompatibilidad o una posible mala práctica de armado, el sistema debe:
   - Mostrar **alertas visuales o mensajes emergentes claros** indicando el tipo de conflicto.  
   - Proporcionar **sugerencias de corrección** para guiar al usuario.  
   - Incluir **tips o recomendaciones de seguridad** sobre buenas prácticas de ensamblaje (corresponde a **RF3** del RTM).

5. **Generación de reporte del ensamblaje.**  
   El sistema debe permitir **generar un reporte** con el detalle del ensamblaje realizado por el usuario (corresponde a **RF4** del RTM), incluyendo como mínimo:
   - Lista de componentes seleccionados.  
   - Resultado de la validación de compatibilidad.  
   - Observaciones o advertencias relevantes.

6. **Acceso a una biblioteca de componentes.**  
   El sistema debe proporcionar acceso a una **biblioteca de componentes** donde el usuario pueda consultar información técnica básica de cada pieza de hardware disponible (corresponde a **RF5** del RTM), como:
   - Nombre del componente.  
   - Tipo (CPU, GPU, RAM, etc.).  
   - Especificaciones clave (capacidad, frecuencia, TDP, socket, etc.).
