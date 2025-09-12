# Desglose del Trabajo (WBS) — MVP 3D PC Builder (3 meses)

> Solo incluye actividades para el **MVP** a entregar en diciembre.  
> Funciones excluidas: “Explorar componentes”, guardar/cargar ensambles, y extras avanzados.

## 1. Análisis
| ID   | Tarea                          | Entregable                          | Responsable |
|------|--------------------------------|-------------------------------------|-------------|
| 1.1  | Recopilar requisitos           | Documento de requisitos validado     | Yandira     |
| 1.2  | Casos de uso del MVP           | Diagramas de casos de uso básicos    | Yandira     |
| 1.3  | Validación de requisitos       | Acta de validación MVP               | Yandira/Erick |

## 2. Diseño
| ID   | Tarea                          | Entregable                          | Responsable |
|------|--------------------------------|-------------------------------------|-------------|
| 2.1  | Arquitectura del software      | Documento de arquitectura            | Wilmer/Erick |
| 2.2  | Modelo de datos simplificado   | Diagrama ER básico                   | Wilmer      |
| 2.3  | Mockups UI MVP                 | Mockups del menú + Armar PC          | Josue/Yandira |
| 2.4  | Especificación modelado 3D     | Documento de piezas mínimas (CPU, MB, RAM, GPU, PSU, Case)| Josue |

## 3. Implementación (MVP)
### 3.1 Backend — Wilmer
| ID   | Tarea                          | Entregable                          | Responsable |
|------|--------------------------------|-------------------------------------|-------------|
| 3.1.1| Validación compatibilidad      | Módulo que valide componentes básicos | Wilmer (MVP) |
| 3.1.2| Sistema de mensajes y avisos   | Funciones de tips y errores          | Wilmer (MVP) |
| 3.2.3| Módulo de estimación de costos (rangos)        | Función para calcular costos basados en rangos locales  | Wilmer                 |

### 3.2 Frontend (Unity/C#) — Josue
| ID   | Tarea                          | Entregable                          | Responsable |
|------|--------------------------------|-------------------------------------|-------------|
| 3.2.1| Menú Principal                 | Escena con botones "Explorar" y "Armar PC" (solo Armar PC funcional) | Josue (MVP) |
| 3.2.2| Opción "Armar PC" — escena base| Vista dividida 3D (izq) + catálogo (der) | Josue (MVP) |
| 3.2.3| Drag & Drop de componentes     | Función de arrastre y colocación     | Josue (MVP) |
| 3.2.4| Notificaciones UI              | Sistema visual de avisos y errores   | Josue (MVP) |
| 3.2.5| Integración con backend        | Flujo ensamblar ↔ validación         | Josue/Wilmer |

### 3.3 Modelado 3D (Blender → Unity)
| ID   | Tarea                          | Entregable                          | Responsable |
|------|--------------------------------|-------------------------------------|-------------|
| 3.3.1| Modelado piezas mínimas        | CPU, motherboard, RAM, GPU, PSU, Case | Josue |
| 3.3.2| Optimización para Unity        | Modelos FBX optimizados             | Josue |
| 3.3.3| Importación en Unity           | Catálogo de assets listo            | Josue |

## 4. Pruebas
| ID   | Tarea                          | Entregable                          | Responsable |
|------|--------------------------------|-------------------------------------|-------------|
| 4.1  | Pruebas unitarias              | Reporte de validación módulos        | Wilmer/Josue |
| 4.2  | Pruebas de integración         | Flujo ensamblaje completo probado    | Todo el equipo |
| 4.3  | Beta interna (usabilidad)      | Feedback de uso                      | Yandira coordina |

## 5. Entrega
| ID   | Tarea                          | Entregable                          | Responsable |
|------|--------------------------------|-------------------------------------|-------------|
| 5.1  | Build MVP (Windows)            | Ejecutable MVP funcional             | Josue/Wilmer |
| 5.2  | Documentación de usuario       | Manual básico del MVP                | Yandira |
| 5.3  | Presentación final             | Slides + demo en vivo                | Erick |

---

## Hitos (Milestones)
- **H1** — Requisitos y casos de uso del MVP completados  
- **H2** — Diseño validado (mockups + arquitectura + modelos 3D mínimos)  
- **H3** — Implementación del flujo “Armar PC” (drag & drop + validación + mensajes)  
- **H4** — Pruebas internas y corrección de errores  
- **H5** — Entrega MVP y presentación  

