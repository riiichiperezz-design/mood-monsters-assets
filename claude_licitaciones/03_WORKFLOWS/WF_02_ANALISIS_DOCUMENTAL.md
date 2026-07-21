# WF_02 — Extracción rápida y análisis documental

> **Propósito:** procedimiento de los estados 2-3: producir la extracción rápida obligatoria y el análisis completo de 13 secciones.
> **Cuándo cargarlo:** tras el inventario documental, al analizar el contenido del expediente.
> **Cuándo no cargarlo:** con el análisis ya realizado; en fases económicas o de redacción.
> **Skills que lo utilizan:** ANALYZER.
> **Palabras clave:** extracción rápida, análisis documental, analizar pliego.
> **Dependencias:** WF_MASTER (E2-E3), K-01, TPL_EXTRACCION_RAPIDA, TPL_RESUMEN_EXPEDIENTE, TPL_CONCLUSION_INTERNA.
> **Prioridad:** alta. **Coste de contexto:** bajo (el coste alto es de los documentos fuente).
> **Resumen:** secuencia de lectura eficiente del expediente: primero el cuadro de características y los anexos de criterios (máxima densidad), después el PCAP completo, después el PPT convertido en obligaciones cuantificables, y por último el cruce de contradicciones. Fija el orden exacto de la extracción rápida, el contenido mínimo de cada una de las 13 secciones del análisis y la obligación de cerrar con bloque interno y preguntas cerradas sin emitir decisión.

---

## 1. Objetivo y estados cubiertos
Estados 2 (Extracción rápida) y 3 (Análisis del expediente).

## 2. Entrada
Inventario documental de WF_01; documentos legibles.

## 3. Pasos — Estado 2 (extracción rápida)

1. Localizar las fuentes densas: cuadro de características del PCAP, anexo de criterios, apartado de solvencia.
2. Extraer **en este orden exacto** (TPL_EXTRACCION_RAPIDA): 1) plazos de ejecución; 2) puntos por precio; 3) puntos por mejora; 4) puntos por memoria; 5) solvencia económica; 6) solvencia técnica.
3. Cada punto: dato literal (cita breve) + referencia (documento, cláusula/apartado, página). Si no consta: «No consta en la documentación aportada» + hipótesis de documento faltante.
4. Casos límite (lotes, contradicciones, clasificación alternativa): según VERSION_COMPLETA §1.
5. Entregar la extracción **antes** de cualquier otro contenido.

## 4. Pasos — Estado 3 (análisis completo)

1. **Barrido PCAP:** objeto, tipo, CPV, órgano, PBL/valor estimado, duración y prórrogas, lotes, presentación (plazo, plataforma, sobres), solvencia y adscripción, criterios y fórmulas, baja anormal, garantías, penalidades, pagos, subcontratación, modificación, condiciones especiales.
2. **Barrido PPT como obligaciones:** cada tarea con frecuencia, volumen, plazo y entregable; reuniones, talleres, viajes, materiales, licencias, tecnología contados (alimentan E7).
3. **Cruce PCAP↔PPT↔anexos:** contradicciones (plazos, equipo, entregables) señaladas con ambas citas (RI-19).
4. **Montar las 13 secciones** según TPL_RESUMEN_EXPEDIENTE y el contenido mínimo de VERSION_COMPLETA §2.
5. **Bloque interno** (TPL_CONCLUSION_INTERNA): solvencias, personal, criterios, riesgos y conclusión operativa **sin decisión** (RI-11).
6. **Preguntas cerradas** consolidadas (máximo 12, por criticidad).

## 5. Salida
Extracción rápida + análisis de 13 secciones + bloque interno + preguntas. Todo etiquetado RI-10.

## 6. Bloqueos
Documentación crítica ilegible o ausente (volver a WF_01); lotes sin elección del usuario (vista comparada + pregunta).

## 7. Criterio de finalización
Las 13 secciones cubiertas con referencias; contradicciones señaladas; ninguna decisión emitida.

## 8. Errores habituales
Empezar por el PPT ignorando el cuadro de características; parafrasear el pliego en lugar de estructurarlo; omitir plazos parciales y penalidades; perder los costes implícitos del PPT (se pagan en E7).

## 9. Conexiones
Alimenta WF_03 (solvencia/personal), WF_04 (criterios) y WF_05 (costes). Reapertura: aclaraciones oficiales posteriores obligan a revisar extracción y análisis.
