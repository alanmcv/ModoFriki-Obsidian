---
tags: [dominio/lectura]
---

# Visitas y lecturas

Dos eventos distintos:

| Evento | Cuándo | Ruta |
|---|---|---|
| **Visita** | Al abrir la ficha de una obra | `POST /works/:id/visits` |
| **Lectura** | Al entrar a un capítulo | `POST /chapters/:id/read-events` |

**Reglas:**
- Los GET no cuentan nada; el front envía el POST.
- Cada operación lleva un UUID (`idempotencyKey`); repetirlo no suma de nuevo → [[Idempotencia]].
- Las lecturas anónimas cuentan para estadísticas públicas, pero no son personas únicas verificadas.
- Con sesión, la lectura además marca el capítulo como leído.
- Para usuarios registrados, solo **una lectura por capítulo y día local** cuenta para estadísticas y rachas.
- Estadísticas públicas de una obra: visitas, visitas 24 h, lecturas, lecturas 24 h, favoritos, valoraciones y promedio.

Son la base de las [[Métricas del negocio]] y del reparto a autores ([[Programa de autores]]).

Implementación: [[BD - Lectura y biblioteca]] · [[Módulo Lectura]] · Flujo: [[Flujo de lectura]] · Mapa: [[Dominio - Mapa]]
