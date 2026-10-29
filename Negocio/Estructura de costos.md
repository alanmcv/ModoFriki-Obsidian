---
tags: [capa/negocio]
---

# Estructura de costos

| Costo | Tipo | Nota |
|---|---|---|
| **Almacenamiento y transferencia de imágenes** (Vercel Blob) | Variable | El más grande: cada capítulo son decenas de imágenes que se descargan en cada lectura |
| Servidores (Render, Vercel) y bases (PostgreSQL, MongoDB) | Fijo / escalonado | Suben con los usuarios |
| Pago a autores | Variable | % de los ingresos ([[Programa de autores]]) |
| Comisión de la pasarela de pagos | Variable | % de cada cobro |
| Moderación y soporte | Fijo | Personas |
| Marketing | Fijo | Redes y convenciones |
| Dominio y correo | Fijo | Bajo |

Formas de bajar costos:
- Borrar imágenes huérfanas → [[Mejora - Limpieza de imágenes huérfanas]].
- Comprimir a WebP y cachear → [[Mejora - Caché de rankings y datos]].

Ingresos: [[Fuentes de ingresos]] · Mapa: [[Negocio - Mapa]]
