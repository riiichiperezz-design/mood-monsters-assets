---
name: analizar-expediente
description: Analiza un expediente de contratación pública (pliegos PCAP, PPT, anexos) y produce la extracción rápida obligatoria más el análisis completo. Úsala cuando el usuario suba o señale los PDF de un pliego, diga "analiza este expediente/pliego", "qué pide este concurso", "resume la licitación" o similar. Es SIEMPRE el primer paso del ciclo, antes de solvencia, economía o memoria.
---

# Analizar expediente

Ejecuta los estados 1-3 del workflow: inventario documental, extracción rápida y análisis completo.

## Archivos a cargar (carga selectiva)

- Skill de dominio: `claude_licitaciones/02_SKILLS/01_EXPEDIENT_ANALYZER.md`
- Método: `claude_licitaciones/04_KNOWLEDGE/01_METODOLOGIA_ANALISIS_EXPEDIENTES.md`
- Plantillas: `claude_licitaciones/06_TEMPLATES/TPL_EXTRACCION_RAPIDA.md`, `TPL_RESUMEN_EXPEDIENTE.md`, `TPL_CONCLUSION_INTERNA.md`
- Checklist: `claude_licitaciones/07_CHECKLISTS/CHK_DOCUMENTOS.md`
- **No** cargues: playbooks (salvo para identificar tipología con `PB_11`), red team, memoria, presupuesto, legislación (salvo duda jurídica concreta).

## Procedimiento

1. **Localiza el expediente:** los PDF están en `expedientes/<NOMBRE>/00_pliegos/`. Si hay varios expedientes, pregunta cuál. Lee los PDF con la herramienta de lectura.
2. **Inventario documental** (CHK_DOCUMENTOS): clasifica cada archivo por su naturaleza real (PCAP, PPT, memoria justificativa, anexos, modelos), detecta faltantes típicos y priméralos por densidad (cuadro de características y anexo de criterios primero).
3. **Extracción rápida** (TPL_EXTRACCION_RAPIDA): entrega SIEMPRE primero los 6 puntos en orden — plazos, puntos por precio, puntos por mejora, puntos por memoria, solvencia económica, solvencia técnica — con cita y referencia.
4. **Análisis completo** (TPL_RESUMEN_EXPEDIENTE): 13 secciones con referencias y etiquetas [EXPEDIENTE]/[INTERPRETACIÓN]/etc.
5. **Cruce PCAP↔PPT** buscando contradicciones; señálalas con doble cita (RI-19).
6. **Identifica la tipología turística** con `claude_licitaciones/05_PLAYBOOKS_TURISMO/PB_11_PATRONES_POR_TIPO_DE_CONTRATO.md` y anótala (sin cargar aún el playbook completo).
7. **Bloque interno** (TPL_CONCLUSION_INTERNA) con conclusión operativa **sin decidir** si presentarse (RI-11) y **preguntas cerradas** consolidadas.

## Salida

Guarda todo en `expedientes/<NOMBRE>/01_analisis/analisis.md`. Actualiza el `README.md` del expediente: «Estado 3 completado. Siguiente: `/validar-solvencia` y `/estrategia-puntuacion`». Muestra al usuario la extracción rápida y un resumen del bloque interno en el chat.

No redactes memoria ni calcules oferta económica definitiva en esta skill.
