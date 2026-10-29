---
tags: [ia/agentes]
---

# Agente planner

**Rol:** Planifica cada feature antes de implementarla.

| | |
|---|---|
| Archivos propios | Solo `docs/features/<feature>.md` |
| Herramientas | Read, Glob, Grep, Bash (solo lectura), Write |
| Definido en | `.claude/agents/planner.md` |

**Reglas principales**
- Lee AGENTS.md, CLAUDE.md y docs/API.md.
- Inspecciona el código real; no asume que algo existe.
- Escribe el plan con **todas** las secciones de la [[Plantilla de plan de feature]]: alcance, API, pipeline, persistencia, contratos compartidos, una tarea por rol, plan de pruebas e integración.
- Si hay una decisión estructural abierta, la anota y recomienda al [[Agente architect]].

**Entrega:** Ruta del plan, resumen de 5 líneas, roles que intervienen y decisiones abiertas.

Flujo: [[Flujo de una feature con agentes]] · Dueños: [[Propiedad de archivos por rol]] · Mapa: [[Desarrollo con IA - Mapa]]
