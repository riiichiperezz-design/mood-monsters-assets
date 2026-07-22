# Plantillas económicas

- **`PLANTILLA_oferta_economica.xlsx`** — plantilla maestra reutilizable. `/base-economica` la copia a `expedientes/<NOMBRE>/02_economico/oferta_economica.xlsx` y cambia solo los datos de coste de cada licitación.
- **`EJEMPLO_Oferta_Laciana.xlsx`** — ejemplo real resuelto (Fundación Laciana, Expte. 740/2026), como referencia de formato.

## Estructura de la plantilla (una hoja, tres bloques)

| Bloque | Celdas | Qué contiene |
|---|---|---|
| Gastos directos | `A5:E12` | Concepto · unidad (B) · coste unidad (C) · Importe (`D=B*C`) · Detalles. Total `D14`. |
| Gastos en horas | `I5:L18` | Concepto · Horas (J) · Importe (`K=$K$2`) · Importe total (`L=J*K`). Total `L21`. |
| Resumen / precio | `F/G` | Presupuesto `G4` · Coste `G5=D14+L21` · Bajada `G6` · Oferta `G8=G4*(1-G6)` · Beneficio `G10` · Margen `G11=G10/G8` · IVA `G13` · Total `G14`. |

## Qué se edita por licitación (marcado en azul/amarillo)

- **Azul:** conceptos, unidades, costes y horas de las dos tablas.
- **Amarillo (palancas):** `K2` coste/hora · `M2` meses · `G4` Presupuesto **base sin IVA** del pliego · `G6` bajada %.
- **No tocar:** las fórmulas (columnas D y L, totales y todo el bloque G5:G14).

## Notas

- `G4` es la base **sin IVA**. En los pliegos el PBL suele venir con IVA incluido y desglose: usa la base imponible (o el valor estimado anual según el caso). El IVA (21 %) lo añade la propia plantilla en `G13`.
- El coste/hora `K2` es una tarifa única mezclada para todas las tareas. Si algún día quieres tarifas por perfil, se puede añadir una columna; de momento se respeta tu modelo actual.
- Si el margen (`G11`) baja del 10-15 %, revísalo antes de ofertar.
- El libro está marcado para **recalcular al abrirse**: al abrir en Excel/LibreOffice verás los totales calculados.
- Contenido económico: **uso interno**, nunca se incluye en la memoria técnica (separación de sobres).
