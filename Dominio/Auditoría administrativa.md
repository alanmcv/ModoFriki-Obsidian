---
tags: [dominio/usuarios]
---

# Auditoría administrativa

Registro de quién hizo qué en temas de permisos.

- Tabla `AdminAuditEvent`: actor, usuario afectado, obra, acción, rol anterior y nuevo, fecha.
- Acciones: ROLE_CHANGED, EDITOR_ASSIGNED, EDITOR_REVOKED.
- Sirve para revisar abusos y resolver disputas (útil cuando haya autores con ingresos → [[Programa de autores]]).

Implementación: [[BD - Usuarios y roles]] · Mapa: [[Dominio - Mapa]]
