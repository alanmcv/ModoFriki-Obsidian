---
tags: [capa/backend]
---

# Backend - Middlewares

Funciones que se ejecutan en cadena antes del controller.

| Middleware | Qué hace |
|---|---|
| `loggerMiddleware` | Registra cada petición (winston) |
| `cors` | Solo permite `http://localhost:5173` y `FRONTEND_URL` |
| `createAuthenticate(auth)` | Lee `Bearer <JWT>`, valida y deja el usuario en `res.locals.user`. Sin token → 401 |
| `createOptionalAuthenticate(auth)` | Igual, pero sin token sigue como anónimo |
| `authorize(["ADMIN"])` | 401 sin usuario, 403 sin rol |
| `validateBody / validateParams / validateQuery` | Joi con `abortEarly: false`; 400 con todos los errores |
| `catalog.middleware` | Params, body, verificación previa y errores del catálogo |
| `media/*` | [[Backend - Pipeline multimedia]] |
| `errorHandler` (4 parámetros) | Convierte cualquier error en JSON. Sin él, Express devolvería HTML con el stack |

Patrón: [[Patrón Chain of Responsibility]] · Seguridad: [[Seguridad]]
Capas: [[Backend - Arquitectura en capas]]
