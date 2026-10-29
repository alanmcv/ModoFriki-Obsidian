---
tags: [capa/frontend]
---

# Feature Panel admin

Página `/admin` (ADMIN y EDITOR), con pestañas:

| Pestaña | Componentes | Quién |
|---|---|---|
| Obras | `WorksTab`, `WorkForm`, `ChaptersPanel`, `ChapterForm`, `PagesManager` | ADMIN y EDITOR |
| Taxonomía | `TaxonomyTab` (tipos y géneros) | solo ADMIN |
| Reportes | `ReportsTab` (moderación) | solo ADMIN |

- `PagesManager` sube, inserta y reordena páginas.
- Valida tipo y tamaño de imágenes antes de enviar (`services/admin.ts`).

Backend: [[Módulo Catálogo]] · [[Módulo Comunidad]] · Conceptos: [[Flujo de publicación]] · [[Reportes y moderación]]
Mapa: [[Frontend - SPA React]]
