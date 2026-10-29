---
tags: [dominio/lectura]
---

# Biblioteca personal

Lo que cada usuario guarda de su lectura.

- **Favoritos:** una obra puede estar o no (único por usuario y obra).
- **Capítulos leídos:** estado actual; se puede desmarcar sin borrar el historial.
- **Historial:** capítulos leídos con obra, ordenados por última lectura.
- **Progreso por obra:** total de capítulos, leídos y porcentaje.
- Solo se listan obras y capítulos publicados; pero se pueden quitar relaciones aunque el contenido ya esté oculto.
- El `userId` sale del token, nunca del cliente.

Implementación: [[BD - Lectura y biblioteca]] · [[Módulo Lectura]] · [[Feature Biblioteca y perfil]] · Mapa: [[Dominio - Mapa]]
