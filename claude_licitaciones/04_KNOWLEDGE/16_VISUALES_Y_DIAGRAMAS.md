# K-16 — Visuales y diagramas

> **Propósito:** criterios y técnicas para visuales que aportan puntuación en ofertas.
> **Cuándo cargarlo:** producción de visuales (Skill 06).
> **Cuándo no cargarlo:** en cualquier fase sin producción visual.
> **Skills que lo utilizan:** 06_VISUAL_DESIGNER.
> **Palabras clave:** visuales, diagramas, SVG, Gantt, infografía.
> **Dependencias:** datos del módulo de origen (plan, gobernanza, KPIs).
> **Prioridad:** media. **Coste de contexto:** medio.
> **Resumen:** doctrina visual del sistema: cuándo un visual gana puntos y cuándo resta espacio, la tabla formato↔tipo de información, los estándares de legibilidad para evaluación (impresión, B/N, tamaños mínimos), las reglas de coherencia texto↔visual, las especificaciones técnicas de producción (SVG editable, mermaid) y la lista de vulneraciones visuales de separación de sobres. Complementa la Skill 06 con el criterio de fondo: un visual es un párrafo comprimido, y se juzga como tal.

---

## 1. Cuándo sí y cuándo no

**Sí:** cuando comprime información evaluable que en texto ocuparía más o se entendería peor (un plan de 20 actividades, un modelo de gobernanza a 3 niveles, un flujo con 4 actores). **No:** iconos decorativos, «conceptos» abstractos con flechas, stock visual de consultoría (RI-16). Prueba rápida: si el visual desapareciera, ¿el evaluador perdería información? Si no, fuera (con límite de páginas, cada visual desplaza texto evaluable).

## 2. Formato según información

| Información | Formato |
|---|---|
| Secuencia temporal | Cronograma / Gantt |
| Estructura de responsabilidad | Organigrama / RACI visual |
| Proceso con actores | Swimlane |
| Proceso lineal | Diagrama de flujo |
| Relaciones entre agentes | Mapa de actores (centralidad = influencia) |
| Mejora continua | Ciclo (PDCA) |
| Sistema técnico | Diagrama de arquitectura por capas |
| Seguimiento | Mockup de cuadro de mando |
| Territorio | Mapa esquemático (comarcas, rutas, sedes) |

## 3. Estándares de legibilidad (evaluación real)

- Legible **impreso a tamaño de inserción** (la mesa imprime): mínimo efectivo ~8-9 pt en el papel; respetar el mínimo tipográfico del pliego también en los gráficos (RI-14 — es un clásico de exclusión parcial).
- **Funciona en B/N:** el color refuerza, nunca es el único código (patrones, etiquetas).
- Máximo ~7 elementos por nivel visual; si hay más, agrupar o dividir en dos visuales.
- Título autoexplicativo + leyenda + nota de fuente/trazabilidad («elaboración propia a partir del PPT, cláusula 5; responde al criterio 2.1»).

## 4. Coherencia texto↔visual (pares de K-14 §3)

El visual dice exactamente lo que dice el texto: mismas fases, fechas, roles, cifras y terminología. Regla de producción: el visual se genera DESPUÉS del contenido aprobado, desde sus datos (nunca «se dibuja algo» y luego se redacta alrededor). Cambio en el texto → regenerar el visual (registro de visuales con su fuente).

## 5. Especificaciones técnicas

- **SVG editable:** viewBox definido; texto como `<text>` (no curvas); grupos `<g id>` semánticos; fuentes sans-serif de sistema; sin dependencias externas. Permite al usuario retocar en Illustrator/Inkscape.
- **Mermaid:** para estructuras estándar (gantt, flowchart, sequence) cuando el destino lo soporte o como borrador previo al SVG.
- Datos ilustrativos SIEMPRE marcados («datos de ejemplo»); placeholders `[PENDIENTE]` visibles (RI-10: un gráfico con cifras inventadas de aspecto real es información inventada).

## 6. Sobres: vulneraciones visuales típicas (RI-05)

Gantt que muestra el plazo reducido ofertado como criterio automático · organigrama que incluye el personal adicional de una mejora automática · mockup de dashboard con presupuesto o precios · infografía de «propuesta de valor» que cuantifica mejoras. Verificación visual específica en CHK_SOBRES.

## 7. Errores caros

Visual espectacular incoherente con el texto (Red Team lo caza; el evaluador también) · microtipografía ilegal · gráficos de datos sin fuente · decorar apartados débiles en vez de reforzar su contenido (K-03) · SVG con texto en curvas que nadie puede editar la víspera de presentar.
