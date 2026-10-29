---
tags: [decision]
estado: aceptada
fuente: docs/features/MODELO_DATOS_PROPUESTO.md
---

# DEC-02 - PostgreSQL como fuente de verdad

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** docs/features/MODELO_DATOS_PROPUESTO.md

## Contexto
Usuarios, obras, capítulos, favoritos y lecturas tienen muchas relaciones y reglas de unicidad.

## Decisión
PostgreSQL (con Prisma) es la fuente de verdad de identidad, catálogo, biblioteca y actividad, con llaves foráneas y transacciones.

## Alternativas descartadas
- **Todo en MongoDB** (como TankoBase): se pierden FK y transacciones entre usuario, obra y capítulo.

## Consecuencias
- ✅ Integridad garantizada por la base (únicos, FK con `Restrict`).
- ⚠️ Hay que mantener migraciones ([[DEC-10 - Migraciones SQL aditivas]]).

Relacionado: [[BD - Persistencia políglota]] · [[DEC-03 - MongoDB para la comunidad]] · Mapa: [[Decisiones - Mapa]]
