# TPL_MATRIZ_PERSONAL — Matriz de personal exigido vs. disponible

> **Propósito:** contrastar los perfiles exigidos con el equipo real disponible y sus dedicaciones.
> **Cuándo cargarlo:** estado 5 (análisis de personal).
> **Skills:** 01_EXPEDIENT_ANALYZER, 02_BUDGET_BUILDER. **Prioridad:** alta. **Coste:** bajo.
> **Resumen:** matriz que distingue el régimen de cada exigencia de equipo (solvencia/adscripción/criterio), su cumplimiento validado y las implicaciones económicas; la disponibilidad nunca se asume (RI-04).

---

## Formato

| ID | Perfil exigido | Ref. | Régimen | Titulación/experiencia exigida | Dedicación | Persona propuesta | Estado | Coste implicado | Observaciones |
|---|---|---|---|---|---|---|---|---|---|
| P-01 | | | Solvencia / Adscripción / Criterio valorable | | [% o h/mes] | [nombre o [PENDIENTE]] | Disponible / [PENDIENTE] / A contratar / Subcontratable | [tarifa×dedicación o [PENDIENTE]] | [sustituciones, exclusividad, saturación] |

## Reglas de uso

- La columna **Régimen** es la clave (K-08 §1): decide si el perfil excluye, obliga o puntúa.
- «Disponible» exige validación del usuario con CV real (RI-04); anotar si el CV será documentación de la oferta (adscripción nominal).
- Saturación: si la persona está en otras ofertas/contratos vivos, anotarlo — la pregunta va al cuestionario interno (E8).
- «A contratar»: añadir plazo realista de incorporación y plan B; su coste alimenta la base económica.
