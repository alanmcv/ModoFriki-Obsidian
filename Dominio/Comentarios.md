---
tags: [dominio/comunidad]
---

# Comentarios

Conversación sobre una obra o un capítulo.

- Se comenta una obra (WORK) o un capítulo (CHAPTER); las respuestas heredan el destino.
- Hilos de **cualquier profundidad**; se piden como páginas planas por raíz o por padre.
- Texto en Markdown, no vacío, hasta 10 000 caracteres. El front debe sanitizarlo.
- Editar exige `expectedRevision` → [[Concurrencia optimista]].
- Borrar no elimina el nodo: queda DELETED y sin texto, para no romper el hilo.
- Si el autor está inactivo, se muestra como `null`.
- Solo se comenta en contenido publicado.

Relacionado: [[Votos]] · [[Reportes y moderación]] · Implementación: [[BD - MongoDB comunidad]] · [[Módulo Comunidad]]
Mapa: [[Dominio - Mapa]]
