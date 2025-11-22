# Pseudocódigo de los Requisitos de Sistema Más Importantes

Los siguientes pseudocódigos representan los procesos fundamentales que garantizan el correcto funcionamiento del sistema **3D PC Builder**.

---

## Pseudocódigo 1 — Verificación de Compatibilidad
```pseudocode
Inicio
    build ← GameManager.ObtenerBuildActual()

    Para cada componente en build
        Para cada otro componente en build
            Si componente.tipo ≠ otro.tipo
                Si NO son compatibles según reglas (socket, chipset, potencia, tamaño)
                    Marcar ambos como incompatibles
                    Mostrar alerta visual en UI
                FinSi
            FinSi
        FinPara
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

## Pseudocódigo 3 - Visualización de Modelos 3D (Individual y Combinado)
```pseudocode
Inicio
    build ← GameManager.ObtenerBuildActual()

    Si build está vacía
        Limpiar todos los contenedores 3D
        Salir
    FinSi

    Si build.count = 1
        componente ← build[0]
        Limpiar contenedor individual de ese tipo
        Instanciar modelo 3D correspondiente al componente en su contenedor
    Sino
        Limpiar todos los contenedores de modelos individuales

        nombresOrdenados ← ordenar componentes según:
            [CPU, Motherboard, RAM, SSD, Case, PSU, GPU]

        nombreCombinado ← unir con "_"

        modeloCombinado ← buscar en carpeta "ContenedorCombi/{n}"
            donde n = cantidad de componentes seleccionados

        Instanciar modeloCombinado en contenedor principal
    FinSi
Fin
```

**Objetivo:** Representar la lógica implementada: Modelos individuales → si la build contiene 1 solo componente. Modelo combinado → si hay 2 o más. Nombre de archivo basado en orden estricto de tipos. Limpieza automática de modelos anteriores.

---

## Pseudocódigo 4 — Sistema de Rotación del Modelo 3D
```pseudocode
Inicio (Update)
    Si tecla flecha izquierda presionada
        rotar modelo en eje Y negativo
    Si tecla flecha derecha presionada
        rotar modelo en eje Y positivo

    Si tecla flecha arriba presionada
        rotar modelo en eje X negativo
    Si tecla flecha abajo presionada
        rotar modelo en eje X positivo

    Si tecla R presionada
        restablecer rotación del modelo a (0, 0, 0)
Fin
```
**Objetivo:** Control simple e intuitivo para rotar cualquier modelo cargado.
