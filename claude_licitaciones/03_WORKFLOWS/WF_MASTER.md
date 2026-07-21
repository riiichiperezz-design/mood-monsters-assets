# WF_MASTER — Máquina de estados del expediente (0-17)

> **Propósito:** definir el ciclo de vida completo de un expediente en 18 estados, con entradas, acciones, salidas, responsables, documentos, bloqueos y transiciones permitidas y prohibidas.
> **Cuándo cargarlo:** al iniciar un expediente, al dudar de la fase actual o al detectar una petición que salta fases.
> **Cuándo no cargarlo:** dentro de una fase ya en curso (basta el WF de tramo).
> **Skills que lo utilizan:** 00_KNOWLEDGE_ROUTER (referencia principal de fases).
> **Palabras clave:** workflow maestro, estados, fases, en qué punto estamos.
> **Dependencias:** WF_01–WF_10 (desarrollo por tramos), REGLAS_INVIOLABLES.md.
> **Prioridad:** alta. **Coste de contexto:** bajo.
> **Resumen:** máquina de estados 0-17 que gobierna todo expediente: recepción, inventario, extracción rápida, análisis, solvencia, personal, criterios, costes, preguntas, base económica, estrategia de puntuación, índice, redacción, cobertura, red team, correcciones, validación formal y cierre. Para cada estado define la ficha completa y las transiciones; las transiciones prohibidas codifican las reglas RI-12, RI-13 y RI-20. El estado 9→10 contiene el único punto de decisión obligatoria del usuario.

---

## Convenciones

- **Skill** = responsable principal (otras pueden asistir).
- **Docs** = módulos que el Router carga en ese estado (además de instrucciones).
- **→ permitido / ⊘ prohibido** = transiciones. Retroceder siempre está permitido (nueva información reabre estados).
- Un turno puede recorrer varios estados si nada bloquea (p. ej. 0→3 en un solo análisis).

## Estados

### ESTADO 0 — Recepción
**Entrada:** archivos o enlaces del expediente; petición inicial. **Acciones:** confirmar recepción; identificar expediente (objeto, órgano); detectar formato legible. **Salida:** expediente registrado en la conversación. **Skill:** ROUTER. **Docs:** WF_01. **Fin:** archivos accesibles. **Bloqueos:** archivos ilegibles → pedir versión nativa. **Pendientes:** ninguno. **→** 1. **⊘** cualquier estado ≥2 sin pasar por 1.

### ESTADO 1 — Inventario documental
**Entrada:** archivos recibidos. **Acciones:** clasificar cada documento (PCAP, PPT, memoria justificativa, CRC, anexos, formularios, modelos); detectar faltantes típicos. **Salida:** inventario clasificado + lista de faltantes. **Skill:** ANALYZER. **Docs:** WF_01, CHK_DOCUMENTOS. **Fin:** todo documento clasificado. **Bloqueos:** falta PCAP y PPT → analizar parcial con advertencia. **Pendientes:** documentos faltantes solicitados. **→** 2. **⊘** 9-17.

### ESTADO 2 — Extracción rápida
**Entrada:** inventario. **Acciones:** extraer los 6 puntos obligatorios en orden con cita: plazos, puntos precio, puntos mejora, puntos memoria, solvencia económica, solvencia técnica. **Salida:** bloque TPL_EXTRACCION_RAPIDA. **Skill:** ANALYZER. **Docs:** WF_02, TPL_EXTRACCION_RAPIDA. **Fin:** 6 puntos con dato o «no consta». **Bloqueos:** ninguno (los vacíos se declaran). **→** 3. **⊘** 11-12 (RI-12).

### ESTADO 3 — Análisis del expediente
**Entrada:** extracción rápida. **Acciones:** barrido PCAP+PPT; 13 secciones; cruce de contradicciones; etiquetado RI-10. **Salida:** TPL_RESUMEN_EXPEDIENTE + bloque interno + preguntas. **Skill:** ANALYZER. **Docs:** WF_02, K-01, TPL_RESUMEN, TPL_CONCLUSION_INTERNA. **Fin:** 13 secciones cubiertas. **Bloqueos:** documentación crítica ausente. **Pendientes:** lista [PENDIENTE]. **→** 4, 5, 6, 7. **⊘** 11-12.

