---
tags: [capa/frontend]
---

# Feature Autenticación

Páginas `/login` y `/register` (`components/auth/`).

- `AuthView`: formularios con `react-hook-form` + Zod.
- Guarda el token en `localStorage` (`modofriki_token`).
- `ProtectedRoute` protege rutas por sesión y rol.

Backend: [[Módulo Auth]] · Conceptos: [[Roles y permisos]] · Seguridad: [[Seguridad]]
Mapa: [[Frontend - SPA React]]
