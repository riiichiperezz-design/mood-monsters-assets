# CONTEXT_LOADING_GUIDE — Estrategia de recuperación selectiva

> **Propósito:** reglas operativas para no exceder el contexto de Claude: qué cargar, cuándo y cuánto.
> **Cuándo cargarlo:** al enrutar peticiones complejas, al instalar el sistema y al mantenerlo.
> **Cuándo no cargarlo:** en peticiones simples ya enrutadas.
> **Skills que lo utilizan:** 00_KNOWLEDGE_ROUTER.
> **Palabras clave:** contexto, qué cargar, tokens, presupuesto de contexto.
> **Dependencias:** MANIFEST.json, FILE_INDEX.md. **Prioridad:** crítica. **Coste:** bajo.
> **Resumen:** define el presupuesto de contexto por turno, las combinaciones de carga por clase de petición, las exclusiones obligatorias, el orden de prioridad cuando hay que recortar y las técnicas de ahorro (trabajar sobre salidas previas, un playbook por vez, redacción por lotes). Es el complemento operativo de la tabla de enrutado del Router.

---

## 1. Principio

Los documentos del expediente (pliegos) son el gasto de contexto dominante e irrenunciable. Todo lo demás compite por el espacio restante: **se carga lo mínimo suficiente para la petición actual** (RI-17). Cada documento del sistema declara en cabecera su propósito, activación y coste: esa cabecera es la unidad de decisión del Router.

## 2. Presupuesto orientativo por turno

Instrucciones del Project (siempre) + expediente o salidas previas + **máximo:** 1 workflow de tramo + 3 Skills + 3 documentos de conocimiento + 1 playbook + las plantillas de la salida a producir + 1 ejemplo (solo primera vez). Si la petición pide más: dividir en turnos siguiendo el orden del workflow.

## 3. Combinaciones de carga por clase (referencia rápida)

| Clase (Router §10) | Cargar | Nunca cargar |
|---|---|---|
| A Análisis | ANALYZER + WF_01/02 + TPL_EXTRACCION + TPL_RESUMEN (+K-01 si hace falta método) | Playbooks, Red Team, memoria, K-18, visuales |
| B Solvencia/personal | ANALYZER + WF_03 + K-07/K-08 + matrices | Visuales, presupuesto, playbooks, K-02/03/05 |
| C Criterios | SCORING + WF_04 + K-05/K-06 + TPL_MATRIZ_CRITERIOS | Presupuesto detallado, playbooks, Red Team |
| D Presupuesto | BUDGET + WF_05/06 + K-09 + TPL_BASE_ECONOMICA + CHK_COSTES | Playbooks, memoria, K-18, visuales |
| E Memoria | SCORING→MEMORY + WF_07 + K-02/K-03 + TPL_MEMORIA + 1 playbook (+Skill de apartado según toque) | K-18 (salvo duda), Red Team hasta borrador, playbooks ajenos |
| F Mejoras | SCORING + BUDGET + WF_08 + K-06 + CHK_SOBRES | Memoria, playbooks, visuales |
| G Red Team | RED_TEAM + WF_09 + K-14 + TPL_RED_TEAM + CHK_RED_TEAM/SOBRES | Playbooks, K-01/02, visuales |
| H Visuales | VISUAL + K-16 + datos de origen | K-18, K-09, K-07, playbooks, Red Team |
| I Jurídica | PROCUREMENT + K-18 + cláusulas relevantes | Playbooks, visuales, plantillas de producción |
| J Edición | EDITORIAL + K-17 + texto e invariantes | Todo lo demás |

## 4. Orden de recorte (cuando no cabe todo)

1. Ejemplos (prescindibles tras la primera vez) → 2. Documentos de conocimiento (la Skill resume su doctrina) → 3. Workflow de tramo (WF_MASTER basta) → 4. Playbook (usar PB_11 y los patrones transversales) → **Nunca se recortan:** instrucciones, REGLAS_INVIOLABLES, la plantilla de la salida y los datos del expediente necesarios.

## 5. Técnicas de ahorro

- **Trabajar sobre salidas previas:** el análisis hecho en la conversación sustituye a los pliegos para las fases siguientes; no recargar los PDF para presupuestar o redactar.
- **Un playbook por vez** (RI-17; híbridos: consecutivo, no simultáneo — PB_11 §2).
- **Redacción por lotes** de 2-4 apartados con las Skills de apartado cargadas solo en su turno.
- **Revisión por bloques** en Red Team con registro acumulado de hallazgos.
- **PB_11 y FILE_INDEX como filtros baratos** antes de cargar documentos densos.
- **No citar, referenciar:** los módulos se citan por nombre e ID de regla (RI-nn), no se transcriben.

## 6. Señales de sobrecarga (actuar)

Respuestas que repiten doctrina en lugar de aplicarla · re-análisis de lo ya analizado · mezcla de vocabularios de varios playbooks · pérdida de datos del expediente al final de turnos largos. Acción: cerrar el turno, consolidar la salida y continuar en el siguiente con solo las salidas previas necesarias.
