---
tags: [capa/backend]
---

# Backend - Services

Aquí viven las **reglas de negocio**.

- Clase con el repositorio inyectado por constructor y una instancia exportada:
  `export class ReadingService { constructor(private readonly repository = readingRepository) {} }`
- Valida la entrada con el helper Joi del dominio.
- Envuelve cada operación en `run()`, que registra el error y lo convierte con `catchAndLogError`.
- Los errores esperados se lanzan como `new AppError("mensaje", 4xx)`.
- No conoce Request, Response ni Blob.

Ejemplos de reglas: publicar exige portada ([[Estados de publicación]]), un editor solo toca obras asignadas ([[Asignación de editores]]), una revisión vieja da 409 ([[Concurrencia optimista]]).

Patrones: [[Inyección de dependencias]] · [[Principios SOLID]] · Capas: [[Backend - Arquitectura en capas]]
