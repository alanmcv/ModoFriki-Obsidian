---
tags: [capa/transversal]
---

# Seguridad

Medidas de seguridad actuales.

- **Contraseñas:** bcrypt coste 12; máximo 72 bytes.
- **JWT:** HS256, 7 días, secreto de 32+ caracteres validado al arrancar (`env.ts`).
- **Roles en cada petición:** se leen de la BD, no se confía en el token.
- **CORS:** solo el front local y `FRONTEND_URL`.
- **Validación:** Joi con `.unknown(false)` (rechaza campos extra como `role`).
- **SQL:** sin `$queryRawUnsafe`.
- **Imágenes:** tipo verificado por firma del archivo, límites de tamaño, nombres generados por el servidor.
- **Errores:** 500 genérico, sin stack ni mensajes internos.
- **Logs:** sin credenciales ni token de Blob.
- **Hooks de Claude:** bloquean editar `.env` y comandos destructivos ([[Desarrollo con IA - Mapa]]).

Faltan: rate limiting, cabeceras con `helmet`, URLs privadas para borradores → [[Mejora - Rate limiting y cabeceras de seguridad]].

Módulo: [[Módulo Auth]] · Middlewares: [[Backend - Middlewares]] · Mapa: [[Arquitectura - Mapa]]
