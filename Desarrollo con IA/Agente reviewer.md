---
tags: [ia/agentes]
---

# Agente reviewer

**Rol:** Revisión independiente del diff antes de cada commit.

| | |
|---|---|
| Archivos propios | Ninguno (no corrige) |
| Herramientas | Read, Glob, Grep, Bash |
| Definido en | `.claude/agents/reviewer.md` |

**Reglas principales**
Revisa en orden: contrato → correctitud (500 inesperados, N+1, paginación sin límite) → arquitectura (Prisma fuera de repositorios, lógica en controllers) → propiedad de archivos. Separa evidencia de hipótesis y cita archivo:línea.

**Entrega:** Hallazgos por impacto (CRÍTICA, ALTA, MEDIA…) que vuelven al dueño del archivo.

Flujo: [[Flujo de una feature con agentes]] · Dueños: [[Propiedad de archivos por rol]] · Mapa: [[Desarrollo con IA - Mapa]]
