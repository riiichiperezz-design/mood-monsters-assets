# TPL_MATRIZ_SOLVENCIA — Matriz de solvencia exigida vs. acreditación

> **Propósito:** contrastar cada requisito de solvencia con la capacidad real y su documentación.
> **Cuándo cargarlo:** estado 4 (validación de solvencia).
> **Skills:** 01_EXPEDIENT_ANALYZER. **Prioridad:** alta. **Coste:** bajo.
> **Resumen:** matriz con el literal exigido, el medio de acreditación, las alternativas admitidas y el estado validado por el usuario; nada se marca acreditable sin validación (RI-03).

---

## Formato

| ID | Requisito (literal) | Ref. | Medio de acreditación | Alternativas admitidas | Capacidad declarada | Estado | Documentación a preparar | Plazo/gestión |
|---|---|---|---|---|---|---|---|---|
| S-E1 | [solvencia económica] | | [cuentas, certificado, seguro] | [clasificación G/S/C, medios externos] | [dato del usuario o [PENDIENTE]] | Acreditable / [PENDIENTE] / En riesgo / No acreditable | | [p. ej. pedir certificado a cliente X: 3-4 semanas] |
| S-T1 | [solvencia técnica] | | | | | | | |

## Reglas de uso

- Estado «Acreditable» solo con validación expresa del usuario (RI-03).
- «En riesgo» = interpretación dudosa del requisito (¿similar?, ¿anualidad?) → nota con las lecturas y, si es material, consulta al órgano o PROCUREMENT.
- «No acreditable» → escalar con alternativas (UTE, medios externos) para decisión del usuario (RI-11/20).
- La columna de plazos existe porque los certificados de buena ejecución tardan: gestionarlos desde el análisis (K-07 §3).
