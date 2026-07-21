# FILE_INDEX — Índice maestro del sistema

> **Propósito:** índice maestro legible de todos los módulos, derivado de `MANIFEST.json`.
> **Cuándo cargarlo:** al enrutar una petición cuando el manifiesto no esté disponible, o al mantener el sistema.
> **Cuándo no cargarlo:** durante la redacción de contenidos; el Router ya conoce el mapa.
> **Skills que lo utilizan:** 00_KNOWLEDGE_ROUTER.
> **Prioridad:** crítica. **Coste de contexto:** bajo.
> **Resumen:** listado completo de los 97 módulos del sistema con su tipo, propósito, prioridad y coste de contexto, agrupados por carpeta. Es la vista humana del manifiesto: cualquier alta, baja o cambio de un archivo debe reflejarse aquí y en MANIFEST.json en el mismo cambio. El Knowledge Router lo usa como tabla de enrutado rápida cuando necesita decidir qué documentos consultar sin cargar el JSON completo.


## 00_README — Documentación general

| Archivo | Tipo | Propósito | Prioridad | Coste |
|---|---|---|---|---|
| `README_GENERAL.md` | readme | Presentación general del sistema y de su filosofía de uso. | low | low |
| `INSTALACION_EN_CLAUDE_PROJECTS.md` | readme | Pasos para instalar el sistema en Claude Projects con carga selectiva. | low | low |
| `GUIA_DE_USO.md` | readme | Manual de uso diario: comandos, fases y ejemplos de peticiones. | low | low |
| `MAPA_DEL_SISTEMA.md` | readme | Arquitectura completa del sistema y relaciones entre módulos. | low | low |

## 01_PROJECT_INSTRUCTIONS — Instrucciones del Project

| Archivo | Tipo | Propósito | Prioridad | Coste |
|---|---|---|---|---|
| `CLAUDE_PROJECT_INSTRUCTIONS.md` | instruction | Instrucciones centrales recomendadas para copiar en el Project. | critical | medium |
| `VERSION_CORTA.md` | instruction | Versión mínima de las instrucciones para contextos ajustados. | critical | medium |
| `VERSION_COMPLETA.md` | instruction | Versión extendida de las instrucciones, para auditoría y consulta. | critical | medium |
| `REGLAS_INVIOLABLES.md` | instruction | Las 20 reglas transversales del sistema; fuente única de verdad. | critical | medium |

## 02_SKILLS — Skills

| Archivo | Tipo | Propósito | Prioridad | Coste |
|---|---|---|---|---|
| `00_KNOWLEDGE_ROUTER.md` | skill | Clasifica la petición, selecciona Skills y documentos, controla el orden de fases. | high | medium |
| `01_EXPEDIENT_ANALYZER.md` | skill | Extrae y estructura todos los elementos del expediente (PCAP, PPT, anexos). | high | medium |
| `02_BUDGET_BUILDER.md` | skill | Convierte obligaciones del pliego en costes, escenarios y márgenes. | high | medium |
| `03_MEMORY_WRITER.md` | skill | Redacta la memoria técnica trazada contra los criterios de adjudicación. | high | medium |
| `04_SCORING_OPTIMIZER.md` | skill | Matriz criterio-evidencia-acción y estrategia de puntuación sin mezclar sobres. | high | medium |
| `05_RED_TEAM_REVIEWER.md` | skill | Revisión adversarial de la memoria con hallazgos clasificados por severidad. | high | medium |
| `06_VISUAL_DESIGNER.md` | skill | Genera diagramas, cronogramas, RACI y SVG con valor informativo. | high | medium |
| `07_GOVERNANCE_DESIGNER.md` | skill | Define roles, comités, escalado y circuitos de aprobación del contrato. | high | medium |
| `08_PLANNING_ENGINE.md` | skill | Desarrolla fases, dependencias, ruta crítica, hitos y holguras. | high | medium |
| `09_RISK_MANAGER.md` | skill | Matriz de riesgos con causa, probabilidad, impacto, prevención y contingencia. | high | medium |
| `10_DELIVERABLES_GENERATOR.md` | skill | Fichas de entregables con criterios de aceptación y validación. | high | medium |
| `11_KPI_GENERATOR.md` | skill | Indicadores con fórmula, fuente, meta, umbral y acción correctora. | high | medium |
| `12_TOURISM_PLAYBOOKS.md` | skill | Selecciona y aplica el playbook turístico que corresponde al objeto del contrato. | high | medium |
| `13_SPANISH_PROCUREMENT_EXPERT.md` | skill | Interpreta el expediente conforme a la LCSP sin sustituir asesoramiento jurídico. | high | medium |
| `14_EDITORIAL_WRITER.md` | skill | Mejora claridad, cohesión y tono sin alterar el significado técnico. | high | medium |

