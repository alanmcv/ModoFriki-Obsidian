---
tags: [dominio/contenido]
---

# Obra

Una serie (manhwa, manga, manhua o novela).

**Datos:** título, slug único, sinopsis, tipo, géneros, títulos alternativos, portada, banner incap, estado de publicación y estado de emisión.

**Reglas:**
- Solo el ADMIN crea obras y géneros; el ADMIN o el EDITOR asignado la editan.
- Publicarla exige portada.
- Sin sesión solo se ven obras PUBLISHED y no eliminadas.
- Borrado lógico (`deletedAt`); los capítulos no se borran en cascada.
- Editar el título conserva la carpeta de imágenes.
- Para editar hay que enviar `expectedUpdatedAt` → [[Concurrencia optimista]].

Partes: [[Capítulo]] · [[Páginas y portadas]] · [[Tipos de obra y géneros]] · [[Estados de publicación]]
Implementación: [[BD - Catálogo]] · [[Módulo Catálogo]] · Mapa: [[Dominio - Mapa]]
