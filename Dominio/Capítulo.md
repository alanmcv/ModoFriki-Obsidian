---
tags: [dominio/contenido]
---

# Capítulo

Una entrega de una [[Obra]], formada por páginas (imágenes).

**Datos:** número decimal (permite `10.5`), título opcional, tipo (NORMAL, EXTRA, ANNOUNCEMENT), estado y `version`.

**Reglas:**
- El número es **único dentro de la obra**, hasta 9 enteros y 3 decimales.
- Publicarlo exige páginas **y** obra publicada.
- Máximo 1000 páginas por capítulo.
- El EDITOR no puede eliminar capítulos; el ADMIN sí.
- Un capítulo eliminado conserva su número (no se puede reutilizar).
- Cada edición sube `version`; enviar una versión vieja da 409.

Relacionado: [[Páginas y portadas]] · [[Flujo de publicación]] · [[Visitas y lecturas]]
Implementación: [[BD - Catálogo]] · [[Módulo Catálogo]] · Mapa: [[Dominio - Mapa]]