### ESTADO 4 — Validación de solvencia
**Entrada:** requisitos de solvencia extraídos. **Acciones:** matriz exigido↔acreditable; alternativas (clasificación, medios externos); preguntas cerradas. **Salida:** TPL_MATRIZ_SOLVENCIA con estados (acreditable/[PENDIENTE]/riesgo). **Skill:** ANALYZER (+PROCUREMENT si duda jurídica). **Docs:** WF_03, K-07, CHK_SOLVENCIA. **Fin:** cada requisito con estado. **Bloqueos:** solvencia claramente inalcanzable → escalar a usuario (RI-20). **→** 5. **⊘** 12.

### ESTADO 5 — Análisis de personal
**Entrada:** exigencias de personal/adscripción. **Acciones:** matriz perfil exigido↔disponible; dedicaciones; penalidades por sustitución; preguntas. **Salida:** TPL_MATRIZ_PERSONAL. **Skill:** ANALYZER. **Docs:** WF_03, K-08, CHK_PERSONAL. **Fin:** cada perfil con estado. **Bloqueos:** personal clave inexistente → escalar (RI-20). **→** 6. **⊘** 12.

### ESTADO 6 — Análisis de criterios
**Entrada:** criterios extraídos. **Acciones:** clasificar fórmula/juicio; analizar fórmula de precio; umbrales; matriz de 7 columnas; taxonomía de mejoras. **Salida:** TPL_MATRIZ_CRITERIOS + mapa de sobres. **Skill:** SCORING. **Docs:** WF_04, K-05, K-06. **Fin:** suma de puntos cuadra con el pliego. **Bloqueos:** anexo de criterios ausente. **→** 7. **⊘** 12 sin pasar por 10-11.

### ESTADO 7 — Identificación de costes
**Entrada:** obligaciones del PPT + análisis. **Acciones:** convertir PPT en necesidades económicas; catálogo completo de categorías; sin valorar si faltan tarifas. **Salida:** inventario de necesidades económicas. **Skill:** BUDGET. **Docs:** WF_05, K-09 (parcial), CHK_COSTES. **Fin:** ninguna obligación sin reflejo. **Bloqueos:** análisis (E3) incompleto → volver (RI-13). **→** 8. **⊘** 9 sin completar 7.

### ESTADO 8 — Preguntas internas
**Entrada:** pendientes acumulados (E3-E7). **Acciones:** consolidar preguntas cerradas por criticidad; indicar qué desbloquea cada una. **Salida:** cuestionario interno único. **Skill:** ROUTER (consolida). **Docs:** WF_05. **Fin:** cuestionario entregado. **Bloqueos:** ninguno. **Pendientes:** respuestas del usuario. **→** 9 (con respuestas o hipótesis declaradas). **⊘** 12.

### ESTADO 9 — Base económica
**Entrada:** necesidades económicas + tarifas/respuestas o hipótesis. **Acciones:** escenarios mínimo/probable/conservador; margen; sensibilidades; punto de equilibrio; zona de baja anormal; advertencia margen <10-15 %. **Salida:** TPL_BASE_ECONOMICA. **Skill:** BUDGET. **Docs:** WF_06, K-09. **Fin:** escenarios y advertencias entregados. **Bloqueos:** sin inventario E7 (RI-13). **→** 10 **solo con decisión del usuario de avanzar** (RI-11, RI-20). **⊘** 10-12 sin decisión expresa.

### ESTADO 10 — Estrategia de puntuación
**Entrada:** decisión de avanzar; matriz de criterios. **Acciones:** refinar matriz con cobertura real; priorizar acciones; decidir tratamiento de mejoras (usuario). **Salida:** estrategia priorizada + mejoras aprobadas/descartadas. **Skill:** SCORING. **Docs:** WF_07, K-05. **Fin:** estrategia aprobada. **Bloqueos:** cobertura desconocida en criterios decisivos. **→** 11. **⊘** 12 sin 11.

### ESTADO 11 — Índice de memoria
**Entrada:** estrategia + límites formales. **Acciones:** índice trazado criterio→apartado; reparto de páginas por puntos; lista de información interna necesaria. **Salida:** índice para aprobación. **Skill:** MEMORY. **Docs:** WF_07, K-02, TPL_MEMORIA. **Fin:** índice aprobado por el usuario. **Bloqueos:** límites formales no identificados. **→** 12. **⊘** 12 sin aprobación (RI-20).

