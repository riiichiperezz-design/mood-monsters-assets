# TPL_CONCLUSION_INTERNA — Bloque interno breve

> **Propósito:** formato del bloque interno de cierre de análisis para la decisión del usuario.
> **Cuándo cargarlo:** cierre de análisis (estado 3) y punto de decisión (estado 9).
> **Skills:** 01_EXPEDIENT_ANALYZER, 02_BUDGET_BUILDER. **Prioridad:** alta. **Coste:** bajo.
> **Resumen:** bloque compacto con solvencias, personal, criterios, riesgos y conclusión operativa; presenta implicaciones y condiciones sin emitir jamás la decisión de avanzar o desestimar (RI-11).

---

## Formato

```markdown
## Bloque interno — [Objeto abreviado]

| Dimensión | Situación | Semáforo |
|---|---|---|
| Solvencia económica | [acreditable/pendiente/en riesgo + 1 línea] | 🟢/🟡/🔴 |
| Solvencia técnica | | 🟢/🟡/🔴 |
| Personal exigido | [disponible/pendiente/a contratar + 1 línea] | 🟢/🟡/🔴 |
| Criterios de adjudicación | [dónde se gana: X pts juicio / Y automáticos; umbrales] | 🟢/🟡/🔴 |
| Riesgos | [los 2-3 dominantes] | 🟢/🟡/🔴 |

**Conclusión operativa:** [3-6 líneas: condiciones bajo las que el expediente es abordable, qué lo haría inviable, qué información falta para decidir. SIN «recomendamos presentarse/no presentarse» — la decisión es del usuario (RI-11).]

**Para decidir necesitas responder:** [las 2-4 preguntas críticas del cuestionario E8]

**Siguiente paso propuesto:** [estado del workflow que sigue]
```

## Reglas de uso

Semáforos con criterio declarado (🔴 = bloqueo potencial; 🟡 = pendiente de validación; 🟢 = validado) · la conclusión describe condiciones («abordable si se confirma X y se acepta un margen del Y %»), no veredictos · máximo una página equivalente.
