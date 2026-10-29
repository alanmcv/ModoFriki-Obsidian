---
tags: [ia/agentes]
---

# Agente security

**Rol:** Auditoría de seguridad de solo lectura, en paralelo con reviewer cuando la feature toca auth, permisos, uploads o datos de usuarios.

| | |
|---|---|
| Archivos propios | Ninguno |
| Herramientas | Read, Glob, Grep, Bash |
| Definido en | `.claude/agents/security.md` |

**Reglas principales**
Audita JWT, autorización e IDOR, *mass assignment* (`role` o `userId` en el body), entradas sin validar, uploads, secretos en logs y abuso (fuerza bruta, CORS abierto). Solo pruebas no destructivas.

**Entrega:** Hallazgos de seguridad sin repetir los del reviewer.

Flujo: [[Flujo de una feature con agentes]] · Dueños: [[Propiedad de archivos por rol]] · Mapa: [[Desarrollo con IA - Mapa]]
