---
tags: [capa/frontend]
---

# Frontend - Shell y providers

Lo que envuelve a toda la app.

- `main.tsx` → `App` → `Providers` → `AppShell` → `AppRoutes`.
- `Providers`: `BrowserRouter` → `AuthProvider` → `LibraryProvider` → `UIProvider` + `Toaster` (avisos).
- `AppShell`: `Header`, `MobileNav`, `AnnouncementBar`, `Footer` y la paleta de comandos (`CommandPalette`, atajo de teclado).
- `ProtectedRoute`: redirige al login si no hay sesión; acepta `roles={['ADMIN','EDITOR']}`.

Rutas:
| Ruta | Página | Protegida |
|---|---|---|
| `/` | Home | — |
| `/series` | Catálogo | — |
| `/series/:id/:slug?` | Ficha | — |
| `/read/:workId/:chapterId` | Lector | — |
| `/genres`, `/rankings` | Géneros, Rankings | — |
| `/favorites`, `/profile` | Biblioteca, Perfil | usuario |
| `/admin` | Panel | ADMIN o EDITOR |
| `/login`, `/register` | Auth | — |

Todas las páginas se importan al inicio (sin lazy loading) → [[Mejora - Frontend por features y lazy loading]].
Estado: [[Frontend - Estado global]] · Mapa: [[Frontend - SPA React]]
