---
tags: [capa/transversal]
---

# Patrón Repository

**Qué es:** una clase que esconde cómo se guardan los datos; el resto del código pide "dame esto" sin saber si viene de PostgreSQL o MongoDB.

**Dónde:** `src/repositories/<dominio>/`. Contratos en `src/types/<dominio>.types.ts`.

**Por qué:**
- El service no cambia si cambia la base.
- Los tests usan un repositorio falso (mock), sin tocar la BD real.

```ts
export class ReadingService {
  constructor(private readonly repository: ReadingRepositoryContract = readingRepository) {}
}
```

Capa: [[Backend - Repositories]] · Bases: [[BD - Persistencia políglota]] · Índice: [[Patrones de diseño]]
