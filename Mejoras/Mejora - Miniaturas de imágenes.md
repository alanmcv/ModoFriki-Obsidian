---
tags: [capa/mejora]
---

# Mejora - Miniaturas de imágenes

**Categoría:** 🟡 Mediana

**Hoy:** las imágenes se guardan y se sirven en su tamaño original (hasta 10 MiB). El catálogo, el inicio y los rankings descargan portadas completas solo para mostrarlas pequeñas.

**Propuesta:**
- Al subir una portada, generar además una **miniatura WebP** (por ejemplo 300 px de ancho) y guardarla como otro `MediaAsset`.
- Opcional: convertir páginas a WebP con calidad ajustada.
- El front usa la miniatura en tarjetas y la original en la ficha.

**Beneficio:** el ancho de banda de Blob es el **costo más grande** del negocio ([[Estructura de costos]]), y el inicio carga mucho más rápido en celular.

**Riesgo:** toca el [[Backend - Pipeline multimedia]], que es la parte más delicada; requiere una migración aditiva y una librería de imágenes (por ejemplo `sharp`).

Relacionado: [[BD - Multimedia]] · [[Mejora - Limpieza de imágenes huérfanas]] · Índice: [[Mejoras - Mapa]]
