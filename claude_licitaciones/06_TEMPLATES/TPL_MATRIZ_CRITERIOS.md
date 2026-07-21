# TPL_MATRIZ_CRITERIOS — Matriz de criterios de adjudicación

> **Propósito:** la matriz central de estrategia de puntuación (7 columnas) más el mapa de sobres.
> **Cuándo cargarlo:** estados 6, 10 y 13 (criterios, estrategia, cobertura).
> **Skills:** 04_SCORING_OPTIMIZER. **Prioridad:** alta. **Coste:** bajo.
> **Resumen:** matriz criterio→puntos→evidencia→cobertura→debilidad→acción→prioridad, con clasificación de tipo y sobre, análisis de fórmula de precio y taxonomía de mejoras. Los puntos deben sumar el total del pliego.

---

## Formato principal

| Criterio | Puntos | Evidencia esperada | Cobertura actual | Debilidad | Acción recomendada | Prioridad |
|---|---|---|---|---|---|---|
| [1.1 nombre del pliego] | | [qué querrá ver el evaluador — K-05 §2] | Alta / Media / Baja / [PENDIENTE] | | | 🔴 Alta / 🟡 Media / 🟢 Baja |

**Verificación:** Σ puntos = [total del pliego] ✔ · Umbrales mínimos: [criterio X exige ≥N puntos]

## Bloques complementarios

**Mapa de sobres:**
| Sobre | Contenido | Prohibido que aparezca en |
|---|---|---|
| B (juicio) | memoria… | — |
| C (automático) | precio, mejoras M1-M2… | Sobre B (RI-05) |

**Fórmula de precio:** [fórmula literal] → valor del punto: [X pts por cada 5 % de baja] · zona de baja anormal: [estimación] · lectura operativa: [dónde pesa el precio].

**Taxonomía de mejoras (K-06/SCORING §11):**
| Mejora | Clasificación | Coste | Puntos | €/punto | Sobre | Decisión usuario |
|---|---|---|---|---|---|---|

## Reglas de uso

Prioridad = puntos en riesgo × viabilidad de la acción · cobertura [PENDIENTE] no impide priorizar · toda acción respeta el pliego (RI-14) · la matriz se re-verifica en el estado 13 contra el borrador real.
