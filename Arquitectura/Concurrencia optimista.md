---
tags: [capa/transversal]
---

# Concurrencia optimista

**Qué es:** no se bloquea el registro; al guardar se envía la versión que uno vio y, si alguien la cambió antes, se rechaza con **409**.

| Recurso | Campo que se envía |
|---|---|
| Obra | `expectedUpdatedAt` |
| Capítulo y páginas | `expectedVersion` |
| Comentario | `expectedRevision` |

El front muestra: "Alguien cambió estos datos antes que tú. Recarga e inténtalo otra vez."

**Por qué:** dos editores pueden trabajar la misma obra sin pisarse.

Módulos: [[Módulo Catálogo]] · [[Módulo Comunidad]] · Índice: [[Patrones de diseño]]
