---
tags: [capa/transversal]
---

# Patrón Chain of Responsibility

**Qué es:** la petición pasa por una cadena de manejadores; cada uno hace su parte y decide si sigue (`next()`) o corta con un error.

**Dónde:**
- Cadena global: logger → CORS → JSON → router → 404 → errorHandler.
- Cadena por ruta: `authenticate → authorize → validar → controller`.
- [[Backend - Pipeline multimedia]]: auth → preflight → Multer → validación → Blob → controller → borrar reemplazados.

**Por qué:** cada paso es pequeño, reutilizable y se puede probar solo.

Capa: [[Backend - Middlewares]] · Índice: [[Patrones de diseño]]
