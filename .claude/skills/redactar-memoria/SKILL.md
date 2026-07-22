---
name: redactar-memoria
description: Prepara el índice y redacta la memoria técnica (oferta técnica) de un expediente, trazada contra los criterios de adjudicación. Úsala cuando el usuario pida "prepara el índice", "redacta la memoria", "desarrolla el apartado de X", "escribe la oferta técnica". Requiere análisis de criterios previo; solo se ejecuta tras la decisión del usuario de avanzar.
---

# Redactar memoria técnica

Ejecuta los estados 11-12. **Precondiciones (RI-12/13/20):** deben existir `01_analisis/criterios.md` y `02_economico/base_economica.md`, y el usuario debe haber decidido avanzar. Si falta la estrategia de criterios, ejecútala antes (`/estrategia-puntuacion`).

## Archivos a cargar

- `claude_licitaciones/02_SKILLS/03_MEMORY_WRITER.md`
- `claude_licitaciones/03_WORKFLOWS/WF_07_MEMORIA_TECNICA.md`
- `claude_licitaciones/04_KNOWLEDGE/02_ARQUITECTURA_MEMORIA_TECNICA.md` y `03_INGENIERIA_DE_EVIDENCIAS.md`
- `claude_licitaciones/06_TEMPLATES/TPL_MEMORIA_TECNICA.md`
- `claude_licitaciones/07_CHECKLISTS/CHK_MEMORIA.md` y `CHK_SOBRES.md`
- **Un solo** playbook sectorial según la tipología identificada (`05_PLAYBOOKS_TURISMO/PB_0X…`).
- Skills de apartado según toque, cargándolas solo cuando redactes ese apartado: `07_GOVERNANCE_DESIGNER`, `08_PLANNING_ENGINE`, `09_RISK_MANAGER`, `10_DELIVERABLES_GENERATOR`, `11_KPI_GENERATOR`, `06_VISUAL_DESIGNER`, `14_EDITORIAL_WRITER`.

## Procedimiento

1. **Índice primero (estado 11):** propón la tabla índice↔criterios↔páginas↔insumos e identifica la información interna pendiente. Respeta los límites formales del pliego (páginas, tipografía, estructura, anonimato). **Pide aprobación del índice** antes de redactar (RI-20).
2. **Redacta por lotes** de 2-4 apartados con la ficha estándar (objetivo, propuesta concreta, método, entregables, indicadores, coordinación, riesgos, trazabilidad con el pliego).
3. **Controles permanentes por lote:** CHK_SOBRES (nada de precio ni mejoras automáticas, RI-05/06), compromisos contra la base económica (RI-07), nada sin validar (usa `[PENDIENTE]`), contador de páginas vivo.
4. Nada de contenido genérico (RI-16); específico del contrato y del destino.

## Salida

Guarda en `expedientes/<NOMBRE>/03_memoria/memoria.md` (y `indice.md` para el índice aprobado). Actualiza el `README.md`. Al terminar, sugiere `/red-team`. Si el usuario tiene la skill `agora-licitaciones` disponible, ofrece exportar a .docx con ella.
