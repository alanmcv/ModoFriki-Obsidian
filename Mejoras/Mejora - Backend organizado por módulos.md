---
tags: [capa/mejora]
---

# Mejora - Backend organizado por módulos

**Categoría:** 🔴 Riesgosa

**Hoy:** las carpetas son por capa (`routes/`, `controllers/`, `services/`…). Para tocar "lectura" hay que abrir 6 carpetas.

**Propuesta:** **monolito modular**, una carpeta por dominio con sus capas adentro:
```
src/modules/
├── auth/        (auth.routes.ts, auth.controller.ts, auth.service.ts, auth.repository.ts, auth.schema.ts, auth.types.ts)
├── catalog/
├── community/
├── reading/
└── discovery/
src/shared/      (middlewares, handlers, utils, config)
```
- Regla: un módulo no importa el repositorio de otro; solo su service o tipos.
- Facilita separar un módulo en microservicio más adelante (por ejemplo comunidad, que ya usa otra base).

**Costo:** mover archivos y arreglar imports; también hay que actualizar la tabla de dueños de archivos de los subagentes ([[Desarrollo con IA - Mapa]]).

Actual: [[Backend - Arquitectura en capas]] · Índice: [[Mejoras - Mapa]]
