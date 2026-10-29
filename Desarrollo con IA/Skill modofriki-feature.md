---
tags: [ia/flujo]
---

# Skill modofriki-feature

Comando `/modofriki-feature <feature>` de Claude Code (`.claude/skills/modofriki-feature/SKILL.md`). Convierte el [[Flujo de una feature con agentes]] en pasos que el coordinador sigue solo:

1. Auditoría con `git status` (si hay cambios ajenos, se detiene y pregunta).
2. Plan con el planner; architect solo si hay decisión estructural.
3. Rama `feat/<feature>` desde `dev`.
4. `db` → `media` → `dev`, solo los que el plan necesita.
5. `test`; si el servidor no responde, lo levanta.
6. `reviewer` + `security`; máximo 2 rondas.
7. `tsc --noEmit` y `build`; reporte; con **OK del usuario**: commit, merge `--no-ff` a `dev` y push de `dev`.

Mapa: [[Desarrollo con IA - Mapa]]
