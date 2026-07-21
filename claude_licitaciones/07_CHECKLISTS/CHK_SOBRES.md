# CHK_SOBRES — Control de separación estricta de sobres

> **Propósito:** verificar la separación de sobres (RI-05/06) en los tres momentos críticos.
> **Cuándo cargarlo:** redacción (WF_07), mejoras (WF_08) y Red Team (WF_09).
> **Skills:** 04_SCORING_OPTIMIZER, 05_RED_TEAM_REVIEWER. **Prioridad:** media. **Coste:** bajo.
> **Resumen:** lista de vulneraciones directas y sutiles; su incumplimiento causa exclusión.

---

## En el sobre de juicio de valor (memoria) NO puede aparecer ni deducirse
- ☐ Precio, % de baja, importes de la oferta económica
- ☐ Existencia, número o alcance de mejoras evaluables automáticamente (RI-06)
- ☐ Plazos/garantías/bolsas ofertados como criterio automático
- ☐ Cualquier dato que permita reconstruir lo anterior

## Vulneraciones sutiles (revisar una a una)
- ☐ Cronograma que revela el plazo reducido ofertado (usar el plazo del pliego)
- ☐ Organigrama/equipo que incluye el personal adicional de una mejora automática
- ☐ Presupuestos «orientativos» o desgloses económicos en la memoria
- ☐ Visuales, tablas o anexos con cifras del sobre económico
- ☐ Frases tipo «además, sin coste adicional ofrecemos…» (mejora encubierta)

## En el sobre automático
- ☐ Modelos oficiales usados sin alterar su estructura
- ☐ Oferta en las unidades exactas de la fórmula (%, importe, número)
- ☐ Coherencia aritmética (decimales, letras vs. cifras según pliego)
- ☐ Mejoras documentadas de forma autocontenida

## Meta-verificación
- ☐ ¿Qué exige exactamente el pliego sobre qué va en cada sobre? Releído y aplicado (RI-01)
- ☐ Anonimato de la memoria verificado si el pliego lo exige (sin logos, nombres ni referencias identificativas)
