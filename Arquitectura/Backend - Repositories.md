---
tags: [capa/backend]
---

# Backend - Repositories

**Única capa** que usa `prisma` o Mongoose.

- Cliente inyectable (para poder usar mocks en los tests).
- Devuelve formas del contrato, nunca `passwordHash`.
- SQL crudo solo con *tagged template* o `Prisma.sql`, nunca `$queryRawUnsafe` (evita inyección SQL).
- Los contratos (interfaces) están en `src/types/<dominio>.types.ts`, por ejemplo `ReadingRepositoryContract`.

Archivos: `auth.repository`, `work/chapter/media/taxonomy.repository`, `comment/comment-vote/comment-report.repository`, `reading.repository`, `discovery.repository`.

Patrón: [[Patrón Repository]] · Bases: [[BD - Persistencia políglota]] · Capas: [[Backend - Arquitectura en capas]]
