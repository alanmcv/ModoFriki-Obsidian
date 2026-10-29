---
tags: [ia/flujo]
---

# Skills y plugin de OpenCode

Configuración de IA del **frontend** (`ModoFriki-Web/.opencode/`).

| Skill | Para qué |
|---|---|
| `modofriki-frontend` | Stack, identidad visual, tokens y estructura de carpetas |
| `modofriki-reader` | Experiencia del lector: pantalla completa, sin anuncios ni distracciones, atajos y progreso |
| `modofriki-delivery` | Definición de terminado, formato de commits; trabajar en la rama `ModoFriki-Interface` y **nunca** hacer `git push` |

**Plugin `modofriki-guard`:** antes de cada herramienta bloquea `git push`, comandos destructivos (`rm -rf`), editar `.git` y archivos `.env` reales, y editar el backend.

Ver fallas en [[Inconsistencias en la configuración de IA]] · Front: [[Frontend - SPA React]] · Mapa: [[Desarrollo con IA - Mapa]]
