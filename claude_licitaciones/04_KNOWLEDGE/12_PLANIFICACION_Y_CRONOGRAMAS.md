# K-12 — Planificación y cronogramas

> **Propósito:** doctrina de planificación defendible: fases, dependencias, ruta crítica y cronogramas.
> **Cuándo cargarlo:** desarrollo de planes de trabajo y cronogramas (Skill 08).
> **Cuándo no cargarlo:** en fases documentales, económicas o de revisión formal.
> **Skills que lo utilizan:** 08_PLANNING_ENGINE.
> **Palabras clave:** planificación, cronograma, ruta crítica, fases, dependencias.
> **Dependencias:** TPL_PLAN_DE_TRABAJO, TPL_CRONOGRAMA.
> **Prioridad:** media. **Coste de contexto:** medio.
> **Resumen:** método de planificación orientado a dos jueces: el evaluador (que puntúa credibilidad y dominio) y la realidad (que castiga el optimismo). Cubre la descomposición fases→actividades→dependencias, la estimación de duraciones con las esperas administrativas incluidas, la identificación de ruta crítica y holguras, el tratamiento de la estacionalidad turística y los periodos muertos de la administración, los planes para servicios recurrentes, y las técnicas de presentación del cronograma que puntúan (hitos del pliego visibles, validaciones explícitas, coherencia total con el resto de la memoria).

---

## 1. Los dos jueces del plan

El evaluador premia: lógica visible, hitos del pliego respetados, validaciones contempladas, coherencia con equipo y entregables. La realidad castiga: esperas no previstas, agosto, dependencias de terceros, arranques lentos. Un plan defendible satisface a ambos; un plan «bonito» que la ejecución incumplirá es un riesgo contractual (K-10) y de credibilidad (K-05 §5).

## 2. Descomposición

- **Fases** con lógica de servicio (arranque → núcleo → despliegue → seguimiento → cierre/transferencia). El arranque (kick-off, acceso a datos, ajuste de plan) consume 2-4 semanas reales: planificarlo.
- **Actividades** con verbo de acción, producto y responsable; granularidad: la que el evaluador pueda seguir (15-40 actividades en un contrato medio, no 200).
- **Dependencias** explícitas, incluidas las externas (datos del órgano, permisos, convocatorias de mesas). Las externas se marcan: son las que justifican después.

## 3. Duraciones honestas

- Estimar con el equipo real y sus dedicaciones (coherencia K-08).
- Incluir SIEMPRE los plazos de revisión y validación del órgano (proponer plazo si el pliego calla, K-04 §4): son la espera dominante en consultoría pública.
- Calendario real: agosto y navidades bajan la disponibilidad de la administración; los procesos participativos no convocan en verano; los eventos mandan sobre el plan.

## 4. Ruta crítica y holguras

Identificar la cadena que fija la duración total y declararla («la ruta crítica pasa por la cesión de datos → diagnóstico → plan de acción»). Las holguras se declaran y se administran (no se rellenan de promesas, RI-18). Presentar medidas de protección de la ruta crítica: arranque anticipado de gestiones externas, solapes controlados, recursos de refuerzo.

## 5. Estacionalidad turística

El plan de un contrato turístico se ancla al ciclo del destino: temporada alta (medición, no molestar al sector), temporada baja (talleres, planificación), ferias (FITUR en enero condiciona campañas y materiales), eventos propios del destino. Ignorar el ciclo delata inexperiencia sectorial ante el evaluador.

## 6. Servicios recurrentes y oficinas técnicas

Plan de doble capa: **flujos recurrentes** (informes mensuales, atención de peticiones con SLA) + **proyectos puntuales** (estudios, eventos) sobre la capacidad restante. Instrumentos: calendario anual tipo, matriz de capacidad mensual, procedimiento de priorización de peticiones. El cronograma clásico solo aplica a la capa de proyectos.

## 7. Presentación que puntúa

Tabla de fases/actividades (TPL_PLAN) + Gantt legible (VISUAL) con: hitos del pliego marcados, validaciones visibles, ruta crítica destacada. El Gantt y el texto cuentan exactamente lo mismo (la incoherencia texto↔visual es hallazgo clásico de Red Team). Nada de plazos ofertados por fórmula en el cronograma de la memoria (RI-05: si el plazo es criterio automático, el cronograma usa el plazo del pliego).

## 8. Errores caros

Arranque en frío (semana 1 produciendo); validaciones instantáneas; agosto laborable; 100 % de ocupación sin holgura; cronograma que revela mejoras automáticas; hitos de facturación ignorados.
