---
tags: [capa/backend]
---

# Backend - Routes

Definen los endpoints y el **orden de los middlewares**. No tienen lógica de negocio.

Convención: cada archivo exporta una fábrica con dependencias por parámetro y una instancia por defecto.
```ts
export function createReadingRouter(service = readingService, auth = authService): Router { ... }
export default createReadingRouter();
```
- Se montan en `src/app.ts` con `app.use("/api", router)`.
- Las rutas literales (`/works/popular`) se montan **antes** que `/works/:workId` para que no las capture el parámetro.
- Orden típico: `authenticate → authorize → validar → controller`.

Patrones: [[Patrón Factory]] · [[Inyección de dependencias]] · [[Patrón Chain of Responsibility]]
Capas: [[Backend - Arquitectura en capas]]
