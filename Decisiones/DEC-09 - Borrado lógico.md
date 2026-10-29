---
tags: [decision]
estado: aceptada
fuente: docs/features/MODELO_DATOS_PROPUESTO.md
---

# DEC-09 - Borrado lógico

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** docs/features/MODELO_DATOS_PROPUESTO.md

## Contexto
Obras, capítulos y comentarios tienen relaciones, estadísticas e historial.

## Decisión
No se borra físicamente: `deletedAt` en PostgreSQL y status DELETED en comentarios. Las FK usan `Restrict`.

## Alternativas descartadas
- **Borrado en cascada:** se perderían lecturas, favoritos e hilos de comentarios.

## Consecuencias
- ✅ Historial y estadísticas se conservan; se puede recuperar.
- ⚠️ Todas las consultas deben filtrar lo eliminado; la purga física queda pendiente.

Relacionado: [[Obra]] · [[Comentarios]] · Mapa: [[Decisiones - Mapa]]
