# Modelo Conceptual de Datos

El **modelo conceptual de datos** del sistema **3D PC Builder** define las entidades, atributos y relaciones necesarias para representar la información de los componentes de hardware, los ensamblajes virtuales, los usuarios y los reportes generados dentro del entorno de simulación.  
Este modelo fue diseñado bajo la notación **Entidad–Relación (E–R)** y mantiene coherencia con los procesos y casos de uso del sistema.

---

## Entidades principales

### 1. Ensamblaje
Representa una configuración o construcción virtual creada por el usuario.  
**Atributos:**
- `ID_Ensamblaje` (PK)
- `Fecha`
- `Estado`

---

### 2. Usuario
Contiene la información del usuario que crea y gestiona los ensamblajes.  
**Atributos:**
- `ID_Usuario` (PK)
- `Nombre`
- `Correo`

---

### 3. Componente
Define cada pieza de hardware disponible (CPU, GPU, RAM, etc.).  
**Atributos:**
- `ID_Componente` (PK)
- `Nombre`
- `Tipo`
- `Precio`
- `Compatibilidad`

---

### 4. Reporte
Registra la información generada tras la creación o modificación de un ensamblaje.  
**Atributos:**
- `ID_Reporte` (PK)
- `Fecha`
- `Detalle`

---

## Relaciones entre entidades

- **Usuario — REALIZA → Ensamblaje:** un usuario puede realizar varios ensamblajes (1:N).  
- **Ensamblaje — CONTIENE → Componente:** un ensamblaje contiene varios componentes (1:N).  
- **Ensamblaje — GENERA → Reporte:** un ensamblaje genera un reporte (1:1).
- **Compatibilidad entre componentes:** puede representarse mediante una relación N:N o mediante una entidad intermedia si se requiere más detalle.  

---

## Justificación del modelo

El modelo conceptual propuesto permite estructurar de forma lógica la información clave del sistema, asegurando una adecuada representación de los **componentes físicos** (hardware) y sus **interacciones funcionales** (ensamblaje, compatibilidad, usuario, reporte).  
Este diseño sirve como base para la implementación posterior del **modelo lógico y físico** en el motor de base de datos **MySQL**.

---

![Imagen de WhatsApp 2025-11-02 a las 02 05 22_2a7eb776](https://github.com/user-attachments/assets/7a077aef-998f-47f3-89a1-58e72444bd4f)



