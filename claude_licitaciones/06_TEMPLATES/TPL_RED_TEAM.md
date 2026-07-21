# TPL_RED_TEAM — Informe de revisión adversarial

> **Propósito:** formato del informe Red Team con hallazgos clasificados y veredicto.
> **Cuándo cargarlo:** estado 14 (Red Team).
> **Skills:** 05_RED_TEAM_REVIEWER. **Prioridad:** alta. **Coste:** bajo.
> **Resumen:** informe con resumen ejecutivo, tabla de hallazgos (ubicación, evidencia, severidad, impacto, propuesta), veredicto de preparación y registro de decisiones para el estado 15. Nada se corrige en el informe: se señala y se propone.

---

## Formato

```markdown
# Informe Red Team — [Objeto] · versión revisada: [v/fecha]

## 1. Alcance de la revisión
Pasadas ejecutadas: [8/8 o cuáles] · Insumos disponibles: matriz de criterios ✔ base económica ✔/✘ [si falta algo, qué no se pudo verificar]

## 2. Resumen ejecutivo
[3-6 líneas: estado general, nº de hallazgos por severidad, los 2-3 problemas que más puntos o riesgo concentran]

## 3. Veredicto
⛔ NO PRESENTAR sin resolver: [C-01, C-02] / ⚠️ Presentable tras resolver altos / ✅ Sin hallazgos bloqueantes

## 4. Hallazgos
| ID | Ubicación (apartado/pág.) | Hallazgo | Evidencia (cita o dato) | Severidad | Impacto | Propuesta de solución |
|---|---|---|---|---|---|---|
| C-01 | §5, pág. 23 | El organigrama incluye al técnico adicional ofertado como mejora automática | «…» | 🔴 Crítico | Mezcla de sobres → exclusión (RI-05) | Retirar del organigrama; verificar resto de visuales |
| A-01 | | | | 🟠 Alto | | |
| M-01 | | | | 🟡 Medio | | |
| B-01 | | | | 🔵 Bajo | | |
| E-01 | | | | ⚪ Editorial | | [delegar en EDITORIAL] |

## 5. Registro de decisiones (se completa en el estado 15)
| ID | Decisión del usuario | Estado final | Re-verificado |
|---|---|---|---|
```

## Reglas de uso

Severidades según VERSION_COMPLETA §6; ante duda, la mayor · cada hallazgo con ubicación exacta y evidencia citada · propuesta siempre (señalar sin proponer es medio trabajo) · el informe no modifica el borrador (Skill 05 §3).
