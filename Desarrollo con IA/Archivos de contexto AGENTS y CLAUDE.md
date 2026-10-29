---
tags: [ia/contexto]
---

# Archivos de contexto AGENTS y CLAUDE

Archivos que la IA lee **antes** de tocar código.

**`AGENTS.md` (general, nació para Codex):**
- Contexto: backend existente, no regenerarlo.
- Arquitectura obligatoria por capas ([[Backend - Arquitectura en capas]]).
- Pipeline multimedia obligatorio ([[Backend - Pipeline multimedia]]).
- Persistencia: qué base es fuente de verdad, operaciones prohibidas.
- Git: nada directo a `main` ni `qa`.
- Contrato de entrega: objetivo, archivos, decisiones, validaciones reales, riesgos, rama y SHA.

**`CLAUDE.md` (solo Claude Code):** empieza con `@AGENTS.md` (lo incluye) y agrega comandos, tabla de capas, middlewares, roles con sus archivos propios, hooks y Git.

**Idea clave:** un archivo general compartido y uno específico por herramienta, para no repetir reglas.

Relacionado: [[Propiedad de archivos por rol]] · [[Vault como contexto para la IA]] · Mapa: [[Desarrollo con IA - Mapa]]
