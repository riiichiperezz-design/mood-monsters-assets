# TPL_MATRIZ_REQUISITOS — Matriz requisito-fuente-cumplimiento-evidencia

> **Propósito:** trazar cada requisito del expediente hasta su cumplimiento y evidencia.
> **Cuándo cargarlo:** análisis detallado de requisitos y verificación final (Red Team).
> **Skills:** 01_EXPEDIENT_ANALYZER, 05_RED_TEAM_REVIEWER. **Prioridad:** alta. **Coste:** bajo.
> **Resumen:** matriz de trazabilidad de requisitos con estado y evidencia; sirve tanto para preparar la oferta como para auditarla antes de presentar.

---

## Formato

| ID | Requisito (literal abreviado) | Fuente (doc./cláusula) | Tipo | Obligatorio/Valorable | Estado | Cómo se cumple / dónde se responde | Evidencia |
|---|---|---|---|---|---|---|---|
| R-01 | | | Adm./Técnico/Formal | | ✔ Cubierto / ◐ Parcial / ✘ Sin cubrir / [PENDIENTE] | [apartado de la oferta o documento] | [certificado, declaración, apartado] |

## Reglas de uso

- Un requisito por fila; los compuestos se descomponen.
- «Tipo formal» incluye límites de páginas, estructura, formatos y firmas: también son requisitos.
- La columna «dónde se responde» conecta con el índice de la memoria (K-02): ningún requisito sin casa.
- En Red Team, la matriz se recorre entera: todo ✘ u ◐ es hallazgo (severidad según VERSION_COMPLETA §6).
