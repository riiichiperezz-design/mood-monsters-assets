---
name: red-team
description: Revisión adversarial (Red Team) de una memoria técnica ya redactada — cobertura de criterios, coherencia, trazabilidad, separación de sobres, compromisos no presupuestados, información inventada e incumplimientos formales. Úsala cuando el usuario pida "revisa la memoria", "pásale el red team", "audita antes de presentar", "¿se nos escapa algo?". No corrige en silencio: señala y propone.
---

# Red Team

Ejecuta los estados 13-14. Requiere un borrador en `03_memoria/memoria.md`.

## Archivos a cargar

- `claude_licitaciones/02_SKILLS/05_RED_TEAM_REVIEWER.md`
- `claude_licitaciones/03_WORKFLOWS/WF_09_REVISION_RED_TEAM.md`
- `claude_licitaciones/04_KNOWLEDGE/14_CALIDAD_Y_CONTROL.md`
- `claude_licitaciones/06_TEMPLATES/TPL_RED_TEAM.md`
- `claude_licitaciones/07_CHECKLISTS/CHK_RED_TEAM.md` y `CHK_SOBRES.md`
- Para contrastar: `01_analisis/criterios.md` (cobertura) y `02_economico/base_economica.md` (RI-07).

## Procedimiento

1. **Revisión de cobertura (estado 13):** contrasta la memoria contra la matriz de criterios; corrige huecos antes del red team.
2. **Ocho pasadas (estado 14):** formal → cumplimiento/sobres → evaluador → coherencia → económica → veracidad → editorial → clasificación.
3. Emite el informe (TPL_RED_TEAM): cada hallazgo con ubicación, evidencia, severidad (crítico/alto/medio/bajo/editorial), impacto y **propuesta de solución**. Veredicto de preparación.
4. **No modifiques el borrador** (RI del sistema): el usuario decide sobre cada hallazgo crítico/alto; después, si lo pide, aplica las correcciones con `/redactar-memoria` (EDITORIAL para estilo) y re-verifica sin regresiones.

## Salida

Guarda el informe en `expedientes/<NOMBRE>/04_revision/red_team.md`. Actualiza el `README.md`. Presenta en el chat el veredicto y los hallazgos críticos. No des la oferta por lista si hay críticos abiertos.
