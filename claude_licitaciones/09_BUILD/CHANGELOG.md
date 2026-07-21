# CHANGELOG — Sistema experto de licitaciones turísticas

> **Propósito:** historial de cambios del sistema. **Cuándo cargarlo:** solo en mantenimiento.
> **Prioridad:** baja. **Coste:** bajo.
> **Resumen:** registro de versiones; toda modificación relevante de módulos se anota aquí y se sincroniza con MANIFEST.json y FILE_INDEX.md.

---

## [1.0.0] — 2026-07-21

### Añadido
- Versión inicial completa del sistema (97 módulos):
  - `00_README/` (4): mapa del sistema, instalación, guía de uso, README general.
  - `01_PROJECT_INSTRUCTIONS/` (4): instrucciones recomendadas, corta, completa y las 20 reglas inviolables.
  - `02_SKILLS/` (15): Router + 14 Skills especializadas con estructura de 28 puntos.
  - `03_WORKFLOWS/` (11): WF_MASTER (estados 0-17) y WF_01–WF_10.
  - `04_KNOWLEDGE/` (18): metodologías K-01 a K-18.
  - `05_PLAYBOOKS_TURISMO/` (11): PB_01–PB_10 + tabla de enrutado PB_11.
  - `06_TEMPLATES/` (16) y `07_CHECKLISTS/` (8).
  - `08_OUTPUT_EXAMPLES/` (5): caso ficticio coherente (oficina técnica PSTD).
  - `09_BUILD/` (5): MANIFEST.json, FILE_INDEX.md, CONTEXT_LOADING_GUIDE.md, CHANGELOG.md, VALIDATION_REPORT.md.

### Notas de esta versión
- Construida sin documentos de referencia de la empresa (el repositorio no los contenía): las referencias previstas (MODELO DE MEMORIA GANADORA – ÁGORA, Memoria Gran Tour Cáceres, Project Management ENEB, materiales internos) quedan pendientes de abstracción para la v1.1/v2 (ver VALIDATION_REPORT §Limitaciones).
- MANIFEST.json se genera de forma reproducible; mantenerlo sincronizado con FILE_INDEX.md en cada cambio.

## Cómo registrar cambios

Formato: `## [x.y.z] — fecha` con secciones **Añadido / Cambiado / Corregido / Eliminado**; cada entrada nombra el archivo y el motivo. Cambios de reglas inviolables o de flujos obligatorios incrementan la versión menor como mínimo.