## 03_WORKFLOWS — Workflows

| Archivo | Tipo | Propósito | Prioridad | Coste |
|---|---|---|---|---|
| `WF_01_RECEPCION_EXPEDIENTE.md` | workflow | Recepción del expediente e inventario documental (estados 0-1). | high | low |
| `WF_02_ANALISIS_DOCUMENTAL.md` | workflow | Extracción rápida y análisis completo del expediente (estados 2-3). | high | low |
| `WF_03_SOLVENCIA.md` | workflow | Validación de solvencia económica y técnica y del personal (estados 4-5). | high | low |
| `WF_04_CRITERIOS_ADJUDICACION.md` | workflow | Análisis de criterios de adjudicación y umbrales (estado 6). | high | low |
| `WF_05_VIABILIDAD_ECONOMICA.md` | workflow | Identificación de costes y preguntas internas (estados 7-8). | high | low |
| `WF_06_PRESUPUESTO.md` | workflow | Construcción de la base económica y escenarios (estado 9). | high | low |
| `WF_07_MEMORIA_TECNICA.md` | workflow | Estrategia de puntuación, índice y redacción de memoria (estados 10-12). | high | low |
| `WF_08_MEJORAS.md` | workflow | Tratamiento de mejoras y criterios automáticos sin mezclar sobres. | high | low |
| `WF_09_REVISION_RED_TEAM.md` | workflow | Revisión de cobertura y Red Team con correcciones (estados 13-15). | high | low |
| `WF_10_CIERRE_Y_ENTREGA.md` | workflow | Validación formal y cierre del expediente (estados 16-17). | high | low |
| `WF_MASTER.md` | workflow | Máquina de estados 0-17: entradas, salidas, bloqueos y transiciones permitidas. | high | low |

## 04_KNOWLEDGE — Base de conocimiento

| Archivo | Tipo | Propósito | Prioridad | Coste |
|---|---|---|---|---|
| `01_METODOLOGIA_ANALISIS_EXPEDIENTES.md` | knowledge | Método completo de lectura y explotación de expedientes de contratación. | medium | high |
| `02_ARQUITECTURA_MEMORIA_TECNICA.md` | knowledge | Estructura, arquitectura y patrones de memorias técnicas ganadoras. | medium | high |
| `03_INGENIERIA_DE_EVIDENCIAS.md` | knowledge | Cómo transformar afirmaciones en evidencias verificables y puntuables. | medium | high |
| `04_INGENIERIA_DE_ENTREGABLES.md` | knowledge | Diseño de entregables con contenido, aceptación y validación. | medium | high |
| `05_OPTIMIZACION_JUICIO_VALOR.md` | knowledge | Técnicas para maximizar puntuación en criterios sujetos a juicio de valor. | medium | high |
| `06_CRITERIOS_AUTOMATICOS_Y_MEJORAS.md` | knowledge | Criterios automáticos, fórmulas de precio, mejoras y separación de sobres. | medium | high |
| `07_SOLVENCIA_Y_ACREDITACION.md` | knowledge | Solvencia económica y técnica: medios, umbrales y acreditación. | medium | high |
| `08_PERSONAL_Y_EQUIPO.md` | knowledge | Requisitos de personal, adscripción de medios y perfiles de equipo. | medium | high |
| `09_PRESUPUESTACION_Y_RENTABILIDAD.md` | knowledge | Método de presupuestación, escenarios, márgenes y baja temeraria. | medium | high |
| `10_RIESGOS_CONTRACTUALES.md` | knowledge | Catálogo de riesgos contractuales y su tratamiento. | medium | high |
| `11_GOBERNANZA_Y_COORDINACION.md` | knowledge | Modelos de gobernanza, comités y coordinación con el órgano de contratación. | medium | high |
| `12_PLANIFICACION_Y_CRONOGRAMAS.md` | knowledge | Planificación, dependencias, ruta crítica y cronogramas defendibles. | medium | high |
| `13_KPIS_Y_SEGUIMIENTO.md` | knowledge | Diseño de indicadores y sistemas de seguimiento del contrato. | medium | high |
| `14_CALIDAD_Y_CONTROL.md` | knowledge | Control de calidad de ofertas: cobertura, coherencia y cumplimiento formal. | medium | high |
| `15_TRANSFERENCIA_Y_CIERRE.md` | knowledge | Transferencia de conocimiento, devolución y cierre de contratos. | medium | high |
| `16_VISUALES_Y_DIAGRAMAS.md` | knowledge | Criterios y técnicas para visuales que aportan puntuación. | medium | high |
| `17_REDACCION_EDITORIAL.md` | knowledge | Estilo editorial: claridad, verbos de acción, jerarquía y tono ejecutivo. | medium | high |
| `18_CONTRATACION_PUBLICA_ESPAÑOLA.md` | knowledge | Marco LCSP: procedimientos, plazos, sobres, solvencia, bajas y recursos. | medium | high |

