---
tags: [ia/agentes]
---

# Propiedad de archivos por rol

En Claude Code los subagentes **comparten carpeta y rama**. Para que no se pisen, cada archivo tiene **un solo dueño**.

| Rol | Edita |
|---|---|
| [[Agente planner]] | `docs/features/<feature>.md` |
| [[Agente db]] | Prisma, migraciones, seed, config de BD, modelos, repositorios, tipos |
| [[Agente media]] | `src/middlewares/media/**`, `media-paths.ts` |
| [[Agente dev]] | routes, controllers, services, schemas, middlewares de auth/rol/validación, `app.ts`, `openapi.yaml`, `package.json` |
| Coordinador | tests unitarios, `vitest.config.ts`, `docs/**`, `CLAUDE.md` |
| [[Agente architect]], [[Agente test]], [[Agente reviewer]], [[Agente security]] | Nada |

- Los hallazgos vuelven **al dueño del archivo**, nunca a otro rol.
- Los roles que editan se ejecutan **en serie**; los que solo leen pueden ir **en paralelo**.
- Con Codex, el aislamiento real era con **worktrees** separados.

Decisión: [[DEC-15 - Subagentes con archivos propios]] · Mapa: [[Desarrollo con IA - Mapa]]
