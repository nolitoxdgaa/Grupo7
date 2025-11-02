# Pseudocódigo de los Requisitos de Sistema Más Importantes

Los siguientes pseudocódigos representan los procesos fundamentales que garantizan el correcto funcionamiento del sistema **3D PC Builder**.

---

## Pseudocódigo 1 — Verificación de Compatibilidad
```pseudocode
Inicio
    Para cada componente seleccionado en la lista
        Comparar tipo y atributos técnicos (socket, potencia, conector)
        Si existe incompatibilidad
            Mostrar alerta visual y sonora
        Sino
            Mostrar mensaje "Componente compatible"
        FinSi
    FinPara
Fin
```
---
**Objetivo:** Evitar que el usuario combine componentes técnicamente incompatibles y reforzar la comprensión de los parámetros de compatibilidad.

---

## Pseudocódigo 2 — Cálculo de Precio Total
```pseudocode
Inicio
  total ← 0
  Para cada componente seleccionado
    total ← total + componente.precio
  FinPara
Mostrar "Precio Total: " + total
Fin
```

**Objetivo:** Mostrar el costo total de la configuración de manera automática y dinámica al modificar la lista de componentes.

---

## Pseudocódigo 3 — Guardado de Configuración
```pseudocode
Inicio
  Crear objeto JSON vacío
  Para cada componente seleccionado
    Agregar nombre, tipo y precio al JSON
  FinPara
  Guardar JSON en carpeta /config/
  Mostrar mensaje "Configuración guardada correctamente"
Fin
```

**Objetivo:** Permitir que el usuario almacene su progreso y pueda recuperar configuraciones anteriores.

---

## Pseudocódigo 4 — Generación de Reporte Final
```pseudocode
Inicio
    Crear documento PDF vacío
    Agregar lista de componentes seleccionados con precios y compatibilidad
    Calcular precio total
    Guardar documento en carpeta /reportes/
    Mostrar mensaje "Reporte generado con éxito"
Fin
```

**Objetivo:** Generar un informe completo y exportable que resuma la configuración final del sistema con todos los detalles técnicos y económicos.
