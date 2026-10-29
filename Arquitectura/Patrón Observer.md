---
tags: [capa/transversal]
---

# Patrón Observer

**Qué es:** objetos que "escuchan" y reaccionan cuando algo cambia.

**Dónde:**
- **React Context:** al cambiar el usuario en `AuthContext`, todos los componentes que usan `useAuth` se vuelven a pintar.
- **Evento del navegador:** `api.ts` emite `modofriki:unauthorized` ante un 401 y el contexto de auth lo escucha para cerrar sesión.

**Por qué:** el cliente HTTP no necesita conocer al contexto; solo avisa.

Capa: [[Frontend - Estado global]] · [[Frontend - Cliente API]] · Índice: [[Patrones de diseño]]
