---
tags: [capa/mejora]
---

# Mejora - Caché de rankings y datos

**Categoría:** 🟡 Mediana

**Hoy:** cada visita al inicio recalcula novedades, populares y recomendados en PostgreSQL. En el front, cada hook vuelve a pedir los datos al montar la página.

**Propuesta:**
- Backend: caché corta (1 a 5 minutos) para `/works/popular` y `/chapters/latest`, o cabeceras `Cache-Control`.
- Frontend: cachear respuestas por clave (por ejemplo con TanStack Query, si se aprueba agregarla).

Módulo: [[Módulo Descubrimiento]] · Estado: [[Frontend - Estado global]] · Índice: [[Mejoras - Mapa]]
