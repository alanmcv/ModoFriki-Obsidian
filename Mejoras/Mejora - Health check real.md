---
tags: [capa/mejora]
---

# Mejora - Health check real

**Categoría:** 🟢 Segura

**Hoy:** `GET /health` responde siempre `{ status: "ok" }`, aunque PostgreSQL o MongoDB estén caídos. Render cree que el servicio está sano.

**Propuesta:** que `/health` pruebe las dos bases.
- PostgreSQL: `SELECT 1` con Prisma.
- MongoDB: `mongoose.connection.readyState === 1`.
- Si alguna falla → **503** con `{ postgres: "down", mongo: "ok" }` (sin mostrar URLs ni credenciales).
- Configurar ese endpoint como *health check* en Render.

**Riesgo:** bajo; solo cambia una ruta. Mantener `GET /` simple para no consultar la BD en cada ping.

Relacionado: [[Mejora - Conectar bases antes de arrancar]] · [[Despliegue y CI-CD]] · Índice: [[Mejoras - Mapa]]
