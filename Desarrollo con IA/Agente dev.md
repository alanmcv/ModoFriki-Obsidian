---
tags: [ia/agentes]
---

# Agente dev

**Rol:** Implementa la API y la lógica de negocio.

| | |
|---|---|
| Archivos propios | `src/routes/**`, `src/controllers/**`, `src/services/**`, schemas Joi, middlewares de auth/rol/validación, `src/app.ts`, `openapi.yaml`, `package.json` |
| Herramientas | Todas |
| Definido en | `.claude/agents/dev.md` |

**Reglas principales**
- Sigue exactamente `docs/API.md`.
- Services con reglas de negocio y control de IDOR.
- Documenta cada endpoint en `openapi.yaml`.
- Si necesita algo de `db` o `media`, **no lo escribe**: lo reporta al dueño.
- Va siempre después de `db` y `media`.

**Entrega:** Endpoints, archivos, un `curl` real por endpoint, riesgos. Nunca dice que algo funciona sin ejecutarlo.

Flujo: [[Flujo de una feature con agentes]] · Dueños: [[Propiedad de archivos por rol]] · Mapa: [[Desarrollo con IA - Mapa]]
