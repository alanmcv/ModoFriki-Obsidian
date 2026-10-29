---
tags: [capa/bd]
---

# BD - Migraciones

Cómo cambia el esquema de PostgreSQL.

- Migraciones **SQL aditivas** en `prisma/migrations/` (hoy: `core_domain`, `chapter_read_receipts`, `work_visits_count`).
- Se aplican con `npx prisma migrate deploy` (también al arrancar en Render con `npm start`).
- **Prohibido:** `migrate dev`, `migrate reset`, `db push`, `DROP`, `TRUNCATE`. Render no tiene *shadow DB* y la base es compartida.
- Para probar sin tocar la base compartida: PostgreSQL desechable en Docker.
- `npx prisma db seed` crea solo el usuario ADMIN.
- Un *hook* de Claude bloquea los comandos prohibidos → [[Desarrollo con IA - Mapa]].

MongoDB no usa migraciones: los esquemas viven en los modelos Mongoose ([[BD - MongoDB comunidad]]).

Mapa: [[BD - Persistencia políglota]]
