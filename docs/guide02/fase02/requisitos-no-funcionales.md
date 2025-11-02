# Requisitos No Funcionales

Los **requisitos no funcionales** definen los **criterios de calidad, las limitaciones técnicas y las condiciones de uso** bajo las cuales debe operar el sistema **3D PC Builder**.  
Estos requisitos no describen funciones específicas del software, sino las **características de desempeño, compatibilidad y mantenimiento** que garantizan su correcto funcionamiento y experiencia de usuario.

---

## Lista de requisitos no funcionales

1. **Portabilidad.**  
   El sistema debe ejecutarse en equipos portátiles o de escritorio con **Windows 10 o superior**, que cuenten con una **GPU dedicada** (RTX 3060 o equivalente) para garantizar el rendimiento adecuado de la simulación 3D.

2. **Mantenibilidad.**  
   El código fuente debe estar estructurado de forma **modular**, empleando los lenguajes **C# (Unity)** y **Python**, con control de versiones mediante **GitHub** y documentación técnica detallada en el archivo **README.md**.

3. **Usabilidad.**  
   La interfaz gráfica debe ser **intuitiva y accesible**, orientada a usuarios principiantes, con mensajes de error claros, instrucciones breves y una navegación coherente entre pantallas.

4. **Velocidad de procesamiento.**  
   La aplicación debe mantener una **tasa mínima de 30 cuadros por segundo (FPS)** durante la visualización y ensamblaje 3D, asegurando una experiencia fluida y estable.

5. **Restricciones técnicas.**  
   El desarrollo debe limitarse al uso de **herramientas y librerías de libre acceso**, como **Unity (C#)**, **Blender** y **Python**, ejecutándose exclusivamente en sistemas **Windows 10 o superior**.  
   En la versión **MVP** (Producto Mínimo Viable) no se considerará la integración con servicios o sistemas externos.
