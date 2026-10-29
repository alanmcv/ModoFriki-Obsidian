---
tags: [dominio/lectura]
---

# Flujo de lectura

```mermaid
sequenceDiagram
  participant L as Lector
  participant F as Front
  participant B as Backend
  L->>F: Abre la ficha
  F->>B: GET /works/:id
  F->>B: POST /works/:id/visits {UUID}
  L->>F: Entra al capítulo
  F->>B: GET capítulo (páginas)
  F->>B: POST /chapters/:id/read-events {UUID}
  B-->>F: counted, isRead
  F->>F: Guarda la página exacta en localStorage
```

- Capítulos leídos antes de crear la cuenta: `PUT /me/read-chapters/:id` (marca sin sumar a la racha).
- Para pintar las marcas de leído: `GET /me/works/:id/progress`.

Pantallas: [[Feature Ficha de obra]] · [[Feature Lector]] · Conceptos: [[Visitas y lecturas]] · [[Rachas y calendario de lectura]]
Mapa: [[Dominio - Mapa]]
