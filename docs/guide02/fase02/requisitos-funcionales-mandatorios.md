# Requisitos Funcionales Mandatorios

Los requisitos funcionales mandatorios definen las **funcionalidades esenciales que el sistema 3D PC Builder debe implementar obligatoriamente** para cumplir su propósito principal: permitir al usuario simular, visualizar y construir una computadora de manera virtual.  
Sin el cumplimiento de estos requisitos, el software no podría considerarse funcional ni alineado a sus objetivos de diseño.

---

## Lista de requisitos mandatorios

1. **Ensamblaje de PC en 3D paso a paso.**  
   El sistema debe permitir el ensamblaje de una computadora en 3D de forma guiada, mostrando cómo se van agregando los componentes dentro del gabinete virtual en una secuencia lógica.
   
2. **Validación automática de compatibilidad entre componentes.**  
   El sistema debe implementar un módulo de validación de compatibilidad que compruebe las relaciones entre los diferentes componentes del PC virtual.  
   Esto incluye, entre otros aspectos:
   - Compatibilidad CPU – placa base.  
   - Compatibilidad RAM – placa base.  
   - Relación entre consumo total de energía y capacidad de la fuente de poder.  
   - Compatibilidad de almacenamiento con la interfaz disponible.
  
3. **Notificación de errores, advertencias y tips de seguridad.**  
   Cuando se detecte una incompatibilidad o una posible mala práctica de armado, el sistema debe:
   - Mostrar alertas visuales o mensajes emergentes claros indicando el tipo de conflicto.  
   - Proporcionar sugerencias de corrección para guiar al usuario.  
   - Incluir tips o recomendaciones de seguridad sobre buenas prácticas de ensamblaje.

4. **Generación de reporte del ensamblaje.**  
   El sistema debe permitir generar un reporte con el detalle del ensamblaje realizado por el usuario, incluyendo como mínimo:
   - Lista de componentes seleccionados.  
   - Resultado de la validación de compatibilidad.  
   - Observaciones o advertencias relevantes.

5. **Acceso a una biblioteca de componentes.**  
   El sistema debe proporcionar acceso a una biblioteca de componentes donde el usuario pueda consultar información técnica básica de cada pieza de hardware disponible, como:
   - Nombre del componente.  
   - Tipo (CPU, GPU, RAM, etc.).  
   - Especificaciones clave (capacidad, frecuencia, TDP, socket, etc.).
