# TPL_PLAN_DE_TRABAJO — Formato del plan de trabajo

> **Propósito:** formato del plan por fases y actividades con dependencias, hitos y validaciones.
> **Cuándo cargarlo:** desarrollo del plan (Skill 08) y su apartado de memoria.
> **Skills:** 08_PLANNING_ENGINE. **Prioridad:** alta. **Coste:** bajo.
> **Resumen:** tablas de fases, actividades e hitos con las validaciones del cliente como actividades visibles y la ruta crítica declarada; datos listos para el Gantt de VISUAL.

---

## Formato

```markdown
## Plan de trabajo — [horizonte: M1-M12, desde formalización]

### Fases
| Fase | Objetivo | Periodo | Entregables clave |
|---|---|---|---|

### Actividades
| ID | Actividad (verbo de acción) | Fase | Depende de | Duración | Periodo | Responsable | Producto |
|---|---|---|---|---|---|---|---|
| A1.1 | | F1 | — | | M1 | | |
| V1 | Validación del órgano: [entregable] | F1 | A1.x | [10-15 días háb.] | | Órgano | Acta de aceptación |

### Hitos
| Hito | Fecha/Mes | Origen (pliego/propuesta) | Condición de superación |
|---|---|---|---|

### Ruta crítica y holguras
Ruta crítica: [A1.2 → V1 → A2.1 → …] · Holgura total: [X semanas, en fase Y]
Protección: [medidas concretas — arranque anticipado de Z, refuerzo en W]

### Riesgos temporales
[Tensiones detectadas contra plazos del pliego, con medida — sin disimular (K-12 §1)]
```

## Reglas de uso

Validaciones del cliente SIEMPRE como filas V-n con duración · hitos del pliego marcados con su referencia · tiempo relativo (M1…) si no hay fecha de formalización · coherencia total con cronograma visual, equipo y entregables (K-14 §3) · sin plazos de criterios automáticos si son mejora ofertada (RI-05).
