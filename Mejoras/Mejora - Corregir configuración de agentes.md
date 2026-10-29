---
tags: [capa/mejora]
---

# Mejora - Corregir configuración de agentes

**Categoría:** 🟢 Segura (solo cambia textos e instrucciones; no toca el código de la app)

Corrige las contradicciones de [[Inconsistencias en la configuración de IA]].

## 1. `db push` recomendado aunque está prohibido (backend)
Regla vigente (`CLAUDE.md`): migraciones SQL aditivas en `prisma/migrations/`, aplicadas con `npx prisma migrate deploy`. **Nunca** `db push`.

| Archivo | Línea actual | Cambiar por |
|---|---|---|
| `.claude/agents/db.md` (description) | "prisma/schema.prisma, db push, seed…" | "prisma/schema.prisma, migraciones SQL, seed…" |
| `.claude/agents/db.md` (regla "Aplicar el schema") | "Aplícalo con `npx prisma db push`." | "Escribe una migración SQL aditiva en `prisma/migrations/` (a mano o con `npx prisma migrate diff`) y aplícala con `npx prisma migrate deploy`. Nunca `db push`." |
| `.claude/agents/db.md` (Entrega) | "si se aplicó `db push`" | "qué migración se creó y si se aplicó con `migrate deploy`" |
| `.claude/hooks/guard-bash.mjs` (regla de `migrate dev`) | "usa `npx prisma db push` para aplicar el schema." | "escribe una migración SQL aditiva y aplícala con `npx prisma migrate deploy`." |
| `.claude/skills/modofriki-feature/SKILL.md` (pasos 1 y 4) | "`schema` (schema completo + `db push` + seed)" y "`db`: schema, `db push`, seed…" | "migración SQL + `migrate deploy`" |

Además, que el hook **bloquee** `db push`, agregando esta regla a `RULES` en `guard-bash.mjs`:
```js
[/prisma\s+db\s+push/, "CLAUDE.md prohíbe `db push`: usa una migración SQL aditiva y `npx prisma migrate deploy`."],
```

## 2. El plugin de OpenCode no protege el backend (frontend)
En `.opencode/plugins/modofriki-guard.ts`, la ruta se pasa a minúsculas (`modofriki-backend`), pero se compara con `modofrikibackend` (sin guion), así que nunca coincide.

```ts
// antes
if (path.includes("modofrikibackend")) {
// después: acepta con o sin guion
if (/modofriki-?backend/.test(path)) {
```
También se puede borrar la constante `BLOCKED_PATHS`, que no se usa.

## 3. Datos viejos en los agentes
| Archivo | Corregir |
|---|---|
| `.claude/agents/db.md` | Mongo guarda comentarios, **votos y reportes**; el seed crea **solo el ADMIN** |
| `.claude/agents/media.md` | Archivos propios: `src/middlewares/media/**` y `src/utils/media-paths.ts`; límite **10 MiB** |
| `.claude/agents/test.md` | Quitar "No existe `npm test`": hay Vitest |
| `docs/agents/EVALUACION.md` | Nota al inicio: describe la configuración anterior con Codex (`.codex/`, `.agents/`) |
| Skill `modofriki-frontend` | Quitar "solo frontend, con mocks, sin panel admin" |

## Cómo comprobarlo
- Backend: pedirle a Claude Code `npx prisma db push` → el hook debe bloquearlo con el mensaje nuevo.
- Frontend: pedirle a OpenCode que edite un archivo de `ModoFriki-Backend` → el plugin debe bloquearlo.

Relacionado: [[Mejora - Documentación desactualizada]] · [[Hooks de Claude Code]] · [[Skills y plugin de OpenCode]] · [[DEC-10 - Migraciones SQL aditivas]]
Índice: [[Mejoras - Mapa]]
