---
tags: [decision]
estado: aceptada
fuente: CLAUDE.md del backend
---

# DEC-15 - Subagentes con archivos propios

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** CLAUDE.md del backend

## Contexto
En Claude Code los subagentes comparten carpeta y rama; con Codex se usaban worktrees.

## Decisión
Cada rol tiene archivos propios disjuntos; los que editan van en serie y los hallazgos vuelven al dueño.

## Alternativas descartadas
- **Worktrees por agente:** aislamiento real, pero más complejo dentro de una sesión de Claude.
- **Sin dueños:** los agentes se pisan.

## Consecuencias
- ✅ Sin conflictos entre agentes.
- ⚠️ Reorganizar carpetas obliga a rehacer la tabla de dueños.

Relacionado: [[Propiedad de archivos por rol]] · [[Flujo de una feature con agentes]] · Mapa: [[Decisiones - Mapa]]
