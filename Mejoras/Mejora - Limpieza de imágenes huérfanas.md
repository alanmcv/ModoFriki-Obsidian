---
tags: [capa/mejora]
---

# Mejora - Limpieza de imágenes huérfanas

**Categoría:** 🟡 Mediana

**Hoy:** la tabla `MediaCleanupJob` existe, pero ningún código la usa. Los lotes ABANDONED, las portadas reemplazadas y los borrados fallidos dejan archivos en Blob para siempre.

**Propuesta:** un proceso programado (cron de Render o GitHub Actions) que:
1. Busque `MediaAsset` sin referencias y `UploadObject` de lotes vencidos.
2. Cree un `MediaCleanupJob` por archivo.
3. Lo borre de Blob con reintentos (`attempts`, `nextAttemptAt`) y marque `CLEANED`.

**Beneficio:** Blob cobra por almacenamiento; con autores subiendo capítulos, el costo crece → [[Estructura de costos]].

BD: [[BD - Multimedia]] · Pipeline: [[Backend - Pipeline multimedia]] · Índice: [[Mejoras - Mapa]]
