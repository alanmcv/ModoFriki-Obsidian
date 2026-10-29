---
tags: [ia/flujo]
---

# Inconsistencias en la configuración de IA

Contradicciones encontradas al revisar los archivos de los agentes. Pueden hacer que la IA actúe mal.

| Dónde | Dice | Pero la regla vigente es |
|---|---|---|
| `.claude/agents/db.md` | Aplicar el esquema con `npx prisma db push` | `CLAUDE.md` prohíbe `db push`: solo migraciones SQL + `migrate deploy` |
| `guard-bash.mjs` | Al bloquear `migrate dev` sugiere "usa `npx prisma db push`" | Lo mismo: el hook recomienda un comando prohibido |
| `.claude/agents/db.md` | MongoDB solo para Comment; seed con 6 a 12 obras y admin `admin@modofriki.com` | Mongo guarda comentarios, votos y reportes; el seed crea solo el ADMIN acordado |
| `.claude/agents/media.md` | Archivos `upload.middleware.ts` y `blob.middleware.ts`, límite de 5 MB | Hoy es `src/middlewares/media/**` y el límite es 10 MiB |
| `.claude/agents/test.md` | "No existe `npm test`" | Existe Vitest con tests unitarios |
| `docs/agents/EVALUACION.md` | Habla de `.codex/agents/*.toml` y `.agents/skills/` | Esas carpetas ya no existen |
| Plugin `modofriki-guard` | Bloquea rutas que contienen `modofrikibackend` | La carpeta real es `ModoFriki-Backend` (con guion): **el bloqueo no se activa** |
| Skill `modofriki-frontend` | "Solo frontend, con mocks, sin panel admin" | El front consume la API y tiene `/admin` |

## Cómo se soluciona
Cada corrección, archivo por archivo y con el código exacto, está en [[Mejora - Corregir configuración de agentes]] (🟢 segura).

Relacionado: [[Mejora - Documentación desactualizada]] · Mapa: [[Desarrollo con IA - Mapa]]
