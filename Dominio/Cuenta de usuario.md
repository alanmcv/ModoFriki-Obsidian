---
tags: [dominio/usuarios]
---

# Cuenta de usuario

**Datos:** email, username, contraseña (hash), rol, estado y zona horaria.

**Reglas:**
- Username de 3 a 32 caracteres; email hasta 254; contraseña mínimo 8 caracteres y máximo 72 bytes.
- Email y username únicos sin importar mayúsculas ni espacios.
- Zona horaria IANA válida; por defecto `America/La_Paz` (se usa para rachas y calendario).
- Todo registro nuevo es BASIC y ACTIVE.
- Estados: ACTIVE, SUSPENDED, DELETED. Solo ACTIVE puede iniciar sesión.
- Un visitante sin cuenta puede leer, pero no guarda favoritos, historial ni progreso.

Implementación: [[BD - Usuarios y roles]] · [[Módulo Auth]] · Roles: [[Roles y permisos]] · Mapa: [[Dominio - Mapa]]
