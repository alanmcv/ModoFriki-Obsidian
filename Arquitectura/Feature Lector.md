---
tags: [capa/frontend]
---

# Feature Lector

Página `/read/:workId/:chapterId` (`components/reader/ReaderView.tsx`).

- Dos modos: **cascada** (scroll vertical, típico de manhwa) o **paginado**.
- Ajustes guardados con `useReaderSettings`.
- Al entrar envía `POST /chapters/:id/read-events` (marca leído si hay sesión).
- Guarda la página exacta en `localStorage` para "continuar leyendo".
- Navegación al capítulo anterior / siguiente.

Backend: [[Módulo Catálogo]] · [[Módulo Lectura]] · Conceptos: [[Flujo de lectura]] · [[Visitas y lecturas]]
Mapa: [[Frontend - SPA React]]
