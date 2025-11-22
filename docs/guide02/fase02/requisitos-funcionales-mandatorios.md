# Requisitos Funcionales Mandatorios

Los requisitos funcionales mandatorios definen las **funcionalidades esenciales que el sistema 3D PC Builder debe implementar obligatoriamente** para cumplir su propósito principal: permitir al usuario simular, visualizar y construir una computadora de manera virtual.  
Sin el cumplimiento de estos requisitos, el software no podría considerarse funcional ni alineado a sus objetivos de diseño.

---

## Lista de requisitos mandatorios

1. **Visualización 3D interactiva de los componentes y del ensamblaje.**  
   El sistema debe permitir observar los modelos tridimensionales de cada pieza de hardware y su ubicación dentro del gabinete virtual.
   Además, debe ofrecer un autoensamblado de los componentes por parte del programa

2. **Validación automática de compatibilidad entre componentes.**  
   El sistema debe implementar un módulo de validación inteligente capaz de comprobar la compatibilidad entre los diferentes componentes del PC virtual.
   Esto incluye la coherencia eléctrica, física y lógica entre elementos como CPU–placa base, RAM–placa base, fuente de poder–GPU, almacenamiento–interfaz y las dimensiones dentro del gabinete.

4. **Notificación de errores o incompatibilidades.**  
   Cuando se detecte una incompatibilidad, el sistema debe mostrar alertas visuales o mensajes emergentes claros, indicando el tipo de conflicto y sugerencias de corrección para guiar al usuario en la selección adecuada.

5. **Incorporación de tips o alertas de seguridad.**  
   Durante el proceso de ensamblaje, el sistema debe mostrar recomendaciones de buenas prácticas para evitar configuraciones incorrectas o malas prácticas de armado.
   Estas alertas deben contribuir a educar al usuario sobre el proceso de montaje seguro y correcto de los componentes.
   
6. **Ejecución en entorno de PC (plataforma principal).**  
   Su arquitectura debe permitir una instalación local completa, sin depender de servicios externos, y ser compatible con hardware estándar de desarrollo.

7. **Operación sin conexión a Internet.**  
   El sistema debe poder ejecutarse localmente, sin requerir conexión activa a la red.

8. **Rendimiento fluido en equipos de gama media.**  
   La aplicación debe ofrecer una experiencia 3D fluida y estable, con un promedio mínimo de 40 a 60 FPS al renderizar los modelos y animaciones.
   Debe estar optimizada en la carga de recursos gráficos, minimizando tiempos de espera y evitando caídas notorias de rendimiento en equipos de gama media con GPU integrada o dedicada de nivel básico.
