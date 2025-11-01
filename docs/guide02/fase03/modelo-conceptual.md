# Modelo Conceptual de Datos

El modelo conceptual de datos del sistema **3D PC Builder** define las entidades, atributos y relaciones que permiten almacenar la información sobre los componentes, configuraciones y reglas de compatibilidad.  
El modelo sigue la notación **Entidad–Relación (E–R)** y mantiene coherencia con los casos de uso y procesos definidos.

## Entidades principales

### 1. Componente
Representa cada pieza de hardware disponible en el sistema.  
**Atributos:**  
- ID_Componente (PK)  
- Nombre  
- Tipo (CPU, GPU, RAM, etc.)  
- Precio  
- Descripción  
- Imagen3D  
- Fecha_Registro  

### 2. Compatibilidad
Define las relaciones entre componentes y si pueden funcionar juntos.  
**Atributos:**  
- ID_Compatibilidad (PK)  
- ID_ComponenteA (FK)  
- ID_ComponenteB (FK)  
- Estado (Compatible / Incompatible)  
- Descripción  

### 3. Configuración
Registra una construcción virtual creada por un usuario.  
**Atributos:**  
- ID_Configuración (PK)  
- Nombre_Usuario  
- Fecha_Creación  
- Precio_Total  
- Lista_Componentes (JSON o array)  

### 4. Usuario (opcional)
Permite identificar a quien crea las configuraciones.  
**Atributos:**  
- ID_Usuario (PK)  
- Nombre  
- Correo  
- Institución  

## Relaciones entre entidades
- Un **Componente** puede pertenecer a muchas **Configuraciones** (N:N).  
- Una **Configuración** contiene varios **Componentes** (N:N).  
- Una **Compatibilidad** relaciona dos **Componentes** específicos (1:1).  
- Un **Usuario** puede crear muchas **Configuraciones** (1:N).

## Justificación
Este modelo conceptual permite representar la estructura de datos del sistema sin depender aún de un motor de base de datos.  
El diseño se enfoca en garantizar la coherencia entre los elementos físicos (componentes) y sus propiedades lógicas (compatibilidad, precio, relación funcional).

*(Incluir diagrama ER exportado en formato .png o .jpg con resolución de 300 dpi.)*
