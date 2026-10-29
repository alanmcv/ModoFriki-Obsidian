---
tags: [capa/mejora]
---

# Mejora - Tests del frontend

**Categoría:** 🟡 Mediana

**Hoy:** el front tiene Vitest y Testing Library configurados, pero **un solo test** (`src/lib/format.test.ts`). El lector, el panel admin, la auth y el cliente API no tienen pruebas.

**Propuesta (de más a menos importante):**
1. `lib/api.ts`: traduce errores, agrega el token, emite `modofriki:unauthorized` ante 401, `withRetry` no reintenta 4xx.
2. `services/*`: los adaptadores `toSeries`, `toChapter`, `refToSeries`.
3. `ProtectedRoute`: redirige sin sesión y bloquea por rol.
4. `services/admin.ts`: `validateImages` (tipo y tamaño).
5. Un test de componente del lector (cambio cascada ↔ paginado).

Se simula `fetch`, sin backend real.

**Riesgo:** no cambia código de producción; el costo es el tiempo de escribirlos.

Relacionado: [[Frontend - Cliente API]] · [[Patrón Adapter]] · [[Mejora - CI que valide build y tests]] · Índice: [[Mejoras - Mapa]]
