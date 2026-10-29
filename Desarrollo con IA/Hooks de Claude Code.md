---
tags: [ia/flujo]
---

# Hooks de Claude Code

Scripts en `.claude/hooks/` que se ejecutan **antes o después** de cada herramienta (`.claude/settings.json`). Hacen **cumplir** reglas que las instrucciones solo piden.

| Cuándo | Script | Qué hace |
|---|---|---|
| Antes de Edit/Write | `check.mjs` | Bloquea `.env*` (excepto `.env.example`) y `src/generated/**` |
| Antes de Bash/PowerShell | `guard-bash.mjs` | Bloquea `migrate reset/dev`, `--accept-data-loss`, DROP/TRUNCATE, borrados masivos, `push --force`, `reset --hard`, push a `main`/`qa` y commit estando en `main`/`qa` |
| Después de Edit/Write | `check.mjs` | `tsc --noEmit` tras editar `.ts`; `prisma validate` + `generate` tras editar el esquema |

Responden con `permissionDecision: "deny"` y un motivo, así la IA sabe por qué se bloqueó.

Ver contradicción en [[Inconsistencias en la configuración de IA]] · Relacionado: [[BD - Migraciones]] · [[Seguridad]] · Mapa: [[Desarrollo con IA - Mapa]]
