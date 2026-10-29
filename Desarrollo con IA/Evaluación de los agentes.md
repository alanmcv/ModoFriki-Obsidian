---
tags: [ia/flujo]
---

# Evaluación de los agentes

`docs/agents/EVALUACION.md` (19/10/2026): revisión **estática** de las instrucciones de los 8 roles, sin ejecutarlos.

Conclusiones:
- Los roles cubren el desarrollo; no hace falta un agente documentador ni depurador.
- `planner` y `reviewer` están bien separados de la implementación.
- `db` y `dev` debían acordar quién es dueño de los repositorios (después se resolvió: `db`).
- Los subagentes de una sesión comparten rama: dividir archivos no basta para commits simultáneos; para eso, worktrees.
- La regla de solo lectura del reviewer es una instrucción, no un sandbox.
- Compilar no demuestra que se probaron las reglas de negocio.

Mapa: [[Desarrollo con IA - Mapa]]
