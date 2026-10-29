---
tags: [ia/agentes]
---

# Agente media

**Rol:** Dueño del pipeline multimedia (Multer + Vercel Blob).

| | |
|---|---|
| Archivos propios | `src/middlewares/media/**`, `src/utils/media-paths.ts` |
| Herramientas | Todas |
| Definido en | `.claude/agents/media.md` |

**Reglas principales**
- Valida la **firma real** del archivo, no solo el MIME.
- Límites explícitos de tamaño y cantidad; nombres sanitizados.
- Deja los metadatos en `res.locals` para el controller.
- Compensación si la persistencia falla después de subir.
- Nunca registra el token de Blob.

**Entrega:** Contrato de los middlewares que consume `dev` y validaciones.

Flujo: [[Flujo de una feature con agentes]] · Dueños: [[Propiedad de archivos por rol]] · Mapa: [[Desarrollo con IA - Mapa]]
