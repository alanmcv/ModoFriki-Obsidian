---
tags: [capa/bd]
---

# BD - Multimedia

Tablas de PostgreSQL que guardan **referencias** a las imágenes de Vercel Blob.

| Tabla | Para qué |
|---|---|
| `MediaAsset` | Una imagen: pathname (único), url, contentType, sizeBytes, width, height, status (AVAILABLE / DELETING) |
| `UploadBatch` | Lote de subida: quién, para qué obra o capítulo, status PENDING / COMMITTED / ABANDONED, `expiresAt` |
| `UploadObject` | Cada archivo planificado del lote: PLANNED → UPLOADED → LINKED → CLEANED |
| `MediaCleanupJob` | Tareas de borrado con reintentos (attempts, nextAttemptAt, lastErrorCode) |
| `SiteSettings` | Banner general de la plataforma |

- El lote reserva los nombres **antes** de subir; si algo falla queda ABANDONED y se puede recuperar.
- ⚠️ `MediaCleanupJob` existe en el esquema pero **ningún código lo usa** → [[Mejora - Limpieza de imágenes huérfanas]].

Pipeline: [[Backend - Pipeline multimedia]] · Archivos: [[BD - Vercel Blob]] · Conceptos: [[Páginas y portadas]]
Mapa: [[BD - Persistencia políglota]]
