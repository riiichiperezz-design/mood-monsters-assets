# SKILL 04 — SCORING_OPTIMIZER

> **Propósito:** construir la estrategia de puntuación: matriz criterio→evidencia→cobertura→acción, distinción de tipos de mejora y separación de sobres.
> **Cuándo cargarlo:** análisis de criterios, estrategia de puntos, preparación de índice de memoria, tratamiento de mejoras (clases C, E y F).
> **Cuándo no cargarlo:** inventario documental inicial, presupuesto puro, visuales, cuestiones jurídicas.
> **Skills que lo utilizan:** ROUTER; MEMORY exige su matriz; BUDGET recibe mejoras a costear; RED_TEAM contrasta cobertura.
> **Palabras clave:** criterios, puntos, puntuación, scoring, baremo, mejoras, umbral.
> **Dependencias:** criterios extraídos por ANALYZER, K-05, K-06, TPL_MATRIZ_CRITERIOS, CHK_SOBRES.
> **Prioridad:** alta. **Coste de contexto:** medio.
> **Resumen:** transforma el baremo del pliego en un plan de acción: para cada criterio identifica puntos, tipo (fórmula o juicio), umbrales, evidencia esperada por el evaluador, cobertura actual de la empresa, debilidades y acción recomendada con prioridad. Distingue mejora legítima de calidad técnica, información obligatoria, mejora automática, compromiso adicional, riesgo económico y riesgo de mezcla de sobres. Es el puente obligatorio entre el análisis y la memoria.

---

## 1. Nombre
SCORING_OPTIMIZER.

## 2. Propósito
Maximizar la puntuación esperada de la oferta dentro de los límites del pliego (RI-14).

## 3. Responsabilidad única
Estrategia de puntuación. No redacta la memoria ni fija el precio.

## 4. Cuándo se activa
Tras el análisis del expediente, cuando se pregunte por criterios o estrategia, y siempre antes de proponer índice de memoria (P1).

## 5. Cuándo no se activa
Sin criterios extraídos; en fases de recepción o inventario.

## 6. Entradas obligatorias
Criterios de adjudicación completos: puntos, subcriterios, fórmulas, umbrales, sobres, límites de mejoras.

## 7. Entradas opcionales
Capacidades reales de la empresa (validadas), base económica, histórico de licitaciones similares.

## 8. Salidas
Matriz principal:

| Criterio | Puntos | Evidencia esperada | Cobertura actual | Debilidad | Acción recomendada | Prioridad |
|---|---|---|---|---|---|---|

más: mapa de sobres, análisis de fórmula de precio, estrategia de mejoras cuantificada, reparto orientativo de esfuerzo por puntos.

## 9. Flujo interno
1. Clasificar cada criterio: fórmula / juicio de valor; sobre al que pertenece. 2. Analizar la fórmula de precio (pendiente de la curva, valor del punto, zona de baja anormal). 3. Para cada criterio de juicio: inferir la evidencia que el evaluador espera (K-05). 4. Contrastar con cobertura actual (validada o [PENDIENTE]). 5. Detectar debilidades y huecos. 6. Priorizar acciones por puntos en riesgo/esfuerzo. 7. Clasificar mejoras (§11). 8. Verificar separación de sobres (CHK_SOBRES).

## 10. Árbol de decisión
- ¿Criterio con umbral mínimo? → Marcarlo como eliminatorio de facto; prioridad máxima.
- ¿Fórmula de precio muy plana? → Los puntos se ganan en memoria; reasignar esfuerzo.
- ¿Mejora definida por el pliego? → Cuantificar coste (BUDGET) y valor en puntos; decidir el usuario.
- ¿Mejora «libre» no regulada? → Riesgo; tratar con cautela y K-06.
- ¿Contenido dudoso de sobre? → Regla: si es cuantificable por fórmula, fuera de la memoria (RI-05).

## 11. Taxonomía obligatoria
- **Mejora legítima de la calidad técnica:** más valor dentro del objeto, evaluable por juicio; va en memoria.
- **Información obligatoria:** exigida por el pliego; su ausencia resta o excluye.
- **Mejora automática:** puntuada por fórmula/checklist; va en su sobre, nunca en memoria (RI-06).
- **Compromiso adicional:** promesa voluntaria con coste; exige presupuesto (RI-07) y decisión del usuario.
- **Riesgo económico:** mejora cuyo coste erosiona el margen; cuantificar siempre.
- **Riesgo de mezcla de sobres:** contenido que anticipa datos de fórmula; eliminar (RI-05).

## 12. Prohibiciones
Recomendar acciones que infrinjan el pliego (RI-14); dar por existente una capacidad no validada (RI-02/03/04); decidir qué mejoras se ofertan (RI-11); ignorar umbrales mínimos.

## 13. Procedimiento paso a paso
Ver §9; la matriz se entrega ordenada por prioridad y con los puntos en juego totalizados.

## 14. Casos especiales
- **Criterios sociales/medioambientales:** verificar acreditación disponible antes de contar sus puntos.
- **Defensa oral puntuada:** incluirla en la estrategia con su preparación.
- **Varios lotes con baremos distintos:** matriz por lote.

## 15. Gestión de ambigüedad
Criterio vago: descomponer según el tenor literal + K-05; declarar la lectura y proponer consulta al órgano si es material.

## 16. Gestión de información faltante
Cobertura desconocida → `[PENDIENTE]` + pregunta cerrada; la prioridad se calcula igualmente con los puntos en juego.

## 17. Errores habituales
Repartir esfuerzo por igual ignorando pesos; despreciar la fórmula de precio; tratar mejoras automáticas como contenido de memoria; olvidar el umbral mínimo para pasar a la fase económica.

## 18. Checklist
☐ Todos los criterios clasificados y sumando el total ☐ Fórmula de precio analizada ☐ Evidencia esperada por criterio ☐ Cobertura y debilidades ☐ Acciones priorizadas ☐ Mejoras taxonomizadas y costeadas ☐ CHK_SOBRES aplicado.

## 19. Prompt operativo interno
«Clasifica criterios por tipo y sobre; analiza la fórmula de precio; infiere evidencia esperada; contrasta cobertura; construye la matriz de 7 columnas priorizada; taxonomiza mejoras con coste; verifica separación de sobres.»

## 20. Ejemplos de activación
«¿Dónde se gana este concurso?»; «¿qué hacemos con las mejoras?»; «prepara la estrategia de puntuación».

## 21. Ejemplos de salida
Matriz de 7 columnas + resumen: «De los 100 puntos, 51 dependen de juicio de valor; el umbral de 26/51 es eliminatorio; la fórmula de precio concentra 4 puntos por cada 5 % de baja hasta la zona anormal…»

## 22. Relación con otras Skills
Recibe de ANALYZER; alimenta a MEMORY (índice trazado), BUDGET (coste de mejoras), RED_TEAM (contraste de cobertura final).

## 23. Datos que puede compartir
Matriz, prioridades, análisis de fórmula.

## 24. Datos que no puede compartir
No traslada a la memoria ningún dato de fórmula ni estrategia de precio (RI-05).

## 25. Consumo de contexto
Medio.

## 26. Estrategia de ahorro de tokens
Trabajar sobre los criterios ya extraídos; no recargar pliegos; tablas compactas.

## 27. Criterios de calidad
La suma de puntos cuadra con el pliego; cada acción es ejecutable y legal; las prioridades reflejan puntos en juego reales.

## 28. Criterios de parada
Matriz completa entregada con estrategia de mejoras; o bloqueo por criterios no disponibles.
