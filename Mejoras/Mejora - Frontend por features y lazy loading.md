---
tags: [capa/mejora]
---

# Mejora - Frontend por features y lazy loading

**Categoría:** 🟡 Mediana

**Hoy:** `router.tsx` importa las 12 páginas al inicio, incluido el panel admin que solo usa el personal. Los componentes están en `components/<feature>` pero sus hooks y services están en carpetas globales.

**Propuesta:**
1. **Lazy loading** con `React.lazy` + `Suspense` en `/admin`, `/read` y `/profile`. El lector común no descarga el panel admin.
2. Carpetas por feature:
```
src/features/
├── catalog/   (pages, components, hooks, services)
├── reader/
├── library/
├── community/
└── admin/
src/shared/    (ui, lib, hooks genéricos)
```
- Regla: una feature no importa otra; lo común va a `shared/`.

Actual: [[Frontend - SPA React]] · [[Frontend - Shell y providers]] · Índice: [[Mejoras - Mapa]]
