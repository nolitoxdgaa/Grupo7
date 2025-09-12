# Desglose del Trabajo (WBS) — 3D PC Builder

> Nota: los entregables marcados con **(MVP)** forman parte del alcance mínimo a entregar en la primera semana de diciembre.

## 1. Análisis
| ID   | Tarea                                 | Entregable                                        | Responsable (Principal) |
|------|---------------------------------------|---------------------------------------------------|-------------------------|
| 1.1  | Recopilar requisitos                  | Documento de requisitos de usuario                | Yandira (Analista)     |
| 1.2  | Revisar y consolidar requisitos       | Versión final del documento de requisitos         | Yandira / Erick (PM)   |
| 1.3  | Documentar casos de uso               | Diagramas de casos de uso / escenarios de usuario | Yandira                |
| 1.4  | Validación de requisitos con el ED    | Acta de validación / lista de prioridades (MoSCoW)| Yandira / Erick        |

## 2. Diseño
| ID   | Tarea                                 | Entregable                                        | Responsable (Principal) |
|------|---------------------------------------|---------------------------------------------------|-------------------------|
| 2.1  | Arquitectura de software              | Documento de arquitectura (componentes y flujo)   | Wilmer / Erick         |
| 2.2  | Modelo de datos                       | Diagrama ER / esquema de almacenamiento local     | Wilmer                 |
| 2.3  | Diseño de interfaces (mockups)        | Mockups / wireframes (Anexo A)                    | Josue / Yandira        |
| 2.4  | Diseño del modelado 3D (escena)       | Documento de especificaciones del modelado 3D     | Josue / Wilmer         |
| 2.5  | Plan de pruebas                       | Plan de pruebas unitarias e integración           | Todo el equipo         |

## 3. Implementación
### 3.1 Preparación del entorno y repo
| ID   | Tarea                                 | Entregable                                        | Responsable (Principal) |
|------|---------------------------------------|---------------------------------------------------|-------------------------|
| 3.1.1| Configurar repositorio GitHub         | Repositorio inicial + branch strategy             | Erick / Todo el equipo |
| 3.1.2| Configurar entornos (Unity, Blender)  | Plantilla de proyecto Unity + proyecto Blender    | Josue / Wilmer         |
| 3.1.3| Documentación de setup                | README de desarrollo (instalación, run)           | Erick / Wilmer         |

### 3.2 Backend (módulo principal) — **Wilmer**
| ID   | Tarea                                         | Entregable                                              | Responsable (Principal) |
|------|-----------------------------------------------|---------------------------------------------------------|-------------------------|
| 3.2.1| Implementar esquema de datos local             | Módulo de almacenamiento (JSON / SQLite / Postgre local)| Wilmer                 |
| 3.2.2| Módulo de validación de compatibilidad         | Servicio/funciones: validar socket, voltaje, etc.       | Wilmer **(MVP)**       |
| 3.2.3| Módulo de estimación de costos (rangos)        | Función para calcular costos basados en rangos locales  | Wilmer                 |
| 3.2.4| Módulo de guardado/carga de ensambles          | Funciones Save/Load de proyectos de usuario            | Wilmer **(MVP)**       |
| 3.2.5| API interna o puente (si se usa Python)        | Scripts Python o endpoints locales para lógica externa | Wilmer / (Python)      |
| 3.2.6| Tests unitarios backend                        | Suite de pruebas unitarias                              | Wilmer                 |

### 3.3 Frontend / Unity (C#) — **Josue**
| ID   | Tarea                                         | Entregable                                              | Responsable (Principal) |
|------|-----------------------------------------------|---------------------------------------------------------|-------------------------|
| 3.3.1| Implementar Menú Principal                     | Escena/menu funcionando                                 | Josue **(MVP)**        |
| 3.3.2| Módulo "Explorar Componentes"                  | Lista de componentes + ventana detalle (UI)            | Josue **(MVP)**        |
| 3.3.3| Módulo "Armar PC" (interfaz dividida)          | Escena con modelado 3D (izq) y catálogo (der)          | Josue **(MVP)**        |
| 3.3.4| Lógica drag & drop y colocación en modelado    | Sistema de arrastre, validación de espacio              | Josue **(MVP)**        |
| 3.3.5| Mensajería: errores, tips y recomendaciones     | Sistema UI para notificaciones y sugerencias           | Josue **(MVP)**        |
| 3.3.6| Integración UI ↔ Backend                        | Conexiones a funciones de validación/guardado           | Josue ↔ Wilmer         |
| 3.3.7| Tests unitarios frontend                        | Suite de pruebas unitarias                              | Josue                  |

