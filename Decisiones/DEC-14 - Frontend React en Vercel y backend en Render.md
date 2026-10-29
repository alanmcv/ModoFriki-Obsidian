---
tags: [decision]
estado: aceptada
fuente: README del front y workflows de GitHub
---

# DEC-14 - Frontend React en Vercel y backend en Render

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** README del front y workflows de GitHub

## Contexto
Dos repositorios, dos personas, despliegue gratuito o barato.

## Decisión
SPA en React + Vite desplegada en Vercel; API Express en Render; se comunican por REST con el contrato de `docs/API.md`.

## Alternativas descartadas
- **Un solo repo con SSR (Next.js):** mejor SEO, pero mezcla el trabajo de dos personas.

## Consecuencias
- ✅ Cada repo se despliega solo.
- ⚠️ SPA sin SSR: las obras se indexan peor en buscadores.
- ⚠️ El contrato se duplica a mano → [[Mejora - Tipos generados desde OpenAPI]].

Relacionado: [[Despliegue y CI-CD]] · [[Frontend - SPA React]] · Mapa: [[Decisiones - Mapa]]
