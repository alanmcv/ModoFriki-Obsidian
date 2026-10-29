---
tags: [ia/agentes]
---

# Agente db

**Rol:** Dueño de la persistencia.

| | |
|---|---|
| Archivos propios | `prisma/schema.prisma`, `prisma/migrations/**`, seed, `src/config/database/**`, `src/models/**`, `src/repositories/**`, tipos de dominio |
| Herramientas | Todas |
| Definido en | `.claude/agents/db.md` |

**Reglas principales**
- PostgreSQL como fuente de verdad, MongoDB solo para comunidad, Blob solo como referencias.
- Repositorios: única capa con Prisma o Mongoose; nunca devuelven `passwordHash`; mapean P2002 → 409 y P2025 → 404.
- Nunca edita `src/generated/`.

**Entrega:** Cambios de esquema, firmas exportadas de los repositorios (las que usará `dev`), seed y validaciones con resultado real.

Flujo: [[Flujo de una feature con agentes]] · Dueños: [[Propiedad de archivos por rol]] · Mapa: [[Desarrollo con IA - Mapa]]