### 3.4 Modelos y assets (Blender) — **Josue / Wilmer**
| ID   | Tarea                                         | Entregable                                              | Responsable (Principal) |
|------|-----------------------------------------------|---------------------------------------------------------|-------------------------|
| 3.4.1| Modelado 3D de componentes básicos            | Modelos .blend / FBX (CPU, MB, RAM, GPU, PSU, Case...)  | Josue                  |
| 3.4.2| Optimización y LOD                             | Modelos optimizados para Unity                          | Josue                  |
| 3.4.3| Exportación y pipeline a Unity                 | Assets listos e importados en Unity                     | Josue / Wilmer         |

## 4. Integración y pruebas
| ID   | Tarea                                 | Entregable                                        | Responsable (Principal) |
|------|---------------------------------------|---------------------------------------------------|-------------------------|
| 4.1  | Pruebas unitarias (backend + frontend)| Reporte de tests unitarios                        | Wilmer / Josue         |
| 4.2  | Pruebas de integración                 | Reporte de integración: flujos (arrastre→validación)| Wilmer / Josue         |
| 4.3  | Pruebas de usabilidad (beta interna)   | Feedback y lista de mejoras                        | Yandira (coordina) / Todo |
| 4.4  | Corrección de fallos                   | Versión estable previa a MVP                       | Todo el equipo         |

## 5. Entrega, documentación y presentación
| ID   | Tarea                                 | Entregable                                        | Responsable (Principal) |
|------|---------------------------------------|---------------------------------------------------|-------------------------|
| 5.1  | Build MVP (Windows)                    | Ejecutable/instalable del MVP **(MVP)**           | Wilmer / Josue         |
| 5.2  | Documentación de usuario               | Manual de usuario (Anexo)                         | Yandira                |
| 5.3  | Documentación técnica                  | Guía de instalación / arquitectura / API          | Wilmer / Erick         |
| 5.4  | Preparación de presentación            | Slides + demo para exposición                     | Erick (lead) / Todo    |
| 5.5  | Repositorio final y entrega            | Repo con código, README, releases                 | Erick / Todo           |

## 6. Gestión del proyecto y soporte
| ID   | Tarea                                 | Entregable                                        | Responsable (Principal) |
|------|---------------------------------------|---------------------------------------------------|-------------------------|
| 6.1  | Planificación (sprints / hitos)        | Cronograma / calendario de sprints                | Erick (PM)             |
| 6.2  | Revisión de avance semanal             | Actas de reunión / reportes de avance             | Erick / Todo           |
| 6.3  | Control de versiones y ramas           | Política Git (branching, PR, review)              | Erick / Todo           |
| 6.4  | Gestión de riesgos                     | Registro de riesgos y planes de mitigación        | Erick                  |
| 6.5  | Soporte y mantenimiento post-entrega   | Lista de tareas pendientes / backlog              | Todo el equipo         |

---

## Hitos (Milestones)
- **H1** — Requisitos aprobados (Entrega: Documento de requisitos) → Responsable: Yandira / Erick  
- **H2** — Diseño completado (Mockups + Arquitectura) → Responsable: Josue / Wilmer  
- **H3** — Implementación core (validación + modelado + UI básica) → Responsable: Wilmer / Josue **(MVP)**  
- **H4** — Pruebas e integración completadas → Responsable: Todo el equipo  
- **H5** — Entrega MVP + Presentación → Responsable: Erick / Todo el equipo

---

### Observaciones y recomendaciones
- Las tareas marcadas como **(MVP)** son prioritarias y deben recibir asignación de tiempo primera en el cronograma.  
- Se recomienda definir estimaciones temporales (horas/días) para cada tarea en la planificación de sprints.  
- Las pruebas de usabilidad con usuarios reales (compañeros/estudiantes) son críticas para validar la interfaz y el flujo de ensamblaje.  
- Mantener ramas claras en Git (por ejemplo `main`, `dev`, `feature/*`) y PRs con revisión por al menos otro integrante.

