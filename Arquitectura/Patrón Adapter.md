---
tags: [capa/transversal]
---

# Patrón Adapter

**Qué es:** convierte una interfaz o formato en otro que el resto espera.

**Dónde:**
- Front: `toSeries(work: WorkDto)`, `toChapter()`, `refToSeries()` traducen los DTO del backend (`releaseStatus: "ONGOING"`) a tipos del front (`"En emisión"`).
- Front: `api.ts` traduce errores en inglés a mensajes en español.
- Back: `@prisma/adapter-pg` conecta Prisma con el driver `pg`.

**Por qué:** si el backend cambia un nombre, solo se toca el adaptador, no todas las pantallas.

Capa: [[Frontend - Cliente API]] · Índice: [[Patrones de diseño]]
