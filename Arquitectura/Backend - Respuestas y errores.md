---
tags: [capa/backend]
---

# Backend - Respuestas y errores

Formato único de respuesta (el "contrato" con el frontend, en `docs/API.md` y `openapi.yaml`).

- OK: `{ "success": true, "code": 200, "data": ... }`
- Error: `{ "success": false, "code": 4xx, "error": { "message": "..." } }`
- Paginado: `{ items, total, page, limit }` · Comunidad usa cursor: `{ items, hasMore, nextCursor }`

Errores:
- `AppError(message, statusCode)` para errores esperados.
- Cualquier otro error → 500 genérico, sin filtrar el mensaje interno.
- Códigos: 400 validación · 401 sesión · 403 permiso · 404 no existe u oculto · 409 conflicto/versión · 413 tamaño · 415 formato · 503 almacenamiento.

Documentación interactiva: `GET /api/docs` (Swagger UI).

El frontend traduce estos errores a español en [[Frontend - Cliente API]].
Capas: [[Backend - Arquitectura en capas]]
