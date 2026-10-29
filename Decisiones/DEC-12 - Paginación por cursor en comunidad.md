---
tags: [decision]
estado: aceptada
fuente: docs/API.md
---

# DEC-12 - Paginación por cursor en comunidad

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** docs/API.md

## Contexto
Los comentarios se agregan todo el tiempo mientras alguien los lee.

## Decisión
Comunidad pagina por cursor (`createdAt` + `id`); el catálogo y la biblioteca usan página y límite.

## Alternativas descartadas
- **Página y límite en comentarios:** al llegar comentarios nuevos se repiten o saltan elementos.

## Consecuencias
- ✅ Listas estables aunque cambien.
- ⚠️ Dos formatos de paginación que el front debe manejar.

Relacionado: [[Comentarios]] · [[BD - MongoDB comunidad]] · Mapa: [[Decisiones - Mapa]]
