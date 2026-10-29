---
tags: [capa/mejora]
---

# Mejora - CI que valide build y tests

**Categoría:** 🟢 Segura

**Hoy:** el workflow del backend ejecuta `find src -name "*.js" -exec node --check`, pero en `src/` solo hay `.ts`: no revisa nada y despliega igual. El front sí compila antes de desplegar (`vercel build` corre `tsc -b && vite build`), pero no corre lint ni tests.

O sea: hoy hay **despliegue continuo (CD)**, pero la **integración continua (CI)** es mínima en el front y nula en el back. Además, todo corre solo al hacer push a `main`, no al integrar a `dev`.

**Propuesta:**
- Backend: `npm ci` → `npx prisma generate` → `npx tsc --noEmit` → `npm test` → recién entonces el deploy hook.
- Frontend: `npm run lint` → `npm run test:run` → `npm run build` → deploy.
- Correr lo mismo en cada *pull request* a `dev`, no solo en `main`.

Actual: [[Despliegue y CI-CD]] · Índice: [[Mejoras - Mapa]]
