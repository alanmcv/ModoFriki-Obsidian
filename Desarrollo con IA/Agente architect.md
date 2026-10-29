---
tags: [ia/agentes]
---

# Agente architect

**Rol:** Consultor de decisiones estructurales. Solo cuando el planner o el usuario marcan una decisión abierta.

| | |
|---|---|
| Archivos propios | Ninguno (no edita) |
| Herramientas | Read, Glob, Grep |
| Definido en | `.claude/agents/architect.md` |

**Reglas principales**
- Propone 2 o 3 alternativas que encajen en las capas actuales.
- Prefiere cambios incrementales; evita reescrituras y abstracciones sin evidencia.
- Para cada una: impacto en el contrato, archivos y roles afectados, riesgo y esfuerzo.
- Si la mejor opción cambia el contrato, decide el usuario.

**Entrega:** Recomendación en 2 líneas + tabla alternativa | pros | contras | esfuerzo. Sus respuestas alimentan las [[Decisiones - Mapa|decisiones]].

Flujo: [[Flujo de una feature con agentes]] · Dueños: [[Propiedad de archivos por rol]] · Mapa: [[Desarrollo con IA - Mapa]]
