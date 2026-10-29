---
tags: [capa/transversal]
---

# Inyección de dependencias

**Qué es:** en vez de que una clase cree lo que necesita, se lo pasan desde afuera.

**Dónde:**
- Services: el repositorio llega por constructor con un valor por defecto.
- Routers: `createCatalogRouter(service = catalogService, auth = authService)`.
- Middlewares: `createAuthenticate(auth)`.

**Por qué:** los tests de Vitest pasan versiones falsas y prueban la lógica sin base de datos ni red.

Es manual (sin contenedor como InversifyJS o NestJS): simple y suficiente para este tamaño.

Principio: [[Principios SOLID]] (D) · Relacionado: [[Patrón Factory]] · Índice: [[Patrones de diseño]]
