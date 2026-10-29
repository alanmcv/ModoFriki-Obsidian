---
tags: [decision]
estado: aceptada
fuente: docs/features/MODELO_DATOS_PROPUESTO.md (confirmado por el usuario)
---

# DEC-11 - Editores solo de obras asignadas

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** docs/features/MODELO_DATOS_PROPUESTO.md (confirmado por el usuario)

## Contexto
Varias personas publican capítulos, pero no todas deben tocar todo.

## Decisión
Un ADMIN asigna obras a cada EDITOR. El editor publica y edita solo esas obras y no elimina capítulos.

## Alternativas descartadas
- **Todos los editores editan todo:** riesgo de errores y abuso.
- **Rol por obra en otra tabla genérica:** más complejo de lo necesario.

## Consecuencias
- ✅ Control fino con auditoría.
- ✅ Sirve de base para el [[Programa de autores]].

Relacionado: [[Asignación de editores]] · [[Roles y permisos]] · Mapa: [[Decisiones - Mapa]]