## 05_PLAYBOOKS_TURISMO — Playbooks turísticos

| Archivo | Tipo | Propósito | Prioridad | Coste |
|---|---|---|---|---|
| `PB_01_DESTINOS_TURISTICOS_INTELIGENTES.md` | playbook | Patrones para contratos de Destinos Turísticos Inteligentes (DTI). | medium | high |
| `PB_02_PLANIFICACION_TURISTICA.md` | playbook | Patrones para planes estratégicos y de sostenibilidad turística. | medium | high |
| `PB_03_MARKETING_Y_PROMOCION.md` | playbook | Patrones para contratos de marketing y promoción de destinos. | medium | high |
| `PB_04_OBSERVATORIOS_TURISTICOS.md` | playbook | Patrones para observatorios e inteligencia turística. | medium | high |
| `PB_05_EVENTOS_Y_ACCIONES_PRESENCIALES.md` | playbook | Patrones para eventos, ferias y acciones presenciales. | medium | high |
| `PB_06_TRANSFORMACION_DIGITAL.md` | playbook | Patrones para transformación digital de destinos y empresas turísticas. | medium | high |
| `PB_07_FONDOS_EUROPEOS.md` | playbook | Patrones para asistencias vinculadas a fondos europeos (PRTR, FEDER). | medium | high |
| `PB_08_OFICINAS_TECNICAS.md` | playbook | Patrones para oficinas técnicas y asistencias técnicas continuadas. | medium | high |
| `PB_09_PARTICIPACION_Y_TALLERES.md` | playbook | Patrones para procesos participativos y talleres. | medium | high |
| `PB_10_COMUNICACION_Y_CONTENIDOS.md` | playbook | Patrones para comunicación, contenidos y redes de destinos. | medium | high |
| `PB_11_PATRONES_POR_TIPO_DE_CONTRATO.md` | playbook | Tabla de enrutado: qué playbook aplicar según el objeto del contrato. | medium | high |

## 06_TEMPLATES — Plantillas

