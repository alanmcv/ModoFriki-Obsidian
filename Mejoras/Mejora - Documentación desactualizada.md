---
tags: [capa/mejora]
---

# Mejora - Documentación desactualizada

**Categoría:** 🟢 Segura

**Hoy:**
- `ModoFriki-Web/README.md` y el skill `modofriki-frontend` dicen "solo frontend, con mocks y sin panel admin", pero el front ya consume la API y tiene `/admin`.
- `docs/API.md` cita `ModoFriki-Web/src/shared/types.ts`, que no existe (es `src/types/index.ts`).
- El README del backend está vacío.
- Las instrucciones de varios agentes contradicen las reglas actuales (por ejemplo, `db.md` y el hook `guard-bash.mjs` recomiendan `db push`, que está prohibido) → [[Inconsistencias en la configuración de IA]]. Su corrección está en [[Mejora - Corregir configuración de agentes]].

**Por qué importa:** los agentes de IA leen estos archivos como verdad; un contexto viejo produce código equivocado.

**Propuesta:** actualizar README, skills y API.md, y enlazar este vault desde ambos repos.

Relacionado: [[Desarrollo con IA - Mapa]] · Índice: [[Mejoras - Mapa]]
