---
tags: [capa/backend]
---

# Módulo Comunidad

Comentarios, votos y reportes (guardados en MongoDB).

| Método | Ruta | Quién |
|---|---|---|
| GET / POST | `/comments` | todos (Bearer opcional) / usuario |
| PATCH / DELETE | `/comments/:id` | autor (o ADMIN para borrar) |
| PUT / DELETE | `/comments/:id/vote` | usuario |
| POST | `/comments/:id/reports` | usuario |
| GET | `/comment-reports` | ADMIN |
| PATCH | `/comment-reports/:id` | ADMIN |

- Editar exige `expectedRevision`; si cambió, 409.
- El backend no interpreta HTML: el front debe sanitizar el Markdown.
- Los permisos se verifican en la ruta **y** en el service.

BD: [[BD - MongoDB comunidad]] · Front: [[Feature Ficha de obra]] · [[Feature Panel admin]]
Conceptos: [[Comentarios]] · [[Votos]] · [[Reportes y moderación]] · Capas: [[Backend - Arquitectura en capas]]
