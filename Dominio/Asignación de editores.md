---
tags: [dominio/usuarios]
---

# Asignación de editores

Un EDITOR solo puede trabajar en las obras que un ADMIN le asignó.

- Tabla `WorkEditorAssignment` con `assignedAt` y `revokedAt` (revocar no borra el registro).
- Única por (obra, editor).
- Si el editor intenta editar otra obra: "Esta obra no está asignada a tu cuenta de editor".
- Cada asignación o revocación queda en la [[Auditoría administrativa]].

Implementación: [[BD - Usuarios y roles]] · Relacionado: [[Roles y permisos]] · [[Flujo de publicación]]
Mapa: [[Dominio - Mapa]]
