---
tags: [capa/backend]
---

# Backend - Controllers

Una clase por dominio que recibe el service por constructor.

Cada *handler*:
1. Saca `req.params`, `req.query`, `req.body` y `res.locals.user`.
2. Llama al service.
3. Responde con `SuccessResponseHandler`, `CreatedResponseHandler` o `NoContentResponseHandler`.

No hace consultas a la base ni valida reglas de negocio.

Respuestas: [[Backend - Respuestas y errores]] · Capas: [[Backend - Arquitectura en capas]]
