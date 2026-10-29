---
tags: [decision]
estado: aceptada
fuente: AGENTS.md
---

# DEC-01 - Monolito en capas

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** AGENTS.md

## Contexto
Equipo pequeño, MVP con fecha y un solo despliegue en Render.

## Decisión
Una sola aplicación Express dividida en routes → controllers → services → repositories, por dominio.

## Alternativas descartadas
- **Microservicios:** demasiada infraestructura para un MVP.
- **Hexagonal completa:** más carpetas e interfaces sin necesidad todavía.

## Consecuencias
- ✅ Simple de entender, desplegar y probar.
- ⚠️ Carpetas por capa: un cambio de dominio toca muchas carpetas → [[Mejora - Backend organizado por módulos]].

Relacionado: [[Backend - Arquitectura en capas]] · Mapa: [[Decisiones - Mapa]]
