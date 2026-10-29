---
tags: [decision]
estado: aceptada
fuente: docs/features/user-reading.md
---

# DEC-08 - Eventos idempotentes para visitas y lecturas

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** docs/features/user-reading.md

## Contexto
En celular la red falla y el front reintenta; las estadísticas no deben inflarse.

## Decisión
El front genera un UUID por operación y lo reutiliza en los reintentos; la base guarda la clave como única. Los GET no escriben nada: la visita y la lectura son POST aparte.

## Alternativas descartadas
- **Contar en el GET:** cada recarga o reintento sumaría.
- **Sin clave:** reintentos duplican conteos.

## Consecuencias
- ✅ Reintentos seguros.
- ⚠️ No impide crear claves nuevas a propósito → [[Mejora - Rate limiting y cabeceras de seguridad]].

Relacionado: [[Idempotencia]] · [[Visitas y lecturas]] · Mapa: [[Decisiones - Mapa]]
