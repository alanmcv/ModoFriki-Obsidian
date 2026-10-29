---
tags: [decision]
estado: aceptada
fuente: docs/features/community.md
---

# DEC-03 - MongoDB para la comunidad

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** docs/features/community.md

## Contexto
Los comentarios tienen respuestas a cualquier profundidad, votos y reportes.

## Decisión
Comentarios, votos y reportes en MongoDB, **un documento por comentario** con referencia al padre y a la raíz.

## Alternativas descartadas
- **Comentarios en PostgreSQL:** posible, pero los árboles profundos son más incómodos de consultar.
- **Respuestas como array dentro del comentario:** el documento crecería sin límite.

## Consecuencias
- ✅ Hilos flexibles y paginación por cursor.
- ⚠️ No hay transacción entre Mongo y PostgreSQL; la identidad del autor se consulta en PostgreSQL.
- ⚠️ Dos bases que operar.

Relacionado: [[BD - MongoDB comunidad]] · [[DEC-12 - Paginación por cursor en comunidad]] · Mapa: [[Decisiones - Mapa]]
