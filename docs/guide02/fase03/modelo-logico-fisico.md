## Modelo lógico-físico de datos (Opcional):
# Modelo Lógico–Físico de Datos (Opcional)

En caso de implementar una base de datos para almacenar los componentes y configuraciones, se propone el siguiente modelo lógico–físico desarrollado en **MySQL Workbench**.

## Tablas propuestas

### Tabla: componentes
| Campo | Tipo de dato | Descripción |
|-------|---------------|--------------|
| id_componente | INT (PK) | Identificador único del componente |
| nombre | VARCHAR(100) | Nombre del componente |
| tipo | VARCHAR(50) | Categoría (CPU, GPU, RAM, etc.) |
| precio | DECIMAL(10,2) | Costo individual |
| descripcion | TEXT | Detalle técnico |
| imagen | VARCHAR(255) | Ruta del modelo 3D |

### Tabla: compatibilidades
| Campo | Tipo | Descripción |
|-------|------|-------------|
| id_compatibilidad | INT (PK) | Identificador |
| componente_a | INT (FK) | ID del primer componente |
| componente_b | INT (FK) | ID del segundo componente |
| estado | BOOLEAN | 1 si son compatibles |
| observacion | TEXT | Descripción de la regla |

### Tabla: configuraciones
| Campo | Tipo | Descripción |
|-------|------|-------------|
| id_configuracion | INT (PK) | Identificador único |
| usuario | VARCHAR(100) | Nombre del creador |
| fecha | DATE | Fecha de creación |
| precio_total | DECIMAL(10,2) | Costo total |
| componentes | TEXT | Lista serializada de componentes |

## Consideraciones físicas
- Motor de base de datos: **InnoDB**  
- Claves foráneas con eliminación en cascada para mantener integridad referencial.  
- Índices en campos de tipo y nombre para optimizar las búsquedas.  

## Ventajas
- Permite la expansión futura hacia una aplicación conectada a base de datos real.  
- Facilita la migración hacia un sistema web o multiplataforma.  
- Mantiene trazabilidad entre configuraciones y componentes.

*(Incluir imagen del modelo físico generado en MySQL Workbench, 300 dpi.)*
