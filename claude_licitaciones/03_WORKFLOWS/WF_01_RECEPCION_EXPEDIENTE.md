# WF_01 — Recepción del expediente e inventario documental

> **Propósito:** procedimiento operativo de los estados 0-1: recibir el expediente, clasificar cada documento y detectar faltantes antes de cualquier análisis.
> **Cuándo cargarlo:** al recibir archivos de un expediente nuevo.
> **Cuándo no cargarlo:** con el inventario ya hecho en la conversación.
> **Skills que lo utilizan:** ROUTER, ANALYZER.
> **Palabras clave:** recepción, inventario, documentos subidos, expediente nuevo.
> **Dependencias:** WF_MASTER (E0-E1), CHK_DOCUMENTOS.
> **Prioridad:** alta. **Coste de contexto:** bajo.
> **Resumen:** guía de arranque de todo expediente. Establece cómo confirmar la recepción, cómo clasificar los documentos por su naturaleza real (no por su nombre de archivo), qué documentos típicos deben existir según el procedimiento, cómo listar faltantes con su impacto y cómo dejar el expediente listo para la extracción rápida sin haber consumido contexto en contenido aún innecesario.

---

## 1. Objetivo y estados cubiertos
Estados 0 (Recepción) y 1 (Inventario documental) de WF_MASTER. Meta: expediente identificado, documentos clasificados, faltantes detectados.

## 2. Entrada
Archivos subidos (PDF, Word, Excel, PowerPoint, texto) o referencias a la Plataforma de Contratación; petición del usuario.

## 3. Pasos

1. **Confirmar recepción e identificar el expediente:** objeto aparente, órgano de contratación, número de expediente si consta. Una línea, sin análisis todavía.
2. **Verificar legibilidad:** documentos escaneados sin OCR, protegidos o truncados se señalan de inmediato (riesgo de análisis incompleto).
3. **Clasificar por naturaleza real, no por nombre de archivo.** Tipología de referencia:
   - **PCAP** (cláusulas administrativas: solvencia, criterios, sobres, plazos de presentación) — a menudo con **cuadro de características/anexo I** que concentra los datos clave.
   - **PPT** (prescripciones técnicas: tareas, entregables, equipo, plazos de ejecución).
   - **Memoria justificativa** (motivación de la necesidad; útil para entender la intención, no vinculante frente a los pliegos).
   - **CRC / informe de insuficiencia de medios**, **anexos** (criterios, modelos de proposición, DEUC), **formularios**, **aclaraciones publicadas**, **acta/composición de mesa** si consta.
4. **Detectar duplicados y versiones:** si hay dos versiones de un pliego, identificar la vigente (rectificaciones) y advertirlo.
5. **Contrastar contra CHK_DOCUMENTOS:** listar faltantes típicos con su impacto (p. ej. «falta el anexo de criterios: la extracción rápida de puntos quedará incompleta»).
6. **Cerrar el inventario** en tabla: documento → tipo → estado (legible/parcial) → observaciones.

## 4. Salida
Tabla de inventario + lista de faltantes con impacto + confirmación de paso a extracción rápida.

## 5. Bloqueos
- Ningún documento legible → parar y pedir versiones nativas.
- Solo documentación parcial → continuar con advertencia expresa de alcance.

## 6. Criterio de finalización
Todo archivo clasificado; faltantes comunicados; usuario sabe con qué se va a trabajar.

## 7. Errores habituales
Fiarse del nombre del archivo («PPT.pdf» que es el PCAP); ignorar rectificaciones publicadas; empezar a analizar contenido antes de cerrar el inventario; no avisar de páginas escaneadas ilegibles.

## 8. Conexiones
Sigue en WF_02 (extracción rápida y análisis). El inventario alimenta CHK_DOCUMENTOS y la sección «documentos del expediente» del análisis completo.
