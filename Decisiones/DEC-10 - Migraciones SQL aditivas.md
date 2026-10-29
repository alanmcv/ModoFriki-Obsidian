---
tags: [decision]
estado: aceptada
fuente: CLAUDE.md y prisma/README.md
---

# DEC-10 - Migraciones SQL aditivas

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** CLAUDE.md y prisma/README.md

## Contexto
La base de Render es compartida y no tiene *shadow database*.

## Decisión
Migraciones SQL escritas a mano o con `prisma migrate diff`, solo aditivas, aplicadas con `migrate deploy`. Prohibido `migrate dev`, `reset` y `db push`.

## Alternativas descartadas
- **`migrate dev`:** necesita shadow DB y puede resetear.
- **`db push`:** no deja historial y puede perder datos.

## Consecuencias
- ✅ Cambios reproducibles y seguros.
- ⚠️ Más trabajo manual; algunos agentes aún sugieren `db push` → [[Inconsistencias en la configuración de IA]].

Relacionado: [[BD - Migraciones]] · [[Hooks de Claude Code]] · Mapa: [[Decisiones - Mapa]]
