---
tags: [capa/transversal]
---

# Patrones de diseño

Patrones que **ya existen** en el código, con dónde y por qué.

| Patrón | Dónde | Por qué |
|---|---|---|
| [[Patrón Repository]] | `src/repositories/` | Aislar Prisma y Mongoose del negocio |
| [[Inyección de dependencias]] | Constructores de services y fábricas de routers | Poder probar con mocks |
| [[Patrón Factory]] | `createXRouter()`, `createAuthenticate()` | Crear objetos configurados con sus dependencias |
| [[Patrón Chain of Responsibility]] | Middlewares de Express y pipeline multimedia | Cada paso valida o corta la petición |
| [[Patrón Adapter]] | `toSeries`, `toChapter` en el front; `@prisma/adapter-pg` | Convertir un formato a otro |
| [[Patrón Observer]] | React Context y el evento `modofriki:unauthorized` | Avisar cambios a quien escucha |
| [[Concurrencia optimista]] | `expectedVersion`, `expectedRevision`, `expectedUpdatedAt` | Evitar que una edición pise a otra |
| [[Idempotencia]] | `idempotencyKey` en visitas y lecturas | Reintentar sin contar doble |

Principios: [[Principios SOLID]] · Mapa: [[Arquitectura - Mapa]]
