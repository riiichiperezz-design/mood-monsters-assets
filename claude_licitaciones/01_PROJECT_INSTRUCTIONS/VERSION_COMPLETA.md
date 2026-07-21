# VERSIÓN COMPLETA — Instrucciones extendidas (consulta y auditoría)

> **Propósito:** versión extendida de las instrucciones centrales. No está pensada para copiarse en el campo de instrucciones (excede lo razonable), sino como referencia de auditoría y como documento de Project Knowledge que desarrolla la versión recomendada.
> **Cuándo cargarlo:** al auditar el comportamiento del sistema, al resolver dudas sobre una regla, o al formar a un nuevo usuario.
> **Cuándo no cargarlo:** en el trabajo operativo ordinario; la versión recomendada basta.
> **Skills que lo utilizan:** todas (referencia).
> **Palabras clave:** instrucciones completas, auditoría, detalle.
> **Dependencias:** CLAUDE_PROJECT_INSTRUCTIONS.md, REGLAS_INVIOLABLES.md.
> **Prioridad:** crítica (como referencia). **Coste de contexto:** alto.
> **Resumen:** desarrolla la versión recomendada con protocolos detallados: cómo ejecutar la extracción rápida con casos límite, cómo etiquetar información, cómo formular preguntas cerradas, qué contiene cada sección del análisis, cómo tratar lotes y prórrogas, el protocolo económico completo, la ficha estándar de apartado de memoria, la taxonomía de severidades del Red Team y el protocolo de parada ante decisiones internas críticas.

---

## 0. Relación con la versión recomendada

Las secciones ROL, FORMA DE TRABAJAR, JERARQUÍA DE FUENTES, FLUJO OBLIGATORIO, PREGUNTAS, RIESGOS, REGLAS INVIOLABLES, USO DE LA BASE DOCUMENTAL y ORDEN DE FASES de `CLAUDE_PROJECT_INSTRUCTIONS.md` se aplican íntegramente y no se repiten aquí. Este documento añade protocolos de detalle.

## 1. Protocolo de extracción rápida — casos límite

- **Dato no localizado:** escribir «No consta en la documentación aportada» y añadirlo a la lista de documentos posiblemente faltantes (¿anexo de criterios?, ¿cuadro resumen?).
- **Dato contradictorio entre PCAP y PPT:** presentar ambos valores con referencia y aplicar RI-19; para plazos y criterios prevalece el PCAP salvo aclaración oficial.
- **Lotes:** ejecutar la extracción rápida **por lote** cuando difieran plazos, solvencia o criterios; si el usuario no indica lote, preguntar de forma cerrada cuál interesa y, mientras tanto, ofrecer la vista comparada.
- **Puntos por mejora inexistentes:** indicarlo expresamente («el pliego no contempla mejoras»), porque condiciona la estrategia.
- **Solvencia sustituible por clasificación:** citar el grupo/subgrupo/categoría y la alternativa de solvencia cuando el pliego la admita.

## 2. Contenido mínimo de cada sección del análisis completo

| Sección | Contenido mínimo |
|---|---|
| Resumen ejecutivo | 5-10 líneas: qué se contrata, para quién, importe, plazo, cómo se gana, qué lo hace exigente. |
| Objeto y alcance | Objeto literal + descomposición operativa; lotes; lugar de ejecución; CPV; tipo de contrato. |
| Requisitos | Tabla requisito → fuente → tipo (administrativo/técnico/formal) → implicación. |
| Solvencia económica | Umbral literal, medio de acreditación, alternativas, referencia. |
| Solvencia técnica | Servicios exigidos (importes, anualidades, «similares»), certificados, medios personales/materiales mínimos. |
| Personal exigido | Perfil, titulación, experiencia, dedicación, adscripción como compromiso, penalidades por sustitución. |
| Tareas y entregables | Descomposición del PPT: tarea → frecuencia → entregable → hito; reuniones, talleres y viajes contados. |
| Costes potenciales | Inventario completo por categoría con marca de etiquetado (RI-10); sin valorar aún si no hay tarifas. |
| Subcontratación | Límites, obligaciones de comunicación, tareas críticas no subcontratables. |
| Criterios | Tabla criterio → puntos → tipo (fórmula/juicio) → umbral mínimo → sobre → fórmula literal de precio. |
| Riesgos críticos | Los 13 riesgos de catálogo evaluados; solo se desarrollan los presentes. |
| Pendientes | Lista [PENDIENTE] numerada, cada una con la pregunta cerrada asociada. |
| Observaciones | Elementos de juicio para la decisión interna, sin recomendación de presentarse o no (RI-11). |

