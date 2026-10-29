---
tags: [capa/mejora]
---

# Mejora - Rate limiting y cabeceras de seguridad

**Categoría:** 🟢 Segura

**Hoy:** no hay límite de peticiones ni `helmet`. El front ya tiene mensaje para 429, pero el backend nunca lo envía.

**Riesgos:**
- Fuerza bruta en `/auth/login`.
- Inflar visitas y lecturas anónimas creando UUID nuevos (la idempotencia no lo impide).

**Propuesta:**
- `express-rate-limit`: más estricto en login/registro y en `visits` / `read-events` anónimos.
- `helmet` para cabeceras HTTP seguras.
- Para borradores: usar Blob privado o URLs firmadas, porque hoy una URL de borrador es pública.

Actual: [[Seguridad]] · Índice: [[Mejoras - Mapa]]
