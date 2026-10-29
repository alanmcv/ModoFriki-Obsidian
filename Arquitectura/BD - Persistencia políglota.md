---
tags: [capa/bd]
---

# BD - Persistencia políglota

ModoFriki usa **tres almacenamientos**, cada uno para lo que hace mejor ("persistencia políglota").

| Almacenamiento | Guarda | Por qué |
|---|---|---|
| **PostgreSQL** (Prisma) | Usuarios, roles, catálogo, capítulos, orden de páginas, referencias de imágenes, favoritos, valoraciones, lecturas y visitas | Fuente de verdad. Relaciones con llaves foráneas y transacciones |
| **MongoDB** (Mongoose) | Comentarios, votos y reportes | Un documento por comentario permite respuestas a cualquier profundidad sin arrays que crezcan sin límite |
| **Vercel Blob** | Bytes de portadas, banners y páginas | Las bases solo guardan URL y metadatos, nunca buffers |

- Tablas de PostgreSQL: [[BD - Usuarios y roles]] · [[BD - Catálogo]] · [[BD - Multimedia]] · [[BD - Lectura y biblioteca]]
- Colecciones de MongoDB: [[BD - MongoDB comunidad]]
- Archivos: [[BD - Vercel Blob]]
- Cambios de esquema: [[BD - Migraciones]]

**Ojo:** no hay transacción distribuida entre PostgreSQL, MongoDB y Blob. La identidad del autor de un comentario se consulta en PostgreSQL; si falla una subida a Blob después de guardar, se compensa (ver [[Backend - Pipeline multimedia]]).

Acceso a datos: [[Patrón Repository]] · Mapa: [[Arquitectura - Mapa]]
