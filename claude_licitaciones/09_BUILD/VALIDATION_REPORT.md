# VALIDATION_REPORT — Informe de validación del sistema v1.0.0

> **Propósito:** resultado de las verificaciones estructurales y de las 8 pruebas funcionales del sistema.
> **Cuándo cargarlo:** en mantenimiento, auditoría o antes de una nueva versión. **Cuándo no:** en el trabajo operativo.
> **Prioridad:** baja. **Coste:** bajo.
> **Resumen:** validación estructural (97/97 módulos, cero dependencias rotas, cabeceras completas) y funcional (8/8 pruebas superadas en recorrido en seco sobre las reglas del sistema), limitaciones conocidas y recomendaciones para la v2.

---

## 1. Validación estructural (automatizada, 2026-07-21)

| Verificación | Resultado |
|---|---|
| Módulos declarados en MANIFEST.json | 97 |
| Archivos presentes en disco | 97/97 ✔ |
| Módulos del manifiesto sin archivo | 0 ✔ |
| Archivos sin registrar en el manifiesto | 0 ✔ |
| Dependencias del manifiesto rotas | 0 ✔ |
| Archivos .md con cabecera completa (propósito, activación, dependencias, prioridad, coste, resumen) | 97/97 ✔ |
| Reglas transversales definidas una sola vez (REGLAS_INVIOLABLES) y citadas por ID (RI-nn) | ✔ (muestreo en Skills, workflows y conocimiento) |

## 2. Pruebas funcionales (recorrido en seco contra las reglas del sistema)

Método: para cada prueba se verifica que las instrucciones centrales, el Router, la Skill responsable y las plantillas producen el comportamiento esperado, y que ninguna regla permite el comportamiento contrario.

**Prueba 1 — PCAP+PPT y petición de análisis.** Router clase A → ANALYZER → TPL_EXTRACCION_RAPIDA precede a todo (instrucciones §Flujo 1; WF_MASTER E2 prohíbe saltarla) → análisis 13 secciones → bloque interno sin decisión (RI-11 en TPL_CONCLUSION_INTERNA). Sin memoria (E12 inaccesible desde E0-E5). **✔ SUPERADA.**

**Prueba 2 — Presupuesto sin tarifas.** Router clase D → BUDGET §10: «¿Hay tarifas? → No: variables abiertas [PENDIENTE] + preguntas cerradas»; RI-02 prohíbe inventarlas; TPL_BASE_ECONOMICA exige partidas [PENDIENTE] visibles; identificación de costes completa vía CHK_COSTES. **✔ SUPERADA.**

**Prueba 3 — Memoria sin análisis de criterios.** Router P1 (RI-12) bloquea MEMORY sin matriz de criterios; ejecuta clase C, propone índice (E11) e identifica pendientes internos; WF_MASTER prohíbe E12 sin E11 aprobado (RI-20). **✔ SUPERADA.**

**Prueba 4 — Obligación en PPT ausente del PCAP.** RI-19 + K-01 §4 (cruce documental obligatorio con doble cita e implicación) + WF_02 §4.3; jerarquía de fuentes y vía de aclaración al órgano (K-18 §9.1). La discrepancia no puede ocultarse (RI-19 es inviolable). **✔ SUPERADA.**

**Prueba 5 — Mejora automática.** SCORING §11 la clasifica; RI-06 la mantiene fuera de la memoria; WF_08 la documenta en su sobre con advertencia expresa y BUDGET la cuantifica (coste y €/punto); CHK_SOBRES verifica en tres momentos. **✔ SUPERADA.**

**Prueba 6 — Memoria promete acciones no presupuestadas.** RED_TEAM pasada 5 (económica) contra la base económica → hallazgo con severidad (alto/crítico según cuantía, VERSION_COMPLETA §6) → propone corregir, limitar o presupuestar → decide el usuario (E15). No hay corrección silenciosa (Skill 05 §3). **✔ SUPERADA.**

**Prueba 7 — «¿Debemos presentarnos?».** RI-11 en instrucciones, Router §12, ANALYZER §12, BUDGET §12 y TPL_CONCLUSION_INTERNA: se presentan implicaciones, riesgos y condiciones; la decisión queda expresamente reservada al usuario. **✔ SUPERADA.**

**Prueba 8 — Petición de un SVG.** Router clase H → VISUAL + K-16 + datos de origen; exclusión expresa de módulos jurídicos y económicos (Router §10 fila H; CONTEXT_LOADING_GUIDE §3). **✔ SUPERADA.**

## 3. Limitaciones conocidas (v1.0.0)

1. **Sin documentos de referencia de la empresa:** el repositorio no contenía las memorias modelo previstas (ÁGORA, Gran Tour Cáceres, ENEB, materiales internos). El sistema se construyó desde doctrina experta general; al incorporarlos, abstraer sus patrones hacia K-02/K-03/K-05 y los playbooks (RI-09).
2. **Vigencia normativa:** K-18 refleja el marco LCSP con la advertencia RI-15; umbrales y plazos deben verificarse por expediente.
3. **Las pruebas funcionales son recorridos en seco** sobre las reglas, no ejecuciones con expedientes reales dentro de un Project; la primera semana de uso real debe tratarse como periodo de rodaje (afinar preguntas, plantillas y DATOS_EMPRESA.md).
4. **Claude Projects no ejecuta un «router» mecánico:** el enrutado depende de que las instrucciones y las cabeceras guíen la atención del modelo; la carga selectiva es probabilística, no determinista. Mitigación: instrucciones compactas + cabeceras uniformes + CONTEXT_LOADING_GUIDE.
5. Los ejemplos usan un único caso ficticio (oficina técnica PSTD); añadir ejemplos de otras tipologías en v1.1 aumentaría la calibración.

## 4. Recomendaciones para la v2

1. Incorporar y abstraer las memorias de referencia reales (patrones de estructura, verbos, evidencias y visuales ganadores).
2. Crear `DATOS_EMPRESA.md` real y un playbook interno de referencias acreditables.
3. Añadir 2-3 ejemplos calibrados por tipología frecuente (plan estratégico, campaña, observatorio).
4. Plantillas .docx corporativas conectadas al sistema (posible integración con la skill de generación Word existente).
5. Registro de lecciones aprendidas por expediente (WF_10 §4.3) que alimente K-05 y K-09 con datos propios (tarifas reales, desviaciones).
6. Revisión semestral de K-18 y PB_07 (normativa y marcos de fondos).
