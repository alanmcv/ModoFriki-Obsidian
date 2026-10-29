---
tags: [capa/transversal]
---

# Patrón Factory

**Qué es:** una función que fabrica objetos ya configurados.

**Dónde:**
- `createAuthRouter()`, `createCatalogRouter()`, `createReadingRouter()`… devuelven un `Router` con sus dependencias.
- `createAuthenticate(auth)` y `createOptionalAuthenticate(auth)` fabrican middlewares.
- `createLogger("ReadingService")` fabrica un logger con nombre.

**Por qué:** la app usa la instancia por defecto (`export default createXRouter()`) y los tests crean otra con mocks.

Capa: [[Backend - Routes]] · Relacionado: [[Inyección de dependencias]] · Índice: [[Patrones de diseño]]
