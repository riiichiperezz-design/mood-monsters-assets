# GUÍA DE USO — Manual del día a día

> **Propósito:** manual de utilización diaria: peticiones tipo, flujo recomendado y buenas prácticas.
> **Cuándo cargarlo:** al aprender a usar el sistema. **Cuándo no:** en el trabajo operativo (el sistema ya sabe operar).
> **Prioridad:** baja. **Coste:** bajo.
> **Resumen:** el ciclo completo con las peticiones exactas que conviene escribir en cada fase, qué esperar de cada una, cómo responder a las preguntas del sistema y los errores de uso que degradan los resultados.

---

## 1. El ciclo en 8 pasos (peticiones tipo)

| Paso | Tú escribes | El sistema entrega |
|---|---|---|
| 1. Análisis | *«Analiza este expediente»* + PCAP, PPT y anexos | Extracción rápida (6 puntos) → análisis completo → bloque interno → preguntas cerradas |
| 2. Solvencia/equipo | *«¿Podemos cumplir solvencia y personal? Estos son nuestros datos: …»* | Matrices de solvencia y personal con estados y gestiones documentales |
| 3. Criterios | *«Estrategia de puntuación»* | Matriz de criterios, análisis de fórmula, mapa de sobres, mejoras costeadas |
| 4. Viabilidad | *«¿Es viable? Tarifas: senior X €/h…»* | Base económica con 3 escenarios, márgenes, sensibilidades y advertencias |
| 5. Decisión | **La tomas tú** (*«avanzamos»*) | El sistema no la toma nunca (RI-11) |
| 6. Índice | *«Prepara el índice de la memoria»* | Índice trazado criterio↔apartado↔páginas + lista de información interna necesaria |
| 7. Redacción | *«Apruebo el índice; redacta los apartados 1-3»* (por lotes) | Apartados con ficha estándar, compromisos medibles, [PENDIENTE] visibles |
| 8. Revisión | *«Red Team completo»* → decides sobre hallazgos → *«aplica C-01 y A-02»* → *«checklist final»* | Informe clasificado → correcciones → CHK_PRESENTACION_FINAL |

Peticiones sueltas también funcionan («hazme el Gantt», «¿es subsanable X?», «pule el apartado 4»): el Router carga solo lo necesario.

## 2. Cómo responder a las preguntas del sistema

- Son **cerradas** y cada una desbloquea algo: contéstalas con datos, no con «sí, tenemos experiencia» (di cuál, con importes y certificados).
- Si no tienes el dato: dilo; el sistema trabajará con variables abiertas o te propondrá una hipótesis que **tú autorizas**.
- Atajo permanente: mantén al día el documento `DATOS_EMPRESA.md` (ver instalación §6).

## 3. Qué exigirle al sistema (y qué te exigirá él)

- Toda cifra con etiqueta y referencia; si ves un dato sin [EXPEDIENTE]/[ESTIMACIÓN]/…, reclámalo.
- Si pides una fase fuera de orden (memoria sin criterios), se detendrá y hará primero lo mínimo pendiente: es diseño, no desobediencia (RI-12/13/20).
- El Red Team no reescribe: te da hallazgos y decides. Pedirle «corrige tú directamente» rompe el control de calidad.

## 4. Errores de uso que degradan resultados

Subir el expediente a trozos sin avisar (inventario incompleto) · confirmar capacidades «de palabra» que luego no existen (el sistema las tratará como validadas: RI-03/04 protegen hasta donde tu palabra alcanza) · pedir «la memoria entera de golpe» (la calidad se produce por lotes) · ignorar las advertencias de margen · saltarte el checklist final por prisa (es donde se evitan las exclusiones tontas).

## 5. Varias licitaciones a la vez

Una conversación por expediente (el estado del workflow vive en la conversación). El Project es común; el contexto de cada expediente, separado. Para retomar: «¿en qué estado está este expediente?» — el sistema lo reconstruye desde la conversación.

## 6. Después de presentar

La conversación sirve para: requerimientos de subsanación, justificación de baja anormal (reabre la base económica) y preparación de alegaciones o defensa (WF_10 §5). Guarda el análisis y la base económica: alimentan las lecciones aprendidas y la próxima oferta similar.
