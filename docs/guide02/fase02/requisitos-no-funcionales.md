# Requisitos No Funcionales

Los **requisitos no funcionales** definen los **criterios de calidad, las limitaciones técnicas y las condiciones de uso** bajo las cuales debe operar el sistema **3D PC Builder**.  
No describen funciones específicas, sino las **características de desempeño, compatibilidad, mantenimiento y entorno de ejecución**.

---

## Lista de requisitos no funcionales

1. **Portabilidad.**  
   El sistema debe ejecutarse en equipos portátiles o de escritorio con:
   - **Sistema operativo:** Windows 10 o superior.  
   - **GPU dedicada de gama media** (por ejemplo, RTX 3060 o similar) para garantizar un rendimiento adecuado en la visualización 3D.

2. **Mantenibilidad.**  
   El código debe estar estructurado de forma **modular**, utilizando:
   - **C# (Unity)** como lenguaje principal de la aplicación.  
   - **Python** para herramientas auxiliares o scripts cuando sea necesario.  
   - Control de versiones mediante **GitHub**.  
   Además, debe mantenerse **documentación técnica básica** en un archivo **README.md**, incluyendo instrucciones de instalación y ejecución.

3. **Usabilidad.**  
   La interfaz gráfica debe ser:
   - **Intuitiva y accesible** para usuarios principiantes.  
   - Acompañada de **mensajes de error claros** y comprensibles.  
   - Coherente en su navegación entre las distintas pantallas del sistema.

4. **Velocidad de procesamiento y rendimiento visual.**  
   La aplicación debe mantener una **tasa mínima de 30 FPS** durante la visualización y el proceso de ensamblaje en 3D, asegurando:
   - Fluidez en la experiencia del usuario.  
   - Ausencia de caídas bruscas de rendimiento en equipos que cumplan las especificaciones mínimas.

5. **Restricciones técnicas.**  
   El desarrollo del sistema estará limitado a herramientas y tecnologías de **libre acceso**, tales como:
   - **Unity (C#)** para la aplicación principal.  
   - **Blender** para la creación o edición de modelos 3D.  
   - **Python** para automatización o scripts de soporte.  
   Asimismo:
   - La plataforma objetivo es **Windows 10 o superior**.  
   - En el **MVP** no habrá integración con sistemas ni servicios externos (APIs de terceros u otros).

6. **Dependencia de red y modo de operación.**  
   El sistema debe poder ejecutarse **sin requerir conexión activa a Internet** para sus funcionalidades principales, de manera que:
   - Todo el proceso de ensamblaje, validación y generación de reporte funcione de forma **local**.  
   - La experiencia del usuario no dependa de la disponibilidad de red.
