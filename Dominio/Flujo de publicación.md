---
tags: [dominio/contenido]
---

# Flujo de publicación

Cómo un editor publica contenido.

```mermaid
flowchart TD
  A[ADMIN crea la obra en borrador] --> B[ADMIN asigna un EDITOR]
  B --> C[Sube portada y publica la obra]
  C --> D[EDITOR crea capítulo en borrador]
  D --> E[Sube páginas: reemplazar, insertar o reordenar]
  E --> F[Publica el capítulo]
  F --> G[Aparece en novedades]
```

Pantalla: [[Feature Panel admin]] · Reglas: [[Estados de publicación]] · [[Asignación de editores]]
Negocio: en la propuesta, el autor independiente sigue este mismo flujo → [[Programa de autores]]
Mapa: [[Dominio - Mapa]]
