---
tags: [capa/bd]
---

# BD - Lectura y biblioteca

Tablas de PostgreSQL para la actividad del lector.

| Tabla | Para qué | Restricción clave |
|---|---|---|
| `Favorite` | Obras favoritas del usuario | Único (userId, workId) |
| `WorkRating` | Valoración 0 a 5 en medias estrellas (`scoreHalfStars`) | Único (userId, workId) |
| `UserChapterRead` | Estado actual "leído" de un capítulo | Único (userId, chapterId) |
| `ChapterReadEvent` | Cada apertura de capítulo (también anónima), con `localDate` y zona horaria | `idempotencyKey` único |
| `ChapterReadReceipt` | Guarda cada clave de operación y la apunta al evento del día | PK = idempotencyKey |
| `WorkVisitEvent` | Cada visita a la ficha de una obra | `idempotencyKey` único |

- `Work.visitsCount` es un contador desnormalizado para ordenar rápido por popularidad.
- Desmarcar un capítulo cambia `UserChapterRead`, pero **no borra** los eventos.

Módulos: [[Módulo Lectura]] · [[Módulo Descubrimiento]] · Patrón: [[Idempotencia]]
Conceptos: [[Visitas y lecturas]] · [[Biblioteca personal]] · [[Valoraciones]] · [[Rachas y calendario de lectura]]
Mapa: [[BD - Persistencia políglota]]
