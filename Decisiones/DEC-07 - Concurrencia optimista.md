---
tags: [decision]
estado: aceptada
fuente: docs/API.md (Catálogo implementado)
---

# DEC-07 - Concurrencia optimista

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** docs/API.md (Catálogo implementado)

## Contexto
Varios editores pueden editar la misma obra o capítulo al mismo tiempo.

## Decisión
Cada edición envía la versión que vio (`expectedUpdatedAt`, `expectedVersion`, `expectedRevision`); si cambió, 409.

## Alternativas descartadas
- **Bloquear el registro mientras se edita:** complejo y deja bloqueos colgados.
- **El último gana:** se pierden cambios sin aviso.

## Consecuencias
- ✅ Nadie pisa el trabajo de otro sin saberlo.
- ⚠️ El front debe recargar tras cada edición.

Relacionado: [[Concurrencia optimista]] · Mapa: [[Decisiones - Mapa]]
