---
tags: [capa/frontend]
---

# Feature Ficha de obra

Página `/series/:id/:slug?` (`components/detail/`).

- `SeriesDetail`: portada, sinopsis, géneros, lista de capítulos con marca de leído.
- Al abrir, envía `POST /works/:id/visits` con un UUID.
- `RatingControl`: valoración en medias estrellas.
- `CommentSection` / `CommentItem`: hilos, votos, edición.
- `ReportDialog`: reportar un comentario.

Backend: [[Módulo Catálogo]] · [[Módulo Lectura]] · [[Módulo Comunidad]]
Conceptos: [[Obra]] · [[Valoraciones]] · [[Comentarios]] · [[Visitas y lecturas]]
Mapa: [[Frontend - SPA React]]