### ESTADO 12 — Redacción
**Entrada:** índice aprobado + información interna validada. **Acciones:** redactar por lotes con ficha estándar; invocar GOVERNANCE/PLANNING/RISK/DELIVERABLES/KPI/VISUAL por apartado; marcar [PENDIENTE]. **Salida:** borrador completo. **Skill:** MEMORY (+auxiliares). **Docs:** WF_07, K-02, K-03, playbook sectorial (uno), plantillas de apartado. **Fin:** todos los apartados redactados. **Bloqueos:** pendientes críticos (RI-20); compromisos sin presupuesto (RI-07). **→** 13. **⊘** 16-17 sin 13-15.

### ESTADO 13 — Revisión de cobertura
**Entrada:** borrador completo. **Acciones:** contraste borrador↔matriz de criterios: cada criterio con cobertura proporcional; huecos listados. **Salida:** informe de cobertura. **Skill:** SCORING (asistido por MEMORY). **Docs:** WF_09, TPL_MATRIZ_CRITERIOS. **Fin:** cobertura verificada o huecos corregidos. **→** 14. **⊘** 16 sin 14.

### ESTADO 14 — Red Team
**Entrada:** borrador con cobertura verificada. **Acciones:** 8 pasadas adversariales; hallazgos clasificados; veredicto. **Salida:** TPL_RED_TEAM. **Skill:** RED_TEAM. **Docs:** WF_09, K-14, CHK_RED_TEAM, CHK_SOBRES. **Fin:** informe emitido. **Bloqueos:** ninguno (informa siempre). **→** 15. **⊘** 16 con críticos abiertos.

### ESTADO 15 — Correcciones
**Entrada:** informe Red Team + decisiones del usuario sobre hallazgos. **Acciones:** MEMORY aplica correcciones aprobadas; EDITORIAL los hallazgos de estilo; re-verificación de hallazgos críticos/altos. **Salida:** versión corregida + registro de hallazgos resueltos/asumidos. **Skill:** MEMORY + EDITORIAL. **Docs:** WF_09. **Fin:** críticos resueltos; altos resueltos o asumidos expresamente por el usuario. **→** 16. **⊘** 17 sin 16.

### ESTADO 16 — Validación formal
**Entrada:** versión corregida. **Acciones:** verificación formal final: páginas, tipografía, estructura exigida, anexos, formularios, firmas, formato de archivos, plataforma y plazo de presentación. **Salida:** CHK_PRESENTACION_FINAL cumplimentado. **Skill:** RED_TEAM (pasada formal) + ROUTER. **Docs:** WF_10, CHK_PRESENTACION_FINAL. **Fin:** checklist sin pendientes. **Bloqueos:** incumplimiento formal → volver a 15. **→** 17. **⊘** —.

### ESTADO 17 — Cierre
**Entrada:** oferta validada. **Acciones:** paquete final de documentos por sobre; recordatorio de plazo/plataforma; lecciones aprendidas opcionales; archivo del expediente. **Salida:** cierre documentado. **Skill:** ROUTER. **Docs:** WF_10. **Fin:** entregado al usuario. **→** fin (o reapertura por aclaraciones/subsanaciones).

## Matriz resumida de transiciones prohibidas

| Desde | Prohibido | Regla |
|---|---|---|
| 0-5 | → 11, 12 | RI-12 (no redactar antes de entender) |
| 0-6 | → 9 | RI-13 (no presupuestar sin obligaciones) |
| 9 | → 10-12 sin decisión del usuario | RI-11, RI-20 |
| 11 | → 12 sin índice aprobado | RI-20 |
| 12-14 | → 16-17 con críticos abiertos | RI-14/RI-05 (formales) |
| Cualquiera | saltar la extracción rápida en primer análisis | Flujo obligatorio |

## Reapertura de estados

Nueva documentación (aclaraciones, rectificaciones) reabre E1-E3 y propaga cambios: el Router identifica qué salidas quedan invalidadas y qué estados deben repetirse.
