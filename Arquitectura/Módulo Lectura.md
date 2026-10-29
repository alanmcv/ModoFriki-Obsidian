---
tags: [capa/backend]
---

# Módulo Lectura

Visitas, lecturas, favoritos, valoraciones e historial.

| Método | Ruta | Auth |
|---|---|---|
| POST | `/works/:workId/visits` | opcional |
| GET | `/works/:workId/stats` | pública |
| PUT / DELETE | `/works/:workId/rating` | usuario |
| POST | `/chapters/:chapterId/read-events` | opcional |
| PUT / DELETE | `/me/read-chapters/:chapterId` | usuario |
| GET | `/me/favorites` · PUT/DELETE `/me/favorites/:workId` | usuario |
| GET | `/me/reading-history`, `/me/reading-stats`, `/me/reading-calendar`, `/me/works/:workId/progress` | usuario |

- El `userId` sale siempre del token, nunca del cliente.
- Visitas y lecturas usan `idempotencyKey` (UUID que genera el front).
- Rachas y calendario en la zona horaria del usuario.

BD: [[BD - Lectura y biblioteca]] · Front: [[Feature Lector]] · [[Feature Biblioteca y perfil]]
Conceptos: [[Visitas y lecturas]] · [[Biblioteca personal]] · [[Valoraciones]] · [[Rachas y calendario de lectura]] · [[Flujo de lectura]]
Patrón: [[Idempotencia]] · Capas: [[Backend - Arquitectura en capas]]
