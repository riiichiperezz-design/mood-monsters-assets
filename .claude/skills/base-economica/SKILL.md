---
name: base-economica
description: Prepara el presupuesto / oferta económica de un expediente rellenando la plantilla Excel de la empresa (empresa/plantillas/PLANTILLA_oferta_economica.xlsx) con los costes de esa licitación. Úsala cuando el usuario pregunte "hazme el presupuesto", "prepara la oferta económica", "¿es rentable?", "¿cuánto cuesta ejecutarlo?", "¿a qué precio ofertamos?" o para valorar mejoras. Uso interno: NUNCA se traslada a la memoria.
---

# Base económica (presupuesto sobre la plantilla de la empresa)

Ejecuta los estados 7-9 del workflow. Es el paso previo obligatorio a la decisión del usuario y a la memoria (RI-13). **El presupuesto se prepara SIEMPRE rellenando la plantilla Excel de la empresa**, cambiando los datos de coste de cada licitación.

## Plantilla y su lógica (respetar sin alterar fórmulas)

Plantilla maestra: `empresa/plantillas/PLANTILLA_oferta_economica.xlsx` (ejemplo real resuelto: `EJEMPLO_Oferta_Laciana.xlsx`). Una hoja con tres bloques:

- **Gastos directos** (A5:E12): `Concepto | unidad (B) | coste unidad (C) | Importe (D=B*C) | Detalles`. Total `D14=SUM(D5:D12)`.
- **Gastos en horas** (I5:L18): `Concepto | Horas (J) | Importe (K=$K$2) | Importe total (L=J*K)`. Total `L21=SUM(L5:L18)`. Coste/hora en `K2`, meses en `M2`.
- **Resumen/precio** (F/G): `G4` Presupuesto (base SIN IVA del pliego) · `G5=D14+L21` Coste · `G6` Bajada % · `G8=G4*(1-G6)` Oferta · `G10=G8-G5` Beneficio · `G11=G10/G8` Margen · `G12=G10/G5` Margen s/coste · `G13=G8*0.21` IVA · `G14=G8+G13` Total.

**Celdas que se editan por licitación (entradas):** las columnas A/B/C/E de directos, I/J de horas, y las palancas `K2` (coste hora), `M2` (meses), `G4` (Presupuesto sin IVA del pliego) y `G6` (bajada %). **No toques las fórmulas** (D, L, G5, G8, G10-G14, totales).

## Archivos a cargar

- `claude_licitaciones/02_SKILLS/02_BUDGET_BUILDER.md` y `04_KNOWLEDGE/09_PRESUPUESTACION_Y_RENTABILIDAD.md`
- `claude_licitaciones/07_CHECKLISTS/CHK_COSTES.md`
- Tarifas/datos de `empresa/DATOS_EMPRESA.md` si existe.

## Procedimiento

1. Parte del análisis (`01_analisis/analisis.md`); si las obligaciones del PPT no están descompuestas, hazlo primero (RI-13).
2. **Copia la plantilla** a `expedientes/<NOMBRE>/02_economico/oferta_economica.xlsx`.
3. **Convierte las obligaciones del pliego en las filas de la plantilla:**
   - Gastos en horas: mapea las tareas del PPT a los conceptos (I5:I18) y estima las horas (J), con supuestos declarados [ESTIMACIÓN]. Ajusta `K2` (coste/hora) desde `DATOS_EMPRESA.md`.
   - Gastos directos: desplazamientos, dietas, materiales, licencias, subcontratación, imprevistos… (A/B/C). Barre el catálogo de `CHK_COSTES.md` para no olvidar partidas (reuniones, viajes, «a demanda», cierre).
   - `G4` = base de licitación **sin IVA** (ojo: en el pliego el PBL suele venir con IVA; usa la base imponible o el valor estimado anual según corresponda). `M2` = meses del contrato. `G6` = bajada propuesta (empieza en 0 y deja que el usuario decida).
4. Edita el xlsx con openpyxl escribiendo SOLO en las celdas de entrada; después ejecuta `python3 /root/.claude/skills/xlsx/scripts/recalc.py <ruta> 180` para recalcular y verificar que no hay errores. Si falta un dato de coste, déjalo a 0 y anótalo como `[PENDIENTE]` en el resumen (nunca inventes tarifas, RI-02).
5. Lee los valores recalculados (Coste G5, Oferta G8, Margen G11) y redacta un breve `base_economica.md` con: supuestos declarados, partidas [PENDIENTE], sensibilidad (qué pasa si suben horas o baja el precio) y **advertencia obligatoria si el Margen < 10-15 %**.
6. Cierra con cuadro de decisión (avanzar / ajustar / desestimar) **sin recomendar** (RI-11).

## Salida

- `expedientes/<NOMBRE>/02_economico/oferta_economica.xlsx` (la plantilla rellena — entregable principal).
- `expedientes/<NOMBRE>/02_economico/base_economica.md` (supuestos, sensibilidad, advertencias).
Actualiza el `README.md`. Recuerda: la decisión de avanzar y el precio final son del usuario, y esta información económica **no puede aparecer en la memoria** (RI-05).
