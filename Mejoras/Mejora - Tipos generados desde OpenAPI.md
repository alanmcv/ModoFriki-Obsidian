---
tags: [capa/mejora]
---

# Mejora - Tipos generados desde OpenAPI

**Categoría:** 🟡 Mediana

**Hoy:** el backend documenta su API en `openapi.yaml`, pero el front escribe los tipos a mano (`services/catalog.ts`, `services/reading.ts`…). Si el back cambia un campo, el front no se entera hasta que falla en ejecución.

**Propuesta:** generar los tipos del front desde `openapi.yaml` (por ejemplo con `openapi-typescript`) y usarlos en los services.
- Un cambio de contrato rompe el `build` del front en vez de romper en producción.
- Mantener `openapi.yaml` al día pasa a ser obligatorio.

**Riesgo:** agrega una dependencia de desarrollo y hay que ajustar los services; los adaptadores ([[Patrón Adapter]]) siguen igual.

Relacionado: [[Backend - Respuestas y errores]] · [[Frontend - Cliente API]] · Índice: [[Mejoras - Mapa]]
