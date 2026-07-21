# TPL_EXTRACCION_RAPIDA — Formato de la extracción rápida obligatoria

> **Propósito:** formato exacto de la primera salida de todo análisis (6 puntos en orden fijo).
> **Cuándo cargarlo:** estado 2 (extracción rápida). **Cuándo no:** en cualquier otra fase.
> **Skills:** 01_EXPEDIENT_ANALYZER. **Prioridad:** alta. **Coste:** bajo.
> **Resumen:** plantilla de los 6 puntos obligatorios con dato literal, referencia y tratamiento de vacíos y lotes. El orden es inalterable y esta salida siempre precede a cualquier otro contenido del análisis.

---

## Formato

```markdown
# 0. Extracción rápida — [Objeto abreviado] (Exp. [número])

| # | Elemento | Dato | Referencia |
|---|---|---|---|
| 1 | **Plazos de ejecución** | [duración total; prórrogas; plazos parciales clave] | [doc., cláusula, pág.] |
| 2 | **Puntos por precio** | [X puntos; fórmula resumida] | [ref.] |
| 3 | **Puntos por mejora** | [X puntos; nº y tipo de mejoras] o «El pliego no contempla mejoras» | [ref.] |
| 4 | **Puntos por memoria** | [X puntos; umbral mínimo si existe] | [ref.] |
| 5 | **Solvencia económica** | [medio y umbral literal abreviado] | [ref.] |
| 6 | **Solvencia técnica** | [medio y umbral literal abreviado] | [ref.] |

**Total criterios:** [X juicio de valor + Y automáticos = 100] · **Presentación:** [fecha y hora límite, plataforma]
```

## Reglas de uso

- Dato no localizado → «**No consta** en la documentación aportada» + documento que probablemente falta.
- Contradicción entre documentos → ambos valores con ambas referencias (RI-19).
- Lotes con condiciones distintas → una tabla por lote o columna por lote.
- Citas literales breves entre comillas cuando el matiz importe (solvencia, fórmulas).
- La fila «Total criterios» y la de presentación son obligatorias aunque no formen parte de los 6 puntos: evitan sustos.
