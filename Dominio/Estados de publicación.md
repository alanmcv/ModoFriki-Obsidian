---
tags: [dominio/contenido]
---

# Estados de publicación

Dos estados distintos en cada obra:

| Estado | Valores | Significado |
|---|---|---|
| **Publicación** (`publicationStatus`) | DRAFT, PUBLISHED | ¿Lo ve el público? |
| **Emisión** (`releaseStatus`) | ONGOING, COMPLETED, HIATUS, CANCELLED | ¿La historia sigue saliendo? (En emisión, Finalizado, En pausa, Cancelado) |

Los capítulos solo tienen estado de publicación.

**Reglas:**
- Obra publicada ⇒ tiene portada.
- Capítulo publicado ⇒ tiene páginas y su obra está publicada.
- Lo oculto devuelve 404 al público (no 403), para no revelar que existe.

Relacionado: [[Obra]] · [[Capítulo]] · [[Flujo de publicación]] · Mapa: [[Dominio - Mapa]]
