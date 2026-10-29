---
tags: [ia/flujo]
---

# Buenas prácticas aprendidas

Lo que muestra la configuración de ModoFriki sobre trabajar con agentes:

1. **Un dueño por archivo** evita que los agentes se pisen ([[Propiedad de archivos por rol]]).
2. **Planificar antes de implementar** y fijar contratos (firmas, `res.locals`) antes de paralelizar.
3. **Las instrucciones piden; los hooks obligan.** Lo crítico (borrar la BD, push a main) se bloquea con código ([[Hooks de Claude Code]]).
4. **Revisión independiente:** quien implementa no se revisa a sí mismo ([[Agente reviewer]], [[Agente security]]).
5. **Nunca afirmar sin ejecutar:** cada entrega reporta validaciones con su resultado real.
6. **Límite de rondas** (2) para que la IA no se quede corrigiendo sin fin.
7. **Humano en el bucle** para integrar a `dev`, `qa` y `main`.
8. **Mantener el contexto al día:** un archivo de reglas viejo es peor que ninguno ([[Inconsistencias en la configuración de IA]]).

Mapa: [[Desarrollo con IA - Mapa]]
