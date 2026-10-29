---
tags: [capa/bd]
---

# BD - MongoDB comunidad

Colecciones de MongoDB (modelos Mongoose en `src/models/community/`).

| Colección | Campos importantes |
|---|---|
| `comments` | id UUID, authorId, targetType (WORK / CHAPTER), targetId, parentCommentId, rootCommentId, bodyMarkdown (≤ 10 000), status ACTIVE/DELETED, revision, editedAt, deletedAt |
| `commentvotes` | commentId, userId, value (-1 o 1). Un voto por usuario y comentario |
| `commentreports` | commentId, reporterId, reason (SPAM, HARASSMENT, HATE, SPOILER, OTHER), details, status (OPEN, IN_REVIEW, RESOLVED, DISMISSED), resolution |

- **Un documento por comentario** con referencia al padre y a la raíz: permite hilos de cualquier profundidad.
- Paginación por **cursor** (createdAt + id), no por página.
- Los IDs son UUID en texto (igual que en PostgreSQL), no ObjectId.
- Las transacciones necesitan que MongoDB esté en *replica set*.

Módulo: [[Módulo Comunidad]] · Conceptos: [[Comentarios]] · [[Votos]] · [[Reportes y moderación]]
Mapa: [[BD - Persistencia políglota]]
