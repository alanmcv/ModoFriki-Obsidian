---
tags: [capa/negocio]
---

# Métricas del negocio

| Métrica | Qué mide | De dónde sale |
|---|---|---|
| Lectores activos mensuales | Usuarios con al menos una lectura en el mes | `ChapterReadEvent` ✅ |
| Retención | % de lectores que vuelven la semana siguiente | `ChapterReadEvent` ✅ |
| Racha promedio | Hábito de lectura | `/me/reading-stats` ✅ |
| Lecturas por obra | Popularidad y base del reparto | `/works/:id/stats` ✅ |
| Autores activos | Autores con un capítulo publicado en el mes | `Chapter.publishedAt` ✅ |
| Conversión a Friki+ | % de lectores que pagan | Módulo Suscripciones 🆕 |
| Cancelaciones mensuales | % de Friki+ que se dan de baja | Módulo Suscripciones 🆕 |
| Ingreso promedio por autor | ¿Le conviene publicar aquí? | Módulo Pagos 🆕 |
| Costo de almacenamiento por lector | Eficiencia | Facturación de Blob |

Meta del primer año (supuesta): 30 autores activos, 5000 lectores activos y 3 % de conversión.

Conceptos: [[Visitas y lecturas]] · [[Rachas y calendario de lectura]] · Mapa: [[Negocio - Mapa]]
