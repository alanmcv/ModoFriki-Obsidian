---
tags: [capa/backend]
---

# Módulo Descubrimiento

Novedades, rankings y recomendaciones (solo lectura).

| Método | Ruta | Query |
|---|---|---|
| GET | `/chapters/latest` | page, limit (≤ 50), typeId |
| GET | `/works/popular` | period = all \| day, page, limit, typeId |
| GET | `/works/recommended` | limit (Bearer opcional) |

- **Popular:** ordena por visitas (desde siempre o últimas 24 h).
- **Recomendado:** con sesión, usa los géneros de tus favoritos y excluye los que ya tienes (`basis: "genres"`); sin sesión o sin favoritos, cae a popular (`basis: "popular"`).

BD: [[BD - Lectura y biblioteca]] · [[BD - Catálogo]] · Front: [[Feature Inicio]] · [[Feature Catálogo]]
Conceptos: [[Rankings y recomendaciones]] · Capas: [[Backend - Arquitectura en capas]]
