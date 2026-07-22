---
name: base-economica
description: Construye la base económica de un expediente — convierte las obligaciones del pliego en costes, monta escenarios (mínimo/probable/conservador), calcula márgenes, sensibilidades y punto de equilibrio, y advierte de márgenes bajos. Úsala cuando el usuario pregunte "¿es rentable?", "hazme el presupuesto", "¿cuánto cuesta ejecutarlo?", "¿a qué precio ofertamos?" o para valorar mejoras. Uso interno: NUNCA se traslada a la memoria.
---

# Base económica

Ejecuta los estados 7-9 del workflow. Es el paso previo obligatorio a la decisión del usuario y a la memoria (RI-13).

## Archivos a cargar

- `claude_licitaciones/02_SKILLS/02_BUDGET_BUILDER.md`
- `claude_licitaciones/03_WORKFLOWS/WF_05_VIABILIDAD_ECONOMICA.md` y `WF_06_PRESUPUESTO.md`
- `claude_licitaciones/04_KNOWLEDGE/09_PRESUPUESTACION_Y_RENTABILIDAD.md`
- `claude_licitaciones/06_TEMPLATES/TPL_BASE_ECONOMICA.md`
- `claude_licitaciones/07_CHECKLISTS/CHK_COSTES.md`
- Tarifas y datos de `empresa/DATOS_EMPRESA.md` si existe.

## Procedimiento

1. Parte del análisis (`01_analisis/analisis.md`); si las obligaciones del PPT no están descompuestas, hazlo primero (RI-13).
2. Convierte obligaciones en unidades costeables (tarea × frecuencia × volumen); asigna perfiles y horas con supuestos declarados [ESTIMACIÓN].
3. Barre el **catálogo completo** de costes incluyendo los olvidados (coordinación, reuniones, revisión, seguimiento, cierre, desplazamientos, «a demanda»).
4. **Sin tarifas → variables abiertas `[PENDIENTE]`** y preguntas cerradas; nunca inventes tarifas (RI-02).
5. Tres escenarios, coste total, precio, márgenes, sensibilidades, punto de equilibrio y contraste con la fórmula de precio.
6. **Advertencia obligatoria** si el margen probable < 10-15 %.
7. Cierra con cuadro de decisión (avanzar / ajustar / desestimar) **sin recomendar** (RI-11).

## Salida

Guarda en `expedientes/<NOMBRE>/02_economico/base_economica.md` (uso interno). Actualiza el `README.md`. Recuerda al usuario que la decisión de avanzar y el precio final son suyos, y que esta información **no puede aparecer en la memoria** (RI-05).
