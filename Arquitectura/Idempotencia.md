---
tags: [capa/transversal]
---

# Idempotencia

**Qué es:** repetir la misma operación da el mismo resultado que hacerla una vez.

**Dónde:** `POST /works/:id/visits` y `POST /chapters/:id/read-events` reciben `{ idempotencyKey: UUID }`.
- El front genera el UUID y lo **reutiliza en los reintentos** (`withRetry`).
- La BD tiene `idempotencyKey` único, y `ChapterReadReceipt` guarda cada clave.
- Usar la misma clave en otro destino → 409.

**Por qué:** si la red falla y el front reintenta, la visita no se cuenta dos veces.

BD: [[BD - Lectura y biblioteca]] · Módulo: [[Módulo Lectura]] · Concepto: [[Visitas y lecturas]] · Índice: [[Patrones de diseño]]
