---
tags: [capa/bd]
---

# BD - Usuarios y roles

Tablas de PostgreSQL para identidad y permisos.

| Tabla | Campos importantes | Notas |
|---|---|---|
| `User` | id (UUID), email, emailNormalized (único), username, usernameNormalized (único), passwordHash, role, status, timezone | role: BASIC / EDITOR / ADMIN. status: ACTIVE / SUSPENDED / DELETED. timezone por defecto `America/La_Paz` |
| `WorkEditorAssignment` | workId, editorId, assignedById, assignedAt, revokedAt | Qué editor puede tocar qué obra. Único por (workId, editorId) |
| `AdminAuditEvent` | actorId, subjectUserId, workId, action, previousRole, newRole | Bitácora: ROLE_CHANGED, EDITOR_ASSIGNED, EDITOR_REVOKED |

- Email y username se comparan normalizados (trim + minúsculas) para evitar duplicados.
- Nunca se devuelve `passwordHash` al cliente.

Módulo: [[Módulo Auth]] · Conceptos: [[Roles y permisos]] · [[Asignación de editores]] · [[Auditoría administrativa]]
Mapa: [[BD - Persistencia políglota]]
