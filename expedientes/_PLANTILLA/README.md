# Expediente: [NOMBRE]

- **Objeto:** [rellenar tras el análisis]
- **Órgano de contratación:**
- **Nº de expediente:**
- **Fecha límite de presentación:**
- **Creado:** [fecha]
- **Estado actual:** Estado 0 — Recepción

## Bitácora de estados

| Estado | Skill | Fecha | Salida | Notas |
|---|---|---|---|---|
| 0 Recepción | `/nuevo-expediente` | | esta carpeta | Pendiente: soltar PDF en `00_pliegos/` |
| 1-3 Análisis | `/analizar-expediente` | | `01_analisis/analisis.md` | |
| 4-5 Solvencia | `/validar-solvencia` | | `01_analisis/solvencia.md` | |
| 6 Criterios | `/estrategia-puntuacion` | | `01_analisis/criterios.md` | |
| 7-9 Economía | `/base-economica` | | `02_economico/base_economica.md` | |
| — Decisión | **usuario** | | | avanzar / ajustar / desestimar |
| 11-12 Memoria | `/redactar-memoria` | | `03_memoria/memoria.md` | |
| 13-14 Red Team | `/red-team` | | `04_revision/red_team.md` | |
| 15 Correcciones | `/redactar-memoria` | | `03_memoria/memoria.md` | |
| 16-17 Cierre | `/cierre-presentacion` | | `04_revision/checklist_final.md` | |

## Contenido de las carpetas

- `00_pliegos/` — PDF originales del expediente (PCAP, PPT, anexos, modelos). **Los pones tú.**
- `01_analisis/` — análisis, solvencia y criterios (los genera el sistema).
- `02_economico/` — base económica. **Uso interno; nunca va a la oferta.**
- `03_memoria/` — índice y memoria técnica.
- `04_revision/` — red team y checklist final.

## Siguiente paso

Soltar los PDF del pliego en `00_pliegos/` y ejecutar `/analizar-expediente`.
