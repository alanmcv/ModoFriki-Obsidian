# ModoFriki

Plataforma web para leer cómics, manhwas, mangas y novelas en español, con biblioteca personal, estadísticas de lectura y comunidad (comentarios, votos y reportes).

Este vault de Obsidian es el **segundo cerebro** del proyecto: arquitectura, dominio y modelo de negocio. El código vive en dos repositorios aparte.

## Contexto
- Proyecto académico: UPB, 6.º semestre, Certificación 1 – IA in Software Development (Módulo 2, examen 2).
- Autor del vault: Alan Cadena.
- Contenido previsto: obras de **autores independientes** de Bolivia y Latinoamérica (ver [[Negocio - Mapa]]).

## Repositorios
| Repo | Ruta local | Stack | Despliegue |
|---|---|---|---|
| Backend | `examen2/ModoFriki-Backend` | Node.js, Express 5, TypeScript, Prisma + PostgreSQL, Mongoose + MongoDB, Multer, Vercel Blob, Joi, JWT, Vitest | Render |
| Frontend | `examen2/ModoFriki-Web` | React 19, Vite 8, TypeScript 6, React Router 7, Tailwind 4, Zod, Vitest | Vercel |

El backend tiene su propio `CLAUDE.md` y `AGENTS.md` con las reglas de código. **Este archivo no los reemplaza**: si hay diferencias, mandan los del repo.

## Estructura del vault
```
ModoFriki/
├── CLAUDE.md           # este archivo
├── ModoFriki - Mapa.md # nota de inicio: enlaza los 6 mapas
├── Dominio/            # conceptos del negocio de lectura (obras, capítulos, roles, lectura, comunidad)
├── Arquitectura/       # cómo está construido (BD, backend, frontend, patrones, despliegue)
├── Decisiones/         # por qué se eligió cada cosa (DEC-NN, con plantilla)
├── Desarrollo con IA/  # agentes, hooks, skills y flujo de trabajo con IA
├── Mejoras/            # mejoras propuestas: seguras, medianas y riesgosas
└── Negocio/            # modelo de negocio propuesto (lienzo, planes, métricas)
```

## Arquitectura (resumen)
- Backend: **monolito en capas** Routes → Controllers → Services → Repositories, dividido en 5 dominios: auth, catalog, community, reading, discovery.
- Persistencia políglota: PostgreSQL (fuente de verdad de usuarios, catálogo y lectura), MongoDB (comentarios, votos, reportes) y Vercel Blob (imágenes).
- Frontend: SPA en React con pages → components → hooks/context → services → `lib/api.ts`.
- Detalle: [[Arquitectura - Mapa]]. Decisiones: [[Decisiones - Mapa]]. Mejoras propuestas: [[Mejoras - Mapa]].

## Reglas de negocio clave
- Roles: BASIC (lector), EDITOR (solo obras asignadas), ADMIN.
- Publicar una obra exige portada; publicar un capítulo exige páginas y obra publicada.
- El número de capítulo es único dentro de la obra.
- Las ediciones usan concurrencia optimista (`expectedUpdatedAt`, `expectedVersion`, `expectedRevision`); un dato viejo devuelve 409.
- Visitas y lecturas son idempotentes (`idempotencyKey`); solo una lectura por capítulo y día local cuenta para la racha.
- Las imágenes nunca se guardan en la BD: solo su referencia (URL y metadatos).
- Borrados lógicos (`deletedAt`, status DELETED).
- Detalle: [[Dominio - Mapa]].

## Convenciones del vault
- Nombre de archivo = título de la nota; enlaces con `[[Nombre exacto]]`.
- Frontmatter con `tags: [...]` para que la nota tome color en el grafo.
- Cada carpeta tiene una nota mapa (MOC) que enlaza todas sus notas.
- Etiquetas y colores:
  - `grupo/mapa` rojo · `capa/bd` rosa · `capa/backend` cian · `capa/frontend` verde lima · `capa/transversal` blanco · `capa/infra` gris · `capa/mejora` naranja
  - `dominio/contenido` azul · `dominio/usuarios` amarillo · `dominio/lectura` verde · `dominio/comunidad` morado
  - `capa/negocio` marrón
  - `decision` lila
  - `ia/contexto` turquesa · `ia/agentes` índigo · `ia/flujo` gris azulado
- Los colores viven en `.obsidian/graph.json`. **Cerrar Obsidian antes de editar ese archivo**, porque al estar abierto lo sobrescribe.

## Convenciones de código (resumen)
- Código simple y de nivel principiante; funciones cortas.
- Variables y código en inglés; interfaz y documentación en español.
- Backend: comillas dobles, punto y coma, tabs. Frontend: Prettier + ESLint.

## Forma de trabajar con Claude
- Respuestas cortas, en español.
- Explicar brevemente cada concepto nuevo.
- Antes de cambios grandes (estructura, dependencias, base de datos) proponer el plan y esperar confirmación.
- No agregar librerías ni funcionalidades no pedidas.
- Al crear notas: respetar las convenciones de arriba y enlazarlas desde su mapa.
- Una decisión nueva se registra en `Decisiones/` con la [[Plantilla de decisión]].
- Antes de aplicar una mejora, leer su nota en `Mejoras/` (categoría y riesgo).
- Nunca afirmar que algo se probó si no se ejecutó.

## Comandos
| Acción | Backend | Frontend |
|---|---|---|
| Instalar | `npm install` + `npx prisma generate` | `npm install` |
| Ejecutar | `npm run dev` (puerto 3000) | `npm run dev` (puerto 5173) |
| Pruebas | `npm test` | `npm run test:run` |
| Build | `npm run build` | `npm run build` |
| Migraciones | `npx prisma migrate deploy` (nunca `migrate dev` ni `reset`) | — |

## Git
- Backend: rama `feat/<feature>` desde `dev`; merge `--no-ff` a `dev`. Nunca push a `main` ni `qa`.
- Ramas `feat/` para funcionalidades y `fix/` para correcciones; commits pequeños.
