---
tags: [capa/negocio]
---

# Planes de suscripción

Planes para **lectores**. ✅ = ya existe en el código · 🆕 = hay que construirlo.

| Funcionalidad | Gratis (Bs 0) | Friki+ (Bs 25/mes o Bs 240/año) | Módulo que la habilita |
|---|---|---|---|
| Leer todas las obras publicadas | ✅ | ✅ | [[Módulo Catálogo]] ✅ |
| Favoritos, historial y progreso | ✅ | ✅ | [[Módulo Lectura]] ✅ |
| Rachas, calendario y estadísticas | ✅ | ✅ | [[Módulo Lectura]] ✅ |
| Comentar, votar y reportar | ✅ | ✅ | [[Módulo Comunidad]] ✅ |
| Recomendaciones por género | ✅ | ✅ | [[Módulo Descubrimiento]] ✅ |
| Anuncios | Sí | **No** | Módulo Anuncios 🆕 |
| Acceso anticipado (capítulos 7 días antes) | — | ✅ | [[Módulo Catálogo]] + Módulo Suscripciones 🆕 |
| Insignia Friki+ en comentarios | — | ✅ | [[Módulo Comunidad]] + Módulo Suscripciones 🆕 |
| Apoyar a autores con un monto | ✅ | ✅ | Módulo Pagos 🆕 |

Idea clave: **todo lo que ya existe queda gratis** para atraer lectores; se paga por comodidad (sin anuncios) y exclusividad (acceso anticipado), no por leer.

**Nota técnica:** el plan del usuario se guardaría en PostgreSQL (tabla `Subscription`) y el acceso anticipado con un campo nuevo en `Chapter` → [[Impacto del negocio en la arquitectura]].

> Precios supuestos: [[Validación de supuestos]]

Autores: [[Programa de autores]] · Ingresos: [[Fuentes de ingresos]] · Mapa: [[Negocio - Mapa]]
