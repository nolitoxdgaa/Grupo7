# Modelo Lógico–Físico de Datos (Opcional)

En caso de implementarse una base de datos para almacenar los **componentes**, **ensamblajes** y **reportes** del sistema **3D PC Builder**, se propone el siguiente modelo lógico–físico, diseñado en **MySQL Workbench**.  
Este modelo sigue la estructura definida en el **modelo conceptual de datos**, adaptándola al nivel físico mediante tipos de datos y claves relacionales.

---

## Tablas propuestas

### Tabla: `componentes`
| Campo | Tipo de dato | Descripción |
|--------|---------------|-------------|
| `id_componente` | INT (PK, AUTO_INCREMENT) | Identificador único del componente |
| `nombre` | VARCHAR(100) | Nombre del componente |
| `tipo` | VARCHAR(50) | Categoría (CPU, GPU, RAM, etc.) |
| `precio` | DECIMAL(10,2) | Costo individual |
| `descripcion` | TEXT | Detalle técnico del componente |
| `imagen3d` | VARCHAR(255) | Ruta o referencia del modelo 3D |

---

### Tabla: `ensamblajes`
| Campo | Tipo de dato | Descripción |
|--------|---------------|-------------|
| `id_ensamblaje` | INT (PK, AUTO_INCREMENT) | Identificador único del ensamblaje |
| `fecha` | DATE | Fecha de creación |
| `estado` | VARCHAR(50) | Estado del ensamblaje (completo, en progreso, etc.) |
| `id_usuario` | INT (FK) | Usuario que realizó el ensamblaje |

---

### Tabla: `usuarios`
| Campo | Tipo de dato | Descripción |
|--------|---------------|-------------|
| `id_usuario` | INT (PK, AUTO_INCREMENT) | Identificador único del usuario |
| `nombre` | VARCHAR(100) | Nombre del usuario |
| `correo` | VARCHAR(100) | Correo electrónico del usuario |

---

### Tabla intermedia: `ensamblaje_componentes`
Relaciona los componentes incluidos en cada ensamblaje (resuelve la relación N:N).  
| Campo | Tipo de dato | Descripción |
|--------|---------------|-------------|
| `id_ensamblaje` | INT (FK) | Identificador del ensamblaje |
| `id_componente` | INT (FK) | Identificador del componente |
| `cantidad` | INT | Cantidad o número de piezas utilizadas |

---

### Tabla: `reportes`
| Campo | Tipo de dato | Descripción |
|--------|---------------|-------------|
| `id_reporte` | INT (PK, AUTO_INCREMENT) | Identificador único del reporte |
| `id_ensamblaje` | INT (FK) | Ensamblaje que genera el reporte |
| `fecha` | DATE | Fecha de generación |
| `detalle` | TEXT | Descripción o contenido del reporte |

---

## Consideraciones físicas

- **Motor de base de datos:** `InnoDB`  
  → Permite transacciones seguras y soporte de claves foráneas.  
- **Integridad referencial:**  
  → Claves foráneas con eliminación en cascada (`ON DELETE CASCADE`) para mantener coherencia entre ensamblajes, usuarios y componentes.  
- **Optimización de búsqueda:**  
  → Índices en los campos `tipo` y `nombre` de la tabla `componentes` para acelerar consultas.  

---

## Ventajas del modelo

- Permite futura expansión hacia una **aplicación web o multiplataforma** conectada a base de datos real.  
- Facilita la **trazabilidad** entre configuraciones, usuarios y componentes.  
- Mantiene una **estructura normalizada** y coherente con el modelo conceptual.  
- Simplifica la **migración** a sistemas basados en la nube o integrados con APIs RESTful.

---

## Instrucción para incluir el diagrama

> Incluir el **modelo físico de base de datos** exportado desde **MySQL Workbench** en formato `.png` o `.jpg` con resolución de **300 dpi**, asegurando que todas las entidades, relaciones y cardinalidades sean legibles.


