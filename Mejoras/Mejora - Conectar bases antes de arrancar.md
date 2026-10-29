---
tags: [capa/mejora]
---

# Mejora - Conectar bases antes de arrancar

**Categoría:** 🟢 Segura

**Hoy:** en `src/index.ts`, `app.listen()` arranca primero y recién dentro del callback conecta a PostgreSQL y MongoDB.
```ts
app.listen(port, async () => {
	await connectDatabase();
	await connectMongoDB();
});
```
Durante esos segundos el servidor ya acepta peticiones que pueden fallar con 500.

**Propuesta:** conectar primero y escuchar después.
```ts
async function start() {
	await connectDatabase();
	await connectMongoDB();
	app.listen(port, () => logger.http(`Server running on port ${port}`));
}
start();
```
Si una base falla, `connectDatabase` ya hace `process.exit(1)`, así que Render reinicia el servicio.

**Riesgo:** casi ninguno; son 5 líneas en un solo archivo.

Relacionado: [[Mejora - Health check real]] · [[Despliegue y CI-CD]] · Índice: [[Mejoras - Mapa]]
