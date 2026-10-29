---
tags: [capa/bd]
---

# BD - Vercel Blob

Almacén de archivos donde viven las imágenes.

Rutas:
- Portada de obra: `<slug-titulo>-<uuid>/Covers/<uuid>.<ext>`
- Banner de capítulos (incap): `<slug-titulo>-<uuid>/CoverPage/<uuid>.<ext>`
- Páginas: `<slug-obra>/Chapter-<chapterUuid>/<uuid>-<posición>.<ext>`

Reglas:
- Nunca se sobrescribe un archivo: una colisión devuelve 409.
- Editar el título conserva la carpeta.
- El almacén es **público**: un borrador oculto en la API sigue teniendo URL accesible.
- El token `BLOB_READ_WRITE_TOKEN` nunca se registra en logs.

Referencias en BD: [[BD - Multimedia]] · Pipeline: [[Backend - Pipeline multimedia]]
Mapa: [[BD - Persistencia políglota]]