| Archivo | Tipo | Propósito | Prioridad | Coste |
|---|---|---|---|---|
| `TPL_EXTRACCION_RAPIDA.md` | template | Formato de la extracción rápida obligatoria de 6 puntos. | high | low |
| `TPL_RESUMEN_EXPEDIENTE.md` | template | Formato del análisis completo del expediente (secciones 0-10). | high | low |
| `TPL_MATRIZ_REQUISITOS.md` | template | Matriz requisito-fuente-cumplimiento-evidencia. | high | low |
| `TPL_MATRIZ_SOLVENCIA.md` | template | Matriz de solvencia exigida frente a acreditación disponible. | high | low |
| `TPL_MATRIZ_PERSONAL.md` | template | Matriz de personal exigido frente a disponible. | high | low |
| `TPL_MATRIZ_CRITERIOS.md` | template | Matriz criterio-puntos-evidencia-cobertura-acción-prioridad. | high | low |
| `TPL_BASE_ECONOMICA.md` | template | Estructura de la base económica con escenarios y sensibilidades. | high | low |
| `TPL_MEMORIA_TECNICA.md` | template | Esqueleto de memoria técnica y ficha estándar de apartado. | high | low |
| `TPL_PLAN_DE_TRABAJO.md` | template | Formato del plan de trabajo por fases y actividades. | high | low |
| `TPL_CRONOGRAMA.md` | template | Formato de cronograma (tabla y Gantt mermaid). | high | low |
| `TPL_RACI.md` | template | Formato de matriz RACI. | high | low |
| `TPL_RIESGOS.md` | template | Formato de matriz de riesgos de 9 columnas. | high | low |
| `TPL_KPIS.md` | template | Formato de ficha y cuadro de indicadores. | high | low |
| `TPL_ENTREGABLES.md` | template | Formato de ficha de entregable. | high | low |
| `TPL_RED_TEAM.md` | template | Formato del informe Red Team con hallazgos clasificados. | high | low |
| `TPL_CONCLUSION_INTERNA.md` | template | Formato del bloque interno breve para decisión del usuario. | high | low |

## 07_CHECKLISTS — Checklists

| Archivo | Tipo | Propósito | Prioridad | Coste |
|---|---|---|---|---|
| `CHK_DOCUMENTOS.md` | checklist | Control del inventario documental del expediente. | medium | low |
| `CHK_SOLVENCIA.md` | checklist | Control de la validación de solvencia. | medium | low |
| `CHK_PERSONAL.md` | checklist | Control del análisis de personal y adscripción. | medium | low |
| `CHK_COSTES.md` | checklist | Control de identificación completa de costes. | medium | low |
| `CHK_MEMORIA.md` | checklist | Control de calidad de la memoria antes del Red Team. | medium | low |
| `CHK_SOBRES.md` | checklist | Control de separación estricta de sobres. | medium | low |
| `CHK_RED_TEAM.md` | checklist | Control de ejecución completa de la revisión Red Team. | medium | low |
| `CHK_PRESENTACION_FINAL.md` | checklist | Control final antes de la presentación de la oferta. | medium | low |

## 08_OUTPUT_EXAMPLES — Ejemplos de salida

| Archivo | Tipo | Propósito | Prioridad | Coste |
|---|---|---|---|---|
| `EJEMPLO_ANALISIS_EXPEDIENTE.md` | example | Ejemplo calibrado de análisis completo de expediente. | low | medium |
| `EJEMPLO_BASE_ECONOMICA.md` | example | Ejemplo calibrado de base económica con escenarios. | low | medium |
| `EJEMPLO_INDICE_MEMORIA.md` | example | Ejemplo de índice de memoria trazado contra criterios. | low | medium |
| `EJEMPLO_APARTADO_MEMORIA.md` | example | Ejemplo de apartado de memoria con ficha completa. | low | medium |
| `EJEMPLO_RED_TEAM.md` | example | Ejemplo de informe Red Team con hallazgos clasificados. | low | medium |

## 09_BUILD — Build y metadatos

| Archivo | Tipo | Propósito | Prioridad | Coste |
|---|---|---|---|---|
| `MANIFEST.json` | build | Metadatos de todos los módulos para el enrutado selectivo. | critical | low |
| `FILE_INDEX.md` | build | Índice maestro legible de todos los archivos. | critical | low |
| `CONTEXT_LOADING_GUIDE.md` | build | Estrategia de recuperación selectiva y presupuesto de contexto. | critical | low |
| `CHANGELOG.md` | build | Historial de cambios del sistema. | critical | low |
| `VALIDATION_REPORT.md` | build | Resultado de las 8 pruebas de validación del sistema. | critical | low |

