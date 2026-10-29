---
tags: [grupo/mapa]
---

# Mejoras - Mapa

La arquitectura actual **funciona y está bien separada**. Estas mejoras la harían más confiable, más segura y más barata. **No están aplicadas en el código.**

## Cómo se categorizan
- 🟢 **Segura:** poco código, en pocos archivos, fácil de revertir. No cambia el comportamiento para el usuario.
- 🟡 **Mediana:** agrega piezas nuevas (tests, librerías, procesos) o toca partes delicadas. Riesgo controlado si se prueba.
- 🔴 **Riesgosa:** mueve mucho código o cambia la forma de trabajar del equipo. Necesita acuerdo del equipo.

## 🟢 Seguras (empezar por aquí)
| Mejora | Repo | Beneficio |
|---|---|---|
| [[Mejora - CI que valide build y tests]] | Ambos | Hoy el CI del back no detecta errores |
| [[Mejora - Conectar bases antes de arrancar]] | Back | Sin errores 500 al arrancar |
| [[Mejora - Health check real]] | Back | Render sabe si las bases están caídas |
| [[Mejora - Rate limiting y cabeceras de seguridad]] | Back | Evita fuerza bruta e inflar lecturas |
| [[Mejora - Corregir configuración de agentes]] | Ambos | Los agentes dejan de recomendar comandos prohibidos y el plugin del front vuelve a proteger el backend |
| [[Mejora - Documentación desactualizada]] | Ambos | Los agentes de IA reciben contexto correcto |

## 🟡 Medianas
| Mejora | Repo | Beneficio |
|---|---|---|
| [[Mejora - Tests del frontend]] | Front | Hoy hay un solo test |
| [[Mejora - Tests de integración del backend]] | Back | Probar consultas y migraciones reales |
| [[Mejora - Miniaturas de imágenes]] | Back + Front | Baja el costo principal y acelera la carga |
| [[Mejora - Limpieza de imágenes huérfanas]] | Back | Baja el costo de almacenamiento |
| [[Mejora - Frontend por features y lazy loading]] | Front | Carga inicial más liviana |
| [[Mejora - Tipos generados desde OpenAPI]] | Ambos | Errores de contrato al compilar, no en producción |
| [[Mejora - Caché de rankings y datos]] | Ambos | Menos consultas repetidas |

## 🔴 Riesgosas
| Mejora | Repo | Por qué es riesgosa |
|---|---|---|
| [[Mejora - Backend organizado por módulos]] | Back | Mueve casi todos los archivos, rompe la tabla de dueños de los subagentes y los hooks, y el repo es compartido |

## Orden recomendado
1. Corregir configuración de agentes + CI + arranque + health check.
2. Rate limiting y helmet.
3. Tests (front y algunos de integración en el back).
4. Miniaturas y limpieza de imágenes.
5. Lazy loading, tipos generados y caché.
6. Organización por módulos, solo con acuerdo del equipo.

Mejoras que pide el negocio (módulos nuevos): [[Impacto del negocio en la arquitectura]]

Decisión de priorizar así: [[DEC-17 - Mejoras priorizadas por riesgo]]

Arquitectura: [[Arquitectura - Mapa]] · Inicio: [[ModoFriki - Mapa]]
