---
tags: [capa/mejora]
---

# Mejora - Tests de integración del backend

**Categoría:** 🟡 Mediana

**Hoy:** hay tests unitarios de schemas, middlewares y services, pero **todos con repositorios simulados**. Ninguno prueba una consulta real, una migración o una transacción.

**Propuesta:** unos pocos tests contra un PostgreSQL desechable (Docker o Testcontainers) para lo más delicado:
- Idempotencia: el mismo `idempotencyKey` no suma dos lecturas ([[Idempotencia]]).
- Una lectura por capítulo y día local para la racha.
- Número de capítulo único y 409 por versión vieja ([[Concurrencia optimista]]).
- Que las migraciones se apliquen desde cero.

**Regla del proyecto:** nunca contra la base compartida de Render ([[BD - Migraciones]]).

**Riesgo:** no toca producción; necesita Docker en la máquina y en el CI.

Relacionado: [[Backend - Repositories]] · [[Mejora - CI que valide build y tests]] · Índice: [[Mejoras - Mapa]]
