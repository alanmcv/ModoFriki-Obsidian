---
tags: [decision]
estado: aceptada
fuente: AGENTS.md (Pipeline multimedia obligatorio)
---

# DEC-04 - Imágenes en Vercel Blob con pipeline en middlewares

**Estado:** ✅ Aceptada (está en el código) · **Fuente:** AGENTS.md (Pipeline multimedia obligatorio)

## Contexto
Cada capítulo son decenas de imágenes pesadas.

## Decisión
Los bytes van a Vercel Blob; la base guarda solo referencias. La recepción, validación y subida ocurren en **middlewares**; el service solo arma el plan.

## Alternativas descartadas
- **Imágenes en la base:** la llenaría y la haría lenta.
- **Subir desde el service:** mezclaría negocio con un proveedor externo.

## Consecuencias
- ✅ Bases livianas; el service no depende de Blob.
- ⚠️ Sin transacción distribuida: puede haber archivos huérfanos → [[Mejora - Limpieza de imágenes huérfanas]].
- ⚠️ Almacén público: los borradores tienen URL accesible.

Relacionado: [[Backend - Pipeline multimedia]] · [[BD - Vercel Blob]] · Mapa: [[Decisiones - Mapa]]
