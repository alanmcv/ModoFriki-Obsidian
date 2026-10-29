---
tags: [ia/agentes]
---

# Agente test

**Rol:** Verifica con peticiones reales (curl) que la API cumple el contrato.

| | |
|---|---|
| Archivos propios | Ninguno |
| Herramientas | Read, Glob, Grep, Bash |
| Definido en | `.claude/agents/test.md` |

**Reglas principales**
- Caso feliz y negativos: 400, 401, 403, 404, 409 e IDOR.
- Que `passwordHash` nunca aparezca.
- Uploads: imagen válida, archivo falso con `.jpg`, archivo enorme.
- No borra datos que no creó (la base es compartida).

**Entrega:** Tabla endpoint | caso | esperado | real | ✅/❌; cada ❌ va a su dueño (`db`, `media` o `dev`).

Flujo: [[Flujo de una feature con agentes]] · Dueños: [[Propiedad de archivos por rol]] · Mapa: [[Desarrollo con IA - Mapa]]
