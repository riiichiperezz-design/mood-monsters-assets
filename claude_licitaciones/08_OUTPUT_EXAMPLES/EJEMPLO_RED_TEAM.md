# EJEMPLO — Informe Red Team

> **Propósito:** ejemplo calibrado de informe Red Team con hallazgos clasificados.
> **Cuándo cargarlo:** primera revisión Red Team. **Cuándo no:** con el formato dominado.
> **Skills:** 05_RED_TEAM_REVIEWER. **Prioridad:** baja. **Coste:** medio.
> **Resumen:** informe sobre el borrador ficticio de la oficina técnica PSTD: veredicto, hallazgos de las cinco severidades con evidencia y propuesta, y registro de decisiones vacío para el estado 15.

---

**⚠️ EJEMPLO FICTICIO** — Informe Red Team, Exp. 2026/00123, borrador v0.9 (28 págs.).

## 1. Alcance
Pasadas ejecutadas: 8/8. Insumos: matriz de criterios ✔ · base económica ✔ · límites formales ✔.

## 2. Resumen ejecutivo
Borrador sólido en metodología (crit. 1.1) pero con **un crítico de mezcla de sobres** y **dos altos** que concentran hasta 8 puntos de riesgo en los criterios 1.2 y 1.3. La corrección estimada afecta a 4 páginas. No presentar sin resolver C-01.

## 3. Veredicto
⛔ **NO PRESENTAR** sin resolver C-01. Altos A-01 y A-02: resolver o asunción expresa del usuario.

## 4. Hallazgos
| ID | Ubicación | Hallazgo | Evidencia | Severidad | Impacto | Propuesta |
|---|---|---|---|---|---|---|
| C-01 | §2.3, pág. 9 | La memoria menciona «150 horas adicionales de refuerzo sin coste» — es la mejora del criterio automático 2.2 | «…complementado con una bolsa de 150 horas…» | 🔴 Crítico | Mezcla de sobres → exclusión (RI-05/06) | Eliminar la frase y el bloque; verificar Gantt y tabla de dedicaciones; re-pasar CHK_SOBRES completo |
| A-01 | §4, pág. 17 | El organigrama asigna al «responsable de calidad» 8 h/mes que no existen en la base económica | Organigrama vs. base econ. §2 | 🟠 Alto | Compromiso no presupuestado (RI-07): margen −0,9 pts o incumplimiento | Presupuestar las 192 h o reasignar la función a la directora dentro de sus horas |
| A-02 | §5, pág. 21 | El criterio 1.3 exige «procedimiento de subsanación de reparos del gestor» (PCAP anexo IV) y el borrador no lo trata | Anexo IV, crit. 1.3.c | 🟠 Alto | Hueco de cobertura: hasta 4 pts | Añadir subapartado 5.4 (½ pág.) con el circuito de respuesta a reparos, plazos y responsable |
| M-01 | §3, pág. 13 | El Gantt sitúa la justificación S1 en el mes 7; el texto dice mes 6 | Gantt vs. §5.2 | 🟡 Medio | Incoherencia texto↔visual (K-14 §3) | Unificar en mes 6 (coherente con el plazo del gestor) y regenerar el Gantt |
| B-01 | §1, pág. 2 | Se cita «Diputación de Vallehermoso» en documento que exige anonimato… del licitador, no del órgano | PCAP anexo V | 🔵 Bajo | Ninguno (el anonimato afecta al licitador); se anota para tranquilidad | Ninguna acción; verificar que ninguna página identifica a la empresa (verificado: ✔) |
| E-01 | §2.1, pág. 6 | «Enfoque integral y holístico de la gestión» | — | ⚪ Editorial | Lenguaje vacío (K-17 §2) | Delegar en EDITORIAL: sustituir por las 3 dimensiones concretas que ya se describen después |

## 5. Registro de decisiones (a completar por el usuario — estado 15)
| ID | Decisión | Estado final | Re-verificado |
|---|---|---|---|
| C-01 | | | |
| A-01 | | | |
| A-02 | | | |

*(Nota de calibración: cada hallazgo tiene ubicación, evidencia citada, severidad justificada y propuesta ejecutable; el informe no corrige nada por su cuenta.)*
