# SKILL 01 — EXPEDIENT_ANALYZER

> **Propósito:** extraer y estructurar todos los elementos relevantes de un expediente de contratación (PCAP, PPT, memoria justificativa, CRC, anexos, formularios).
> **Cuándo cargarlo:** al recibir documentación de un expediente o ante preguntas sobre su contenido (clases A y B del Router).
> **Cuándo no cargarlo:** en redacción de memoria, presupuestación avanzada, revisión Red Team o visuales.
> **Skills que lo utilizan:** ROUTER lo activa; BUDGET, SCORING y MEMORY consumen sus salidas.
> **Palabras clave:** analiza, pliego, expediente, PCAP, PPT, extracción, requisitos, solvencia.
> **Dependencias:** K-01 (metodología de análisis), TPL_EXTRACCION_RAPIDA, TPL_RESUMEN_EXPEDIENTE, CHK_DOCUMENTOS; K-07/K-08 para solvencia y personal.
> **Prioridad:** alta. **Coste de contexto:** medio-alto (procesa los documentos fuente).
> **Resumen:** Skill de lectura experta del expediente. Inventaría los documentos, distingue su naturaleza (PCAP, PPT, memoria justificativa, CRC, anexos, formularios, modelos), ejecuta la extracción rápida obligatoria de 6 puntos, y produce el análisis completo de 13 secciones con todos los datos referenciados y etiquetados según RI-10. Detecta contradicciones documentales y vacíos. No redacta memoria ni calcula ofertas económicas definitivas.

---

## 1. Nombre
EXPEDIENT_ANALYZER.

## 2. Propósito
Convertir el expediente en información estructurada, referenciada y accionable para todas las fases posteriores.

## 3. Responsabilidad única
Leer, extraer, estructurar y señalar. No valora estrategia, no presupuesta, no redacta oferta.

## 4. Cuándo se activa
Subida de documentos de expediente; preguntas sobre contenido del pliego; validación de solvencia/personal (con K-07/K-08).

## 5. Cuándo no se activa
Peticiones de redacción, presupuesto cerrado, revisión o visuales; cuestiones puramente jurídicas (van a 13_PROCUREMENT).

## 6. Entradas obligatorias
Al menos un documento del expediente (idealmente PCAP y PPT).

## 7. Entradas opcionales
Aclaraciones oficiales, memoria justificativa, CRC, anexos, cuadro de características, modelos de proposición, información interna de la empresa.

## 8. Salidas
Extracción rápida (TPL_EXTRACCION_RAPIDA) → análisis completo (TPL_RESUMEN_EXPEDIENTE) → matrices de requisitos/solvencia/personal cuando se soliciten → bloque interno (TPL_CONCLUSION_INTERNA) → preguntas cerradas.

## 9. Flujo interno
1. Inventariar documentos y clasificarlos por naturaleza (CHK_DOCUMENTOS). 2. Detectar faltantes típicos. 3. Localizar el cuadro de características o resumen del PCAP (fuente más densa). 4. Extracción rápida de 6 puntos con referencias. 5. Barrido completo del PCAP (administrativo). 6. Barrido completo del PPT (técnico-operativo). 7. Cruce PCAP↔PPT en busca de contradicciones (RI-19). 8. Montar el análisis de 13 secciones. 9. Bloque interno + preguntas cerradas.

## 10. Árbol de decisión
- ¿Hay PCAP y PPT? → No: analizar lo disponible, listar faltantes, advertir alcance parcial.
- ¿Hay lotes? → Sí: extracción rápida por lote o comparada.
- ¿Contradicción entre documentos? → Señalar ambos, indicar prevalencia probable, marcar [INTERPRETACIÓN].
- ¿Dato esencial ausente? → «No consta» + posible documento faltante + pregunta cerrada.

## 11. Elementos que debe extraer (catálogo completo)
Objeto · tipo de contrato · CPV · órgano de contratación · PBL (con/sin IVA) · valor estimado · duración · prórrogas · lotes · fecha y hora límite · plataforma de presentación · forma de presentación (sobres/archivos electrónicos) · documentos que integran el expediente · solvencia económica y técnica (umbrales y medios) · clasificación alternativa · personal exigido y adscripción de medios · tareas · entregables · reuniones · talleres · viajes · dietas · materiales · licencias · tecnología · subcontratación (límites y régimen) · lugar de ejecución · hitos y plazos parciales · régimen de pagos · penalidades · criterios de adjudicación (puntos, fórmulas, umbrales) · parámetros de baja anormal · mejoras (definición, límites, sobre) · condiciones especiales de ejecución · garantías · revisión de precios · confidencialidad · riesgos · contradicciones.

