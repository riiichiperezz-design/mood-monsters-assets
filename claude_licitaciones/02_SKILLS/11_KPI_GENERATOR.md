# SKILL 11 — KPI_GENERATOR

> **Propósito:** definir el sistema de indicadores del contrato: indicador, objetivo, fórmula, fuente, periodicidad, responsable, meta, umbral y acción correctora.
> **Cuándo cargarlo:** apartado de indicadores/seguimiento de la memoria o peticiones expresas de KPIs.
> **Cuándo no cargarlo:** análisis documental, presupuesto, revisión, cuestiones jurídicas.
> **Skills que lo utilizan:** MEMORY, DELIVERABLES (evidencias), VISUAL (dashboard), RED_TEAM (contraste de metas).
> **Palabras clave:** KPI, indicadores, seguimiento, metas, cuadro de mando.
> **Dependencias:** K-13, TPL_KPIS; objetivos y tareas del contrato (ANALYZER/MEMORY).
> **Prioridad:** alta. **Coste de contexto:** medio.
> **Resumen:** construye indicadores medibles y alcanzables ligados a los objetivos del contrato y a los compromisos de la memoria. Cada KPI tiene fórmula exacta, fuente de datos existente, periodicidad, responsable real, meta cuantificada, umbral de alerta y acción correctora predefinida. Distingue indicadores de ejecución (proceso), de resultado y de calidad de servicio, y evita metas temerarias que se conviertan en incumplimientos contractuales.

---

## 1. Nombre
KPI_GENERATOR.

## 2. Propósito
Un sistema de seguimiento que puntúe por concreción y sea gobernable durante la ejecución.

## 3. Responsabilidad única
Indicadores y su sistema de seguimiento. No fija los objetivos del servicio (vienen del pliego y la propuesta).

## 4. Cuándo se activa
Apartado de indicadores/seguimiento/calidad; «pon KPIs a este plan»; diseño de cuadro de mando.

## 5. Cuándo no se activa
Sin compromisos definidos que medir; en fases de análisis o presupuesto.

## 6. Entradas obligatorias
Objetivos y compromisos del contrato (pliego + memoria en curso); entregables definidos.

## 7. Entradas opcionales
KPIs exigidos por el pliego (prioridad absoluta), sistemas de datos disponibles del destino, acuerdos de nivel de servicio.

## 8. Salidas
Cuadro TPL_KPIS:

| Indicador | Objetivo | Fórmula | Fuente | Periodicidad | Responsable | Meta | Umbral | Acción correctora |
|---|---|---|---|---|---|---|---|---|

más propuesta de cuadro de mando (para VISUAL si se pide) y calendario de medición.

## 9. Flujo interno
1. Incorporar KPIs exigidos por el pliego tal cual (RI-01). 2. Mapear objetivos→resultados esperados→magnitudes medibles. 3. Seleccionar 2-4 KPIs por bloque (ejecución, resultado, calidad); evitar inflación de indicadores. 4. Definir fórmula exacta y fuente existente o creada por el propio contrato. 5. Meta realista [ESTIMACIÓN] con base declarada; umbral de alerta. 6. Acción correctora concreta por umbral. 7. Responsable real y periodicidad compatible con la gobernanza. 8. Verificar que ninguna meta crea un compromiso no asumible (RI-07).

## 10. Árbol de decisión
- ¿KPI exigido por el pliego? → Se adopta literal y se construye alrededor.
- ¿No existe fuente de datos? → O se crea dentro del contrato (con coste visible) o el KPI se descarta; nunca fuentes fantasma (RI-02).
- ¿Meta convertible en penalidad? → Advertir y proponer meta defendible.
- ¿Indicador de impacto fuera del control del adjudicatario (p. ej. llegadas de turistas)? → Reclasificar como indicador de contexto, no de compromiso.

## 11. Reglas prioritarias
Fórmula sin ambigüedad (numerador, denominador, unidad); fuente nombrada y accesible; meta con línea base o justificación; acción correctora ejecutable; pocos indicadores buenos antes que muchos vacíos (RI-16, RI-18).

## 12. Prohibiciones
Indicadores sin fuente; metas temerarias para puntuar (RI-14 espíritu: no prometer lo inejecutable); comprometer resultados que dependen de terceros como si fueran propios; duplicar el mismo KPI con nombres distintos.

## 13. Procedimiento paso a paso
Ver §9.

## 14. Casos especiales
Observatorios (los KPIs son el producto: separar KPIs del servicio y KPIs del destino); campañas (KPIs por canal con ventanas de medición); oficinas técnicas (SLA: plazos de respuesta y resolución).

## 15. Gestión de ambigüedad
Objetivo difuso del pliego → derivar el KPI de la actividad concreta comprometida y declarar la lectura.

## 16. Gestión de información faltante
Sin línea base → meta relativa («+15 % sobre el valor del primer trimestre medido») y obtención de línea base como actividad del plan.

## 17. Errores habituales
Confundir indicador con actividad; metas absolutas sin línea base; responsable «el equipo»; periodicidades imposibles; ignorar los KPIs del propio pliego.

## 18. Checklist
☐ KPIs del pliego incorporados ☐ 9 campos completos por indicador ☐ Fuentes existentes o creadas con coste visible ☐ Metas justificadas ☐ Acciones correctoras concretas ☐ Volumen contenido (calidad sobre cantidad).

## 19. Prompt operativo interno
«Incorpora los KPIs del pliego; deriva indicadores de ejecución, resultado y calidad de los compromisos; completa los 9 campos con fórmula exacta y fuente real; fija metas defendibles con umbral y acción correctora; verifica que ninguna meta genera compromiso inasumible.»

## 20. Ejemplos de activación
«KPIs para el plan de dinamización»; «apartado de seguimiento y evaluación»; «cuadro de mando del servicio».

## 21. Ejemplos de salida
Cuadro de 9 columnas con 8-12 indicadores agrupados, p. ej. «% informes entregados en plazo = informes en plazo/informes totales; fuente: registro de entregas; meta ≥ 95 %; umbral < 90 % → refuerzo de revisión interna y análisis de causas en el comité mensual».

## 22. Relación con otras Skills
Consume compromisos de MEMORY/PLANNING/DELIVERABLES; coordina periodicidad con GOVERNANCE; alimenta VISUAL y RED_TEAM.

## 23. Datos que puede compartir
Cuadro completo de indicadores.

## 24. Datos que no puede compartir
Márgenes o costes internos asociados al cumplimiento de metas.

## 25. Consumo de contexto
Medio.

## 26. Estrategia de ahorro de tokens
Trabajar por bloques de apartado; tabla directa; no repetir objetivos ya redactados (referenciarlos).

## 27. Criterios de calidad
Cada KPI es medible el primer mes de contrato con las fuentes declaradas; el conjunto cubre ejecución, resultado y calidad sin redundancia.

## 28. Criterios de parada
Cuadro entregado y verificado contra compromisos; o bloqueo por ausencia de compromisos que medir.
