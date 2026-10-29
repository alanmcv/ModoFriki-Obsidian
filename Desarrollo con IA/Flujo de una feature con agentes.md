---
tags: [ia/flujo]
---

# Flujo de una feature con agentes

Las 7 etapas de `docs/agents/WORKFLOW.md`:

1. **Auditoría:** el coordinador revisa estructura, scripts, Prisma, Mongoose, rutas y Git.
2. **Planificación:** [[Agente planner]] escribe el plan con la [[Plantilla de plan de feature]].
3. **Contratos:** `db` define persistencia y `media` define `res.locals`; se resuelven antes de paralelizar.
4. **Trabajo:** `db` → `media` → `dev`, con archivos disjuntos ([[Propiedad de archivos por rol]]).
5. **Entrega de cada rol:** rama, SHA, archivos, validaciones, riesgos.
6. **Integración controlada:** build y tests, [[Agente reviewer]] y [[Agente security]], máximo 2 rondas de corrección.
7. **QA:** solo con criterios cumplidos y **aprobación humana**.

Orden del MVP: base → schema → auth → genres-tags → works → chapters → favorites → comments → users → uploads.

Automatizado en: [[Skill modofriki-feature]] · Mapa: [[Desarrollo con IA - Mapa]]
