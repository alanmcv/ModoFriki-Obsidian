---
tags: [capa/frontend]
---

# Frontend - Estado global

Estado compartido con **React Context** + hooks.

| Context | Guarda | Hook |
|---|---|---|
| `AuthContext` | Usuario, token, login/logout | `useAuth` |
| `LibraryContext` | Favoritos (del backend) y progreso de página dentro del capítulo (local) | `useLibrary` |
| `UIContext` | Paleta de comandos, menú móvil, anuncio cerrado | `useUI` |

Hooks de datos: `useCatalog` (`useWork`, `useChapters`, `useGenres`…), `useReading` (`useWorkStats`, `useWorkProgress`), `useAsync`, `usePagination`.
Hooks de UI: `useDebounce`, `useHotkeys`, `useMediaQuery`, `useReaderSettings`, `useLocalStorage`…

- El progreso exacto de página se guarda en `localStorage` porque el backend solo registra lectura por capítulo.
- No hay librería de estado ni de caché (Redux, TanStack Query).

Patrón: [[Patrón Observer]] · Mapa: [[Frontend - SPA React]]
