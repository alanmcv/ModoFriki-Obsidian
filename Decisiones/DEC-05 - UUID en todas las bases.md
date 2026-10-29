---
tags: [decision]
estado: aceptada
fuente: prisma/schema.prisma y modelos Mongoose
---

# DEC-05 - UUID en todas las bases

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** prisma/schema.prisma y modelos Mongoose

## Contexto
Hay datos en PostgreSQL y MongoDB que se referencian entre sí.

## Decisión
Todos los IDs son UUID en texto, también en MongoDB (no ObjectId).

## Alternativas descartadas
- **Enteros autoincrementales:** se pueden adivinar y no sirven entre bases.
- **ObjectId en Mongo:** dos formatos distintos para el front.

## Consecuencias
- ✅ Un solo formato para validar y referenciar.
- ✅ No revela cuántos registros hay.

Relacionado: [[BD - Persistencia políglota]] · Mapa: [[Decisiones - Mapa]]
