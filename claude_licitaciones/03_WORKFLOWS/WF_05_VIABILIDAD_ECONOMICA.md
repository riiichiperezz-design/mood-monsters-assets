# WF_05 — Identificación de costes y preguntas internas

> **Propósito:** procedimiento de los estados 7-8: convertir el PPT en necesidades económicas completas y consolidar las preguntas internas antes de presupuestar.
> **Cuándo cargarlo:** al iniciar el estudio de viabilidad o cuando el usuario pregunte por costes sin base económica previa.
> **Cuándo no cargarlo:** con el inventario de costes ya hecho (pasar a WF_06); en fases documentales.
> **Skills que lo utilizan:** BUDGET (E7), ROUTER (E8, consolidación).
> **Palabras clave:** viabilidad, costes, necesidades económicas, preguntas internas.
> **Dependencias:** WF_MASTER (E7-E8), K-09, CHK_COSTES.
> **Prioridad:** alta. **Coste de contexto:** bajo.
> **Resumen:** primer tramo económico. Convierte cada obligación del PPT en necesidades cuantificables (tarea × frecuencia × volumen × recursos), barre el catálogo completo de categorías de coste incluyendo los sistemáticamente olvidados (coordinación, reuniones, revisión, seguimiento, cierre), y consolida todas las incógnitas en un único cuestionario interno de preguntas cerradas ordenado por criticidad. Prohíbe valorar en euros lo que carece de tarifa: eso pertenece a WF_06 con datos o hipótesis declaradas.

---

## 1. Objetivo y estados cubiertos
Estados 7 (Identificación de costes) y 8 (Preguntas internas).

## 2. Entrada
Análisis del expediente (WF_02) con el PPT descompuesto en obligaciones; matrices de solvencia/personal si existen.

## 3. Pasos — Estado 7 (identificación de costes)

1. **Verificar RI-13:** si el PPT no está descompuesto en obligaciones, volver a WF_02.
2. **Convertir obligaciones en unidades costeables:** tarea × frecuencia × volumen × duración (p. ej. «12 informes mensuales × revisión de 2 niveles», «8 talleres × 2 técnicos × desplazamiento a comarca»).
3. **Asignar recursos por unidad:** perfil y horas [ESTIMACIÓN] con supuesto declarado.
4. **Barrer el catálogo completo** (BUDGET §11): personal, dirección, coordinación, producción, revisión, viajes, alojamiento, dietas, talleres/eventos, materiales, diseño, impresión, licencias, software, plataformas, compras, subcontratación, gastos generales, contingencia, beneficio, impuestos.
5. **Costes ocultos obligatorios (RI-08):** reuniones y comités del pliego, gestión de cambios, informes de seguimiento, cierre y transferencia, garantía si existe.
6. **Clasificar cada partida:** directo/indirecto, interno/externo, fijo/variable.
7. **Contrastar CHK_COSTES:** ninguna obligación sin reflejo.

## 4. Pasos — Estado 8 (preguntas internas)

1. Consolidar pendientes de E3-E7 en un **cuestionario único** sin duplicados.
2. Ordenar por criticidad: excluyentes (solvencia, personal) → económicas (tarifas, límites de precio) → estratégicas (subcontratación, mejoras, desplazamientos).
3. Formato cerrado con desbloqueo: «¿Tarifa hora del consultor senior? → desbloquea escenarios de E9».
4. Máximo 12 preguntas; el resto, hipótesis declaradas de bajo riesgo.
5. Entregar y **esperar respuestas o autorización para trabajar con hipótesis** antes de E9.

## 5. Salida
Inventario de necesidades económicas clasificado + cuestionario interno único.

## 6. Bloqueos
Obligaciones sin descomponer (RI-13). El paso a E9 sin respuestas exige hipótesis declaradas y aceptadas.

## 7. Criterio de finalización
Catálogo barrido al completo; cuestionario entregado.

## 8. Errores habituales
Poner euros sin tarifa (adelantarse a E9 inventando); olvidar la dedicación de dirección; no contar desplazamientos de reuniones ordinarias; ignorar el coste de producir las propias ofertas de mejora.

## 9. Conexiones
WF_06 construye los escenarios sobre este inventario. Las respuestas del cuestionario actualizan también las matrices de WF_03.
