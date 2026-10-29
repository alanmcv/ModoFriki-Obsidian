---
tags: [capa/bd]
---

# BD - Catálogo

Tablas de PostgreSQL para obras y capítulos.

| Tabla | Campos importantes | Notas |
|---|---|---|
| `WorkType` | name, slug | Manhwa, Manga, Manhua, Novela |
| `Work` | title, slug (único), synopsis, typeId, publicationStatus, releaseStatus, coverAssetId, incapBannerAssetId, visitsCount, deletedAt | La obra |
| `WorkAlternativeTitle` | workId, title, normalizedTitle | Otros nombres para la búsqueda |
| `Genre` / `WorkGenre` | name, slug / workId + genreId | Relación muchos a muchos |
| `Chapter` | workId, number (decimal 12,3), title, kind, status, version, deletedAt | Único por (workId, number). `version` para concurrencia optimista |
| `ChapterPage` | chapterId, assetId, position | Orden de las páginas. Único por (chapterId, position) |

Enums: `PublicationStatus` DRAFT/PUBLISHED · `WorkReleaseStatus` ONGOING/COMPLETED/HIATUS/CANCELLED · `ChapterKind` NORMAL/EXTRA/ANNOUNCEMENT.

- Borrado lógico con `deletedAt`.
- Todas las FK usan `onDelete: Restrict`: no se borra en cascada.

Módulo: [[Módulo Catálogo]] · Conceptos: [[Obra]] · [[Capítulo]] · [[Tipos de obra y géneros]] · [[Estados de publicación]]
Mapa: [[BD - Persistencia políglota]]
