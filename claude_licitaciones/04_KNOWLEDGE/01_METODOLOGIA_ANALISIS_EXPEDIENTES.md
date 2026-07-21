# K-01 — Metodología de análisis de expedientes

> **Propósito:** método completo de lectura y explotación de expedientes de contratación pública.
> **Cuándo cargarlo:** durante el análisis de un expediente (estados 2-3) cuando se necesite método, no solo plantilla.
> **Cuándo no cargarlo:** en redacción, presupuesto, revisión o visuales.
> **Skills que lo utilizan:** 01_EXPEDIENT_ANALYZER.
> **Palabras clave:** metodología, análisis de pliegos, cómo leer un expediente.
> **Dependencias:** TPL_EXTRACCION_RAPIDA, TPL_RESUMEN_EXPEDIENTE.
> **Prioridad:** media. **Coste de contexto:** alto.
> **Resumen:** doctrina de lectura profesional de expedientes: orden óptimo de lectura por densidad de información, técnica de doble pasada (administrativa y operativa), conversión del PPT en obligaciones cuantificables, detección sistemática de contradicciones y trampas típicas de los pliegos, y disciplina de referencia y etiquetado. Incluye el catálogo de señales de alarma que distinguen un expediente sano de uno problemático.

---

## 1. Principios

1. **El expediente se explota, no se lee de corrido.** El objetivo es extraer decisiones, no resumir prosa.
2. **Orden por densidad:** cuadro de características → anexo de criterios → solvencia/adscripción → PPT (obligaciones) → resto del PCAP → memoria justificativa (intención) → formularios (forma exacta de presentar).
3. **Doble pasada:** administrativa (¿podemos y nos conviene?) y operativa (¿qué hay que hacer exactamente?).
4. **Todo dato con referencia** (documento, cláusula, página) y etiqueta RI-10: el análisis debe ser auditable por un tercero.

## 2. Técnica de explotación del PCAP

- Buscar primero el **cuadro-resumen/anexo I**: concentra PBL, plazo, solvencia, criterios, garantías. El resto del PCAP matiza.
- **Criterios:** copiar el desglose completo con puntos y fórmulas; verificar que suman el total; identificar umbrales y desempates.
- **Solvencia:** literal exacto (los matices —«similares», «anualidad de mayor ejecución», «certificados»— deciden si se puede concurrir).
- **Adscripción de medios:** distinta de la solvencia; es compromiso contractual con penalidad.
- **Régimen económico:** pagos, revisión, penalidades, garantía definitiva; condicionan la tesorería y el riesgo real.
- **Trampas típicas:** plazos parciales escondidos en cláusulas de penalidades; obligaciones «a costa del adjudicatario» dispersas; condiciones especiales de ejecución con obligaciones materiales; confidencialidad que limita referencias futuras.

## 3. Técnica de explotación del PPT

Convertir cada párrafo en, como máximo, una fila de esta estructura mental: **tarea → frecuencia → volumen → plazo → entregable → recurso implícito**. Señales de coste oculto: «al menos», «cuantas veces sea necesario», «a demanda del órgano», «incluyendo desplazamientos», «con los medios del adjudicatario». Cada aparición se cuenta y se traslada al inventario económico (E7).

## 4. Cruce documental (RI-19)

Contrastes obligatorios: plazo total (PCAP↔PPT), equipo (solvencia↔PPT↔criterios), entregables (PPT↔criterios), mejoras (definición↔sobre), presupuesto (PBL↔desglose de la memoria justificativa). Toda contradicción se documenta con ambas citas y su implicación; prevalencia según jerarquía de fuentes, con aclaración al órgano como vía preferente si hay plazo.

## 5. Señales de alarma de expediente problemático

- PBL visiblemente infradotado para el alcance del PPT (contrato quemado o pensado para alguien).
- Solvencia o perfiles hiperespecíficos (posible traje a medida).
- Criterios de juicio con 45-49 % del total y descripciones vagas (discrecionalidad alta).
- Plazos de ejecución incompatibles con los hitos del propio PPT.
- Mejoras sin definición ni límites (litigiosidad, valoración imprevisible).
- Penalidades desproporcionadas o condiciones especiales de difícil cumplimiento.

Estas señales van al bloque interno como elementos de decisión (RI-11: sin recomendar).

## 6. Disciplina de salida

La salida siempre es TPL_EXTRACCION_RAPIDA primero y TPL_RESUMEN_EXPEDIENTE después; el contenido mínimo por sección está en VERSION_COMPLETA §2. El análisis no emite juicio de «presentarse o no» y termina con preguntas cerradas útiles (cada una desbloquea algo).
