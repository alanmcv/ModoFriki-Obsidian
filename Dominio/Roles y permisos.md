---
tags: [dominio/usuarios]
---

# Roles y permisos

| Acción | Visitante | BASIC (Lector) | EDITOR | ADMIN |
|---|---|---|---|---|
| Leer obras publicadas | ✅ | ✅ | ✅ | ✅ |
| Favoritos, valoraciones, historial, rachas | — | ✅ | ✅ | ✅ |
| Comentar, votar, reportar | — | ✅ | ✅ | ✅ |
| Ver borradores | — | — | De obras asignadas | ✅ |
| Editar obra y capítulos | — | — | De obras asignadas | ✅ |
| Eliminar capítulos | — | — | — | ✅ |
| Crear obras, tipos y géneros | — | — | — | ✅ |
| Moderar reportes y borrar comentarios ajenos | — | — | — | ✅ |

- El rol se consulta en la BD en cada petición.
- El EDITOR no modera comentarios ajenos.

Relacionado: [[Asignación de editores]] · [[Cuenta de usuario]] · Implementación: [[Módulo Auth]] · [[Seguridad]]
Negocio: [[Programa de autores]] · Mapa: [[Dominio - Mapa]]
