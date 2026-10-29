---
tags: [capa/backend]
---

# Módulo Catálogo

Obras, capítulos, páginas, tipos y géneros.

| Método | Ruta | Quién |
|---|---|---|
| GET / POST | `/works` | todos / ADMIN |
| GET / PUT / PATCH / DELETE | `/works/:workId` | todos / ADMIN o EDITOR asignado |
| GET / POST | `/works/:workId/chapters` | todos / ADMIN o EDITOR asignado |
| GET / PUT / PATCH / DELETE | `/works/:workId/chapters/:chapterId` | ídem |
| PUT / POST / PATCH | `/works/:workId/chapters/:chapterId/pages` | reemplazar / insertar / reordenar |
| GET / POST | `/work-types`, `/genres` | todos / ADMIN |

- Sin sesión solo se ve lo PUBLISHED; con `includeDrafts=true` el personal ve borradores.
- Ediciones con `expectedUpdatedAt` (obra) o `expectedVersion` (capítulo).
- Es el módulo más complejo por el [[Backend - Pipeline multimedia]].

BD: [[BD - Catálogo]] · [[BD - Multimedia]] · Front: [[Feature Catálogo]] · [[Feature Panel admin]] · [[Feature Lector]]
Conceptos: [[Obra]] · [[Capítulo]] · [[Flujo de publicación]] · Patrón: [[Concurrencia optimista]]
Capas: [[Backend - Arquitectura en capas]]
