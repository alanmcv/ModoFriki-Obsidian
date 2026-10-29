---
tags: [capa/frontend]
---

# Frontend - Cliente API

`src/lib/api.ts`: una sola función `request<T>()` para hablar con el backend.

- URL base: `VITE_API_URL` o `http://localhost:3000/api`.
- Agrega `Authorization: Bearer <token>` si hay token en `localStorage`.
- Envía JSON o `FormData` (para subir imágenes).
- Desempaqueta `data` del envelope del backend.
- Traduce errores a español: primero por mensaje exacto (`DETAILS`) y si no por código (`MESSAGES`).
- Un 401 con token dispara el evento `modofriki:unauthorized` → la sesión se cierra.
- `withRetry()` reintenta errores de red o 5xx (solo en operaciones idempotentes).

Encima están los **services** (`services/catalog.ts`, `reading.ts`, `community.ts`, `discovery.ts`, `auth.ts`, `admin.ts`), que convierten los DTO del backend a tipos del front (`toSeries`, `toChapter`).

Contrato: [[Backend - Respuestas y errores]] · Patrones: [[Patrón Adapter]] · [[Patrón Observer]] · [[Idempotencia]]
Mapa: [[Frontend - SPA React]]
