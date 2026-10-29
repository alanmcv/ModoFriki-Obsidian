---
tags: [capa/negocio]
---

# Impacto del negocio en la arquitectura

Qué hay que **agregar** a la arquitectura actual para que el modelo de negocio funcione.

| Necesidad | Cambio | Dónde |
|---|---|---|
| Planes Gratis / Friki+ | Módulo **Suscripciones**: tabla `Subscription` (userId, plan, estado, venceEn) | Backend + [[BD - Usuarios y roles]] |
| Cobros por QR y tarjeta | Módulo **Pagos**: adaptador a la pasarela + webhooks | Backend ([[Patrón Adapter]]) |
| Anuncios solo en plan gratis | Módulo **Anuncios** o proveedor externo; el front consulta el plan | Front + Backend |
| Acceso anticipado | Campo `earlyAccessUntil` en `Chapter`; el service filtra según el plan | [[Módulo Catálogo]] |
| Autores | Flujo de solicitud y aprobación; reutiliza EDITOR + asignación | [[Módulo Auth]] |
| Reparto mensual | Proceso programado que cuenta lecturas válidas por obra y genera pagos | [[Módulo Lectura]] + Pagos |
| Reporte para autores | Endpoint de ingresos por obra | Nuevo |
| Clasificación por edad | Campo en `Work` y filtro | [[Módulo Catálogo]] |

Con la [[Mejora - Backend organizado por módulos]], cada uno de estos sería un módulo nuevo sin tocar los existentes.

Mejoras técnicas: [[Mejoras - Mapa]] · Negocio: [[Negocio - Mapa]]
