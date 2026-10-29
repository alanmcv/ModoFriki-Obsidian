---
tags: [decision]
estado: aceptada
fuente: docs/features/auth.md
---

# DEC-06 - Rol leído de la BD en cada petición

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** docs/features/auth.md

## Contexto
Un JWT dura 7 días; si a alguien le quitan el rol o lo suspenden, el token viejo seguiría siendo válido.

## Decisión
`authenticate` valida el JWT y además consulta el usuario: exige ACTIVE y toma el rol **actual** de la BD.

## Alternativas descartadas
- **JWT stateless puro:** más rápido, pero los privilegios quitados siguen vivos hasta que expire.

## Consecuencias
- ✅ Suspender o bajar de rol tiene efecto inmediato.
- ⚠️ Una consulta extra por petición autenticada.

Relacionado: [[Módulo Auth]] · [[Seguridad]] · [[Roles y permisos]] · Mapa: [[Decisiones - Mapa]]
