# SKILL 06 — VISUAL_DESIGNER

> **Propósito:** generar visuales con valor informativo para la oferta: diagramas de proceso, cronogramas, Gantt, organigramas, RACI, swimlanes, mapas de actores, ciclos de mejora, arquitecturas, dashboards, flujos de gobernanza y SVG editables.
> **Cuándo cargarlo:** petición expresa de un visual o necesidad detectada por MEMORY/PLANNING/GOVERNANCE (clase H).
> **Cuándo no cargarlo:** análisis de solvencia, presupuestación, cuestiones jurídicas, primera lectura (exclusiones expresas del Router).
> **Skills que lo utilizan:** MEMORY, PLANNING, GOVERNANCE, KPI (dashboards).
> **Palabras clave:** SVG, diagrama, Gantt, organigrama, RACI, esquema, gráfico, visual.
> **Dependencias:** K-16; datos del módulo de origen (plan, gobernanza, KPIs).
> **Prioridad:** alta. **Coste de contexto:** medio.
> **Resumen:** produce visuales que condensan información evaluable —nunca decoración—. Cada visual parte de datos reales del expediente o de la propuesta, declara su fuente, cabe en los límites de la memoria y es editable (SVG o mermaid). Incluye criterios de elección de formato, estándares de legibilidad en impresión B/N y reglas para no introducir datos de otros sobres en los gráficos.

---

## 1. Nombre
VISUAL_DESIGNER.

## 2. Propósito
Aumentar puntuación y legibilidad condensando información compleja en visuales precisos y editables.

## 3. Responsabilidad única
Diseño y producción de visuales. No genera el contenido de fondo (lo reciben de otras Skills) ni lo altera.

## 4. Cuándo se activa
«Hazme un SVG/Gantt/organigrama»; MEMORY detecta un apartado que gana con visual; PLANNING entrega cronograma.

## 5. Cuándo no se activa
Cuando el visual no aporta información (decoración, RI-16); en fases de análisis puro.

## 6. Entradas obligatorias
Datos estructurados a representar (fases y fechas; roles; flujos; indicadores) y el destino (memoria con límite de páginas, anexo, presentación).

## 7. Entradas opcionales
Identidad gráfica de la empresa, restricciones del pliego (B/N, tamaño de fuente mínimo).

## 8. Salidas
SVG editable autocontenido y/o diagrama mermaid; leyenda; nota de fuente de datos; recomendación de tamaño de inserción.

## 9. Flujo interno
1. Verificar que el visual aporta información evaluable. 2. Elegir formato según el dato (§10). 3. Verificar que ningún dato pertenece a otro sobre (RI-05). 4. Construir con jerarquía visual clara y textos legibles a tamaño de impresión. 5. Validar contra límites del pliego (fuente mínima, B/N). 6. Entregar con leyenda y fuente.

## 10. Árbol de decisión (elección de formato)
- Secuencia temporal → cronograma/Gantt. - Responsabilidades → RACI/organigrama. - Flujo con actores → swimlane. - Relaciones entre agentes → mapa de actores. - Mejora continua → ciclo PDCA. - Sistema/plataforma → arquitectura. - Seguimiento → dashboard/mockup de cuadro de mando. - Proceso lineal → diagrama de proceso.

## 11. Reglas prioritarias
Todo texto legible impreso a tamaño real; máximo ~7 elementos por nivel visual; los colores nunca son el único portador de significado (imprimible en B/N); cada visual referencia el apartado y la cláusula/criterio al que sirve; SVG con capas/grupos nombrados para edición.

## 12. Prohibiciones
Decoración sin datos (RI-16); inventar hitos, fechas o roles no confirmados (RI-02); incluir precios, plazos ofertados por fórmula o mejoras automáticas en visuales de la memoria (RI-05); tipografías por debajo del mínimo del pliego (RI-14).

## 13. Procedimiento paso a paso
Ver §9; para SVG: viewBox definido, fuentes seguras (sans-serif del sistema), textos como `<text>` (no trazados), grupos `<g id="...">` por bloque.

## 14. Casos especiales
- **Límite severo de páginas:** visuales que sustituyen texto, no que lo duplican.
- **Pliego que exige memoria «sin identificación»:** visuales sin logotipos ni marcas.
- **Datos aún [PENDIENTE]:** placeholders visibles `«[PENDIENTE]»`, nunca cifras simuladas de aspecto real.

## 15. Gestión de ambigüedad
Si el dato de origen es ambiguo, devolver la duda al módulo de origen; no «resolverla» gráficamente.

## 16. Gestión de información faltante
Entregar la estructura del visual con placeholders y lista de datos necesarios.

## 17. Errores habituales
Gantt con actividades sin dependencia con el plan del texto; organigramas con perfiles no ofertados; dashboards con KPIs que no existen en el apartado de indicadores; SVG con texto convertido a curvas (ineditable).

## 18. Checklist
☐ Aporta información evaluable ☐ Formato adecuado al dato ☐ Coherente con el texto de la memoria ☐ Legible impreso y en B/N ☐ Sin datos de otros sobres ☐ Editable ☐ Fuente y trazabilidad indicadas.

## 19. Prompt operativo interno
«Con los datos estructurados recibidos, elige formato según §10, construye SVG/mermaid legible y editable, verifica coherencia con el texto y separación de sobres, y entrega con leyenda y fuente.»

## 20. Ejemplos de activación
«Genera el Gantt de las 4 fases»; «necesito un swimlane del circuito de validación de entregables»; «SVG del modelo de gobernanza».

## 21. Ejemplos de salida
Bloque ```mermaid gantt``` o `<svg viewBox="0 0 1200 600">…</svg>` con grupos nombrados, más leyenda y nota: «Fuente: plan de trabajo, apartado 4; responde al criterio 2.1».

## 22. Relación con otras Skills
Recibe datos de PLANNING, GOVERNANCE, KPI, MEMORY; sus salidas se insertan vía MEMORY; RED_TEAM verifica coherencia texto↔visual.

## 23. Datos que puede compartir
Visuales, leyendas, recomendaciones de inserción.

## 24. Datos que no puede compartir
Nada procedente de la base económica en visuales de memoria (RI-05).

## 25. Consumo de contexto
Medio (datos de origen + esta Skill; no necesita pliegos).

## 26. Estrategia de ahorro de tokens
Mermaid para estructuras estándar (más compacto); SVG solo cuando se pida editable o el formato lo exija; reutilizar estilos entre visuales del mismo expediente.

## 27. Criterios de calidad
Un evaluador entiende el visual en 15 segundos sin leer el texto; cero incoherencias con el plan escrito.

## 28. Criterios de parada
Visual entregado y validado contra checklist; o devolución al módulo de origen por datos insuficientes.
