---
tags: [capa/transversal]
---

# Principios SOLID

Cómo se ven los principios SOLID **en el código actual** de ModoFriki.

| Principio | Qué dice | Ejemplo en ModoFriki |
|---|---|---|
| **S** Responsabilidad única | Una clase, una razón para cambiar | Controller solo maneja HTTP; Service solo reglas; Repository solo datos ([[Backend - Arquitectura en capas]]) |
| **O** Abierto/cerrado | Extender sin modificar | Para un dominio nuevo se agrega su router y se monta en `app.ts`; los middlewares existentes no cambian ([[Backend - Routes]]) |
| **L** Sustitución de Liskov | Una implementación se puede cambiar por otra del mismo contrato | En los tests, el repositorio real se reemplaza por un mock que cumple `ReadingRepositoryContract` ([[Patrón Repository]]) |
| **I** Segregación de interfaces | No depender de lo que no usas | `createCatalogRouter` pide `Pick<AuthService, "authenticateToken">`, solo el método que necesita |
| **D** Inversión de dependencias | Depender de abstracciones | `new ReadingService(repository = readingRepository)`: el service recibe el contrato por constructor ([[Inyección de dependencias]]) |

En el front: cada componente de `ui/` hace una sola cosa (S) y los services aíslan a las páginas del formato del backend (D) → [[Patrón Adapter]].

Patrones: [[Patrones de diseño]] · Mapa: [[Arquitectura - Mapa]]