## 12. Prohibiciones
Redactar memoria; calcular oferta económica definitiva; afirmar cumplimiento de solvencia o disponibilidad de personal (RI-03, RI-04); rellenar vacíos con supuestos no marcados (RI-02, RI-10); ocultar contradicciones (RI-19); emitir recomendación de presentarse (RI-11).

## 13. Procedimiento paso a paso
Según §9, con esta disciplina de referencia: todo dato lleva (documento, apartado o cláusula, página si consta). Los datos de la extracción rápida se citan literalmente entre comillas cuando sean breves.

## 14. Casos especiales
- **Pliegos escaneados/ilegibles:** advertir del riesgo de pérdida de información y pedir versión nativa.
- **Acuerdo marco o contrato basado:** distinguir condiciones del marco y del basado.
- **Expediente con aclaraciones publicadas:** las aclaraciones prevalecen (jerarquía de fuentes 2).
- **PPT con anexos técnicos extensos:** extraer obligaciones cuantificables (frecuencias, volúmenes, plazos) antes que descripciones.

## 15. Gestión de ambigüedad
Término ambiguo con impacto (p. ej. «servicios similares»): presentar las lecturas posibles, marcar [INTERPRETACIÓN], proponer consulta al órgano si el plazo lo permite.

## 16. Gestión de información faltante
Lista numerada de faltantes con su efecto («sin el anexo III no puedo confirmar los umbrales de solvencia») y pregunta cerrada asociada.

## 17. Errores habituales
Confundir PBL con valor estimado; ignorar plazos parciales y penalidades; leer solo el PPT y omitir el cuadro de características; no contar reuniones/viajes/talleres (coste oculto, RI-08); tratar la memoria justificativa como si fuera vinculante frente al PCAP.

## 18. Checklist
☐ Inventario documental completo ☐ Extracción rápida con 6 puntos referenciados ☐ 13 secciones cubiertas ☐ Contradicciones señaladas ☐ Todo dato etiquetado ☐ Preguntas cerradas formuladas ☐ Sin decisión de presentarse.

## 19. Prompt operativo interno
«Inventaría y clasifica los documentos; ejecuta la extracción rápida de 6 puntos con citas; barre PCAP y PPT extrayendo el catálogo §11; cruza documentos buscando contradicciones; entrega TPL_RESUMEN_EXPEDIENTE + bloque interno + preguntas cerradas, todo etiquetado RI-10.»

## 20. Ejemplos de activación
«Analiza este expediente de la Junta»; «¿qué solvencia piden?»; «¿cuántos puntos vale la memoria?».

## 21. Ejemplos de salida
Ver 08_OUTPUT_EXAMPLES/EJEMPLO_ANALISIS_EXPEDIENTE.md.

## 22. Relación con otras Skills
Entrega insumos a BUDGET (obligaciones económicas), SCORING (criterios), MEMORY (requisitos y trazabilidad), RISK (riesgos detectados), PROCUREMENT (dudas jurídicas).

## 23. Datos que puede compartir
Todo el análisis estructurado y sus referencias.

## 24. Datos que no puede compartir
Valoraciones estratégicas definitivas (corresponden a SCORING) y juicios de «cumplimos/no cumplimos» sin validación del usuario.

## 25. Consumo de contexto
Medio-alto: documentos fuente + esta Skill + plantillas. No cargar playbooks ni conocimiento no relacionado durante el análisis.

## 26. Estrategia de ahorro de tokens
Priorizar cuadro de características y anexos de criterios; citar literalmente solo lo esencial; resumir el resto con referencia; no reproducir cláusulas estándar de la LCSP.

## 27. Criterios de calidad
Cada afirmación es verificable contra el expediente; un tercero podría localizar cada dato con la referencia dada; los 13 riesgos de catálogo evaluados.

## 28. Criterios de parada
Análisis de 13 secciones entregado con bloque interno y preguntas; o bloqueo por documentación insuficiente comunicado.
