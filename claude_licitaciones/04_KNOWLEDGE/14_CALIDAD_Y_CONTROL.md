# K-14 — Calidad y control

> **Propósito:** doctrina de control de calidad de ofertas: cobertura, coherencia, veracidad y cumplimiento formal.
> **Cuándo cargarlo:** revisiones (estados 13-15) y diseño del apartado de calidad de la memoria.
> **Cuándo no cargarlo:** en fases de análisis o presupuestación.
> **Skills que lo utilizan:** 05_RED_TEAM_REVIEWER.
> **Palabras clave:** calidad, control, verificación, revisión.
> **Dependencias:** TPL_RED_TEAM, CHK_MEMORIA, CHK_SOBRES, CHK_RED_TEAM.
> **Prioridad:** media. **Coste de contexto:** medio.
> **Resumen:** las dos caras del control de calidad: (1) el control de la propia oferta —los cuatro planos de verificación (formal, cumplimiento, puntuación, coherencia), la técnica de revisión con cambio de rol, los pares de coherencia que siempre se contrastan y la disciplina de no corregir en silencio—; y (2) el sistema de control de calidad que se propone en la memoria como contenido evaluable (revisión por niveles, estándares aplicables, no conformidades y mejora continua), dimensionado para ser real y presupuestable.

---

## 1. Los cuatro planos de verificación de una oferta

1. **Formal:** límites (páginas, fuente, estructura), anexos, modelos oficiales, firmas, formato de archivos. Fallo aquí = riesgo de exclusión con la mejor memoria del mundo.
2. **Cumplimiento:** todo lo obligatorio está; nada prohibido está (sobres, RI-05/06); requisitos con respuesta.
3. **Puntuación:** cada criterio con cobertura proporcional y evidencia (contraste con la matriz de SCORING).
4. **Coherencia:** la oferta cuenta una sola historia (§3).

El orden importa: formal y cumplimiento antes que puntuación (de nada sirve pulir lo que excluye).

## 2. Técnica de revisión con cambio de rol

El revisor no es el redactor defendiendo su texto: adopta el rol de (a) secretario de mesa buscando causas de exclusión, (b) evaluador con rúbrica y poco tiempo, (c) director de proyecto que heredará los compromisos. Cada rol encuentra defectos distintos. En este sistema, el cambio de rol lo institucionaliza RED_TEAM; la regla de oro es **señalar y proponer, nunca corregir en silencio** — la corrección silenciosa destruye la trazabilidad de decisiones y puede introducir regresiones invisibles.

## 3. Pares de coherencia obligatorios

Plan ↔ cronograma (mismas fases y fechas) · plan ↔ equipo (quién hace cada cosa existe y tiene dedicación) · entregables ↔ plan (cada entregable nace de una actividad) · KPIs ↔ compromisos (se mide lo prometido) · riesgos ↔ plan (los riesgos citan actividades reales) · gobernanza ↔ dedicaciones · memoria ↔ base económica (RI-07) · texto ↔ visuales · terminología única en toda la oferta.

## 4. Clasificación y disciplina de hallazgos

Severidades (crítico/alto/medio/bajo/editorial) según VERSION_COMPLETA §6; ante duda, la mayor. Cada hallazgo: ubicación exacta + evidencia + impacto + propuesta. El usuario decide sobre críticos y altos; el registro final documenta resuelto/asumido (WF_09 §5).

## 5. El apartado de calidad de la memoria (contenido evaluable)

Sistema propuesto, proporcionado y real:

- **Revisión por niveles:** autor → revisor técnico → responsable de calidad/dirección (2 niveles en contratos pequeños, 3 en grandes). Con tiempos presupuestados (RI-07).
- **Estándares de referencia:** solo los que la empresa realmente aplica o certifica (RI-02); citar la certificación validada si existe.
- **Control de entregables:** checklist de salida por tipo de entregable (conexión K-04 §3).
- **No conformidades y mejora:** registro, análisis de causas en el comité (K-11), acción correctiva verificada — ciclo PDCA aplicado al contrato, no como póster.
- **Indicadores de calidad:** los del bloque calidad de K-13 §1.

## 6. Errores caros

Pulir estilo antes que fondo · revisar sin la matriz de criterios delante · «aprobar» por cansancio la víspera del plazo · prometer en el apartado de calidad revisiones que las horas presupuestadas no permiten · corregir un hallazgo creando otro (siempre re-verificar, WF_09 §5.3).
