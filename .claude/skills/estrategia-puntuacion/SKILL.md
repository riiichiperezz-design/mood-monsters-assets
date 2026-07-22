---
name: estrategia-puntuacion
description: Construye la estrategia de puntuación de un expediente — matriz de criterios de adjudicación, análisis de la fórmula de precio, separación de sobres y tratamiento de mejoras. Úsala cuando el usuario pregunte "dónde se gana este concurso", "cómo se puntúa", "qué hacemos con las mejoras", "estrategia de puntos" o antes de preparar el índice de la memoria.
---

# Estrategia de puntuación

Ejecuta los estados 6 y 10 del workflow. Es el puente obligatorio entre el análisis y la memoria (RI-12).

## Archivos a cargar

- `claude_licitaciones/02_SKILLS/04_SCORING_OPTIMIZER.md`
- `claude_licitaciones/03_WORKFLOWS/WF_04_CRITERIOS_ADJUDICACION.md`
- `claude_licitaciones/04_KNOWLEDGE/05_OPTIMIZACION_JUICIO_VALOR.md` y `06_CRITERIOS_AUTOMATICOS_Y_MEJORAS.md`
- `claude_licitaciones/06_TEMPLATES/TPL_MATRIZ_CRITERIOS.md`
- `claude_licitaciones/07_CHECKLISTS/CHK_SOBRES.md`

## Procedimiento

1. Parte de los criterios ya extraídos en `01_analisis/analisis.md`.
2. Verifica que los puntos **suman el total del pliego**; si no, busca el anexo que falta.
3. Clasifica cada criterio (fórmula/juicio, sobre, umbral mínimo eliminatorio).
4. **Analiza la fórmula de precio**: valor real del punto por tramo de baja y zona de baja anormal.
5. Infiere la **evidencia esperada** por criterio de juicio (K-05) y construye la matriz de 7 columnas priorizada.
6. **Taxonomía de mejoras** con coste/punto (coordínalo con `/base-economica` si ya existe) y **mapa de sobres** (CHK_SOBRES): qué no puede aparecer en la memoria (RI-05/06).

## Salida

Guarda en `expedientes/<NOMBRE>/01_analisis/criterios.md`. Actualiza el `README.md`. Esta matriz es requisito para `/redactar-memoria`.