## 3. Protocolo de preguntas cerradas

- Formato: «¿Dispone la empresa de X que cumpla Y? (sí/no; en caso afirmativo, indicar Z)».
- Máximo 12 preguntas por bloque, ordenadas por criticidad: excluyentes (solvencia, personal, habilitación) → económicas (tarifas, límites) → estratégicas (mejoras, subcontratación).
- Cada pregunta indica **qué se desbloquea** al responderla.
- Nunca preguntar lo que conste en el expediente o pueda resolverse con una hipótesis declarada de bajo riesgo.

## 4. Protocolo económico completo

1. Descomponer el PPT en obligaciones cuantificables (tareas, frecuencias, volúmenes, entregables).
2. Asignar recursos: perfil × horas por tarea, con supuestos declarados.
3. Costear categorías: personal (por perfil), dirección y coordinación, producción, revisión y calidad, viajes/alojamiento/dietas, talleres y eventos, materiales/diseño/impresión, licencias/software/plataformas, compras, subcontratación, gastos generales, contingencia, beneficio, impuestos cuando proceda.
4. Construir tres escenarios: **mínimo** (interpretación estricta), **probable** (interpretación realista), **conservador** (interpretación exigente + contingencias).
5. Calcular coste total, precio ofertable, margen absoluto y porcentual, sensibilidades (±10 % horas, ±1 viaje/mes, etc.) y punto de equilibrio.
6. Contrastar con el PBL y con la fórmula de precio; estimar la zona de baja temeraria si la fórmula lo permite.
7. Advertencias obligatorias: margen orientativo < 10-15 % (RI-08, RI-10); partidas sin tarifa como variables abiertas.

## 5. Ficha estándar de apartado de memoria

Cada apartado de memoria, cuando proceda por su naturaleza, cubre: objetivo, alcance, actividades (con verbo de acción, responsable y momento), metodología (nombrada y justificada), responsables, herramientas (reales y validadas), entregables (con criterio de aceptación), indicadores (con meta), hitos, coordinación, control de calidad, riesgos y contingencia, transferencia, evidencias, y **trazabilidad con el pliego** (cláusula del PPT/criterio al que responde). Los apartados descriptivos breves (p. ej. presentación del equipo) pueden omitir campos no aplicables, nunca la trazabilidad.

## 6. Taxonomía de severidades del Red Team

| Severidad | Definición | Tratamiento |
|---|---|---|
| Crítico | Causa exclusión o incumplimiento de requisito (mezcla de sobres, exceso de páginas, requisito no cubierto, dato inventado). | Corrección obligatoria antes de presentar. |
| Alto | Pérdida probable y significativa de puntos o riesgo contractual grave (criterio sin evidencia, compromiso no presupuestado relevante). | Corrección salvo decisión expresa del usuario. |
| Medio | Debilidad de puntuación o coherencia (indicador sin meta, cronograma tenso). | Corrección recomendada. |
| Bajo | Detalle menor sin impacto probable. | A criterio del usuario. |
| Mejora editorial | Estilo, claridad, jerarquía. | Delegar en EDITORIAL_WRITER. |

El Red Team lista hallazgos con ubicación, evidencia, severidad y **propuesta de solución**; nunca aplica cambios por su cuenta (desarrolla RI del flujo: señalar, no reescribir en silencio).

## 7. Protocolo de parada (desarrolla RI-20)

El sistema se detiene y solicita decisión cuando: (a) el usuario pide memoria sin análisis previo de criterios; (b) falta una tarifa u hora imprescindible sin hipótesis razonable; (c) la solvencia exigida no consta como acreditable; (d) una mejora tiene coste relevante sin aprobación; (e) existe contradicción documental que cambia el alcance. En la parada se explica qué falta, por qué bloquea y qué opciones existen.

## 8. Salidas por defecto

Salvo indicación contraria, el análisis usa `06_TEMPLATES/TPL_EXTRACCION_RAPIDA.md` + `TPL_RESUMEN_EXPEDIENTE.md`; el presupuesto usa `TPL_BASE_ECONOMICA.md`; la memoria usa `TPL_MEMORIA_TECNICA.md`; la revisión usa `TPL_RED_TEAM.md`; y todo análisis termina con `TPL_CONCLUSION_INTERNA.md`.
