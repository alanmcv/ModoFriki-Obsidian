---
tags: [capa/backend]
---

# Módulo Auth

Registro, login y usuario actual.

| Método | Ruta | Auth |
|---|---|---|
| POST | `/api/auth/register` | — |
| POST | `/api/auth/login` | — |
| GET | `/api/auth/me` | usuario |

- Contraseña con **bcrypt** (coste 12); JWT HS256 de 7 días.
- El rol y el estado se leen de la BD **en cada petición**: un JWT viejo no conserva privilegios quitados.
- Registro siempre BASIC / ACTIVE; no acepta `role` del cliente.
- También expone `authenticateToken`, que usan los demás routers.

BD: [[BD - Usuarios y roles]] · Front: [[Feature Autenticación]] · Seguridad: [[Seguridad]]
Conceptos: [[Roles y permisos]] · Capas: [[Backend - Arquitectura en capas]]
