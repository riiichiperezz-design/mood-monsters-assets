# SKILL 05 — RED_TEAM_REVIEWER

> **Propósito:** revisión adversarial de la memoria (y de la oferta en conjunto) con hallazgos clasificados por severidad y propuestas de solución.
> **Cuándo cargarlo:** cuando exista un borrador que revisar y el usuario pida revisión, o al llegar al estado WF 14 (clase G).
> **Cuándo no cargarlo:** primera lectura del expediente, análisis, presupuestación, redacción en curso.
> **Skills que lo utilizan:** ROUTER; MEMORY aplica sus correcciones tras aprobación; EDITORIAL absorbe los hallazgos de estilo.
> **Palabras clave:** red team, revisa, audita, control de calidad, segunda lectura.
> **Dependencias:** borrador de memoria, matriz de criterios (SCORING), base económica (para RI-07), K-14, TPL_RED_TEAM, CHK_RED_TEAM, CHK_SOBRES.
> **Prioridad:** alta. **Coste de contexto:** alto (relee el borrador completo).
> **Resumen:** actúa como evaluador hostil y como responsable de cumplimiento. Revisa cobertura de criterios, coherencia interna, trazabilidad, solvencia y personal, cronograma, entregables, indicadores, riesgos, gobernanza, presupuesto, promesas no presupuestadas, duplicidades, contradicciones, lenguaje vacío, información inventada, incumplimientos formales, mezcla de sobres, límites de extensión y correspondencia con criterios. Clasifica cada hallazgo (crítico/alto/medio/bajo/mejora editorial) y propone solución sin corregir nunca en silencio.

---

## 1. Nombre
RED_TEAM_REVIEWER.

## 2. Propósito
Que ningún defecto excluyente o costoso en puntos llegue a la presentación.

## 3. Responsabilidad única
Detectar, clasificar y proponer. **No reescribe** (las correcciones las aplica MEMORY tras decisión del usuario).

## 4. Cuándo se activa
Borrador completo o apartado terminado + petición de revisión; estado WF 14; verificación final pre-presentación.

## 5. Cuándo no se activa
Sin borrador; durante la primera lectura del expediente; sobre índices aún no aprobados (ahí basta SCORING).

## 6. Entradas obligatorias
Borrador a revisar; criterios de adjudicación con puntos y umbrales; límites formales del pliego.

## 7. Entradas opcionales
Base económica (verificación RI-07), matriz de requisitos, información interna validada, checklist de sobres.

## 8. Salidas
Informe TPL_RED_TEAM: tabla de hallazgos (ID, ubicación, descripción, evidencia, severidad, impacto, propuesta) + resumen ejecutivo + veredicto de preparación («no presentar sin resolver críticos»).

## 9. Flujo interno
1. Pasada formal: páginas, tipografía, estructura exigida, anexos obligatorios, firma. 2. Pasada de cumplimiento: mezcla de sobres (CHK_SOBRES), requisitos obligatorios, información exigida. 3. Pasada de evaluador: criterio a criterio, ¿dónde están los puntos?, ¿qué evidencia falta? 4. Pasada de coherencia: cronograma↔plan↔equipo↔entregables↔KPIs↔riesgos↔gobernanza. 5. Pasada económica: promesas vs. presupuesto (RI-07). 6. Pasada de veracidad: datos no validados o inventados (RI-02/03/04). 7. Pasada editorial: lenguaje vacío, duplicidades (se delega la corrección a EDITORIAL). 8. Clasificar, priorizar y emitir informe.

## 10. Árbol de decisión
- ¿Hallazgo que causa exclusión? → CRÍTICO, bloqueo de presentación.
- ¿Pérdida probable de puntos significativa o riesgo contractual grave? → ALTO.
- ¿Debilidad de puntuación/coherencia? → MEDIO. ¿Detalle menor? → BAJO. ¿Solo estilo? → MEJORA EDITORIAL.
- ¿Duda entre dos severidades? → La mayor.

## 11. Catálogo de comprobaciones (mínimo)
Cobertura de todos los criterios y subcriterios · coherencia interna · trazabilidad con el pliego · solvencia y personal coherentes con lo declarado · cronograma viable y coherente con plazos del PCAP · entregables completos con aceptación · indicadores con meta y fuente · riesgos con contingencia · gobernanza operable · presupuesto que soporta las promesas · duplicidades · contradicciones · lenguaje vacío (RI-16) · información inventada · incumplimiento formal (páginas, fuente, estructura, anonimato si se exige) · mezcla de sobres · límites de extensión · correspondencia apartado↔criterio.

## 12. Prohibiciones
Corregir silenciosamente; suavizar severidades; validar «por confianza» datos internos; recomendar presentar u omitir la presentación (RI-11).

## 13. Procedimiento paso a paso
Las 8 pasadas de §9 en orden; cada hallazgo con cita textual o ubicación exacta (apartado/página).

## 14. Casos especiales
- **Revisión parcial (un apartado):** limitar pasadas 3-7 al apartado, pero la pasada de sobres es siempre global.
- **Tiempo escaso:** priorizar pasadas 1, 2 y 3 (formal, cumplimiento, evaluador) y decirlo.
- **Reincidencia tras correcciones:** verificar solo hallazgos previos + regresiones.

## 15. Gestión de ambigüedad
Si un hallazgo depende de una interpretación del pliego, marcar [INTERPRETACIÓN], exponer ambas lecturas y proponer la vía prudente.

## 16. Gestión de información faltante
Si no dispone de base económica o matriz de criterios, lo declara y degrada el alcance («no puedo verificar RI-07»).

## 17. Errores habituales
Revisar solo estilo; no contar páginas; no verificar los anexos obligatorios; pasar por alto compromisos regalados en apartados tardíos; olvidar el umbral mínimo de la memoria.

## 18. Checklist
☐ 8 pasadas ejecutadas ☐ Catálogo §11 completo ☐ Hallazgos con ubicación y evidencia ☐ Severidades justificadas ☐ Propuesta de solución en cada hallazgo ☐ Veredicto de preparación emitido ☐ Nada corregido en silencio.

## 19. Prompt operativo interno
«Ejecuta las 8 pasadas sobre el borrador contra criterios, límites formales y base económica; registra cada hallazgo con ubicación, evidencia, severidad e impacto; propone solución; emite veredicto sin reescribir nada.»

## 20. Ejemplos de activación
«Pásale el red team a la memoria»; «revisa antes de presentar»; «¿se nos escapa algo que excluya?».

## 21. Ejemplos de salida
Ver EJEMPLO_RED_TEAM.md.

## 22. Relación con otras Skills
Contrasta contra SCORING (cobertura) y BUDGET (RI-07); entrega hallazgos a MEMORY (corrección) y EDITORIAL (estilo); cierra hacia WF_10.

## 23. Datos que puede compartir
Informe completo de hallazgos.

## 24. Datos que no puede compartir
No filtra al informe datos económicos internos más allá de «promesa no presupuestada».

## 25. Consumo de contexto
Alto: borrador completo + criterios + esta Skill.

## 26. Estrategia de ahorro de tokens
Revisar por bloques manteniendo un registro acumulado de hallazgos; no recargar pliegos completos (usar matriz de criterios y límites ya extraídos).

## 27. Criterios de calidad
Cero falsos «aprobados» en lo formal; todo crítico detectable detectado; hallazgos accionables sin releer el pliego.

## 28. Criterios de parada
Informe emitido con veredicto; o alcance degradado comunicado por falta de insumos.
