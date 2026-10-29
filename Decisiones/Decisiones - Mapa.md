---
tags: [grupo/mapa]
---

# Decisiones - Mapa

Registro de **por qué** ModoFriki está hecho así. Cada nota sigue la [[Plantilla de decisión]]: contexto, decisión, alternativas descartadas y consecuencias.

## ✅ Aceptadas (ya están en el código)
| Decisión | Fuente |
|---|---|
| [[DEC-01 - Monolito en capas]] | AGENTS.md |
| [[DEC-02 - PostgreSQL como fuente de verdad]] | docs/features/MODELO_DATOS_PROPUESTO.md |
| [[DEC-03 - MongoDB para la comunidad]] | docs/features/community.md |
| [[DEC-04 - Imágenes en Vercel Blob con pipeline en middlewares]] | AGENTS.md (Pipeline multimedia obligatorio) |
| [[DEC-05 - UUID en todas las bases]] | prisma/schema.prisma y modelos Mongoose |
| [[DEC-06 - Rol leído de la BD en cada petición]] | docs/features/auth.md |
| [[DEC-07 - Concurrencia optimista]] | docs/API.md (Catálogo implementado) |
| [[DEC-08 - Eventos idempotentes para visitas y lecturas]] | docs/features/user-reading.md |
| [[DEC-09 - Borrado lógico]] | docs/features/MODELO_DATOS_PROPUESTO.md |
| [[DEC-10 - Migraciones SQL aditivas]] | CLAUDE.md y prisma/README.md |
| [[DEC-11 - Editores solo de obras asignadas]] | docs/features/MODELO_DATOS_PROPUESTO.md (confirmado por el usuario) |
| [[DEC-12 - Paginación por cursor en comunidad]] | docs/API.md |
| [[DEC-13 - Lecturas anónimas en estadísticas]] | docs/features/MODELO_DATOS_PROPUESTO.md (confirmado por el usuario) |
| [[DEC-14 - Frontend React en Vercel y backend en Render]] | README del front y workflows de GitHub |
| [[DEC-15 - Subagentes con archivos propios]] | CLAUDE.md del backend |

## 💡 Propuestas (de este vault)
| Decisión | Fuente |
|---|---|
| [[DEC-16 - Contenido de autores independientes]] | Este vault (Negocio) |
| [[DEC-17 - Mejoras priorizadas por riesgo]] | Este vault (Mejoras) |

Las decisiones estructurales nuevas las propone el [[Agente architect]] y quedan registradas aquí.

Arquitectura: [[Arquitectura - Mapa]] · Mejoras: [[Mejoras - Mapa]] · Inicio: [[ModoFriki - Mapa]]
