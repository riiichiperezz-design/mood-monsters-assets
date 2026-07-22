---
name: validar-solvencia
description: Valida la solvencia económica y técnica exigida y el personal requerido de un expediente contra la capacidad real de la empresa. Úsala cuando el usuario pregunte "¿cumplimos la solvencia?", "¿podemos acreditar esto?", "qué equipo exige", "¿tenemos los perfiles?" o tras el análisis del expediente.
---

# Validar solvencia y personal

Ejecuta los estados 4-5 del workflow.

## Archivos a cargar

- `claude_licitaciones/03_WORKFLOWS/WF_03_SOLVENCIA.md`
- `claude_licitaciones/04_KNOWLEDGE/07_SOLVENCIA_Y_ACREDITACION.md` y `08_PERSONAL_Y_EQUIPO.md`
- `claude_licitaciones/06_TEMPLATES/TPL_MATRIZ_SOLVENCIA.md` y `TPL_MATRIZ_PERSONAL.md`
- `claude_licitaciones/07_CHECKLISTS/CHK_SOLVENCIA.md` y `CHK_PERSONAL.md`
- Si hay dudas jurídicas: `claude_licitaciones/02_SKILLS/13_SPANISH_PROCUREMENT_EXPERT.md` + `04_KNOWLEDGE/18_CONTRATACION_PUBLICA_ESPAÑOLA.md`
- Datos de la empresa: `empresa/DATOS_EMPRESA.md` si existe.

## Procedimiento

1. Parte del análisis ya guardado en `01_analisis/analisis.md` (no reanalices los pliegos si el análisis existe).
2. **Matriz de solvencia** (TPL_MATRIZ_SOLVENCIA): requisito literal → medio de acreditación → alternativas (clasificación, medios externos, UTE) → capacidad declarada → estado (acreditable / [PENDIENTE] / en riesgo / no acreditable). Distingue el régimen de cada exigencia.
3. **Matriz de personal** (TPL_MATRIZ_PERSONAL): distingue solvencia / adscripción / criterio valorable; estado por perfil; dedicaciones × tarifas como suelo de coste (para la base económica).
4. **Nada se marca "acreditable" sin validación** del usuario o de `DATOS_EMPRESA.md` (RI-03/04). Requisitos claramente inalcanzables → escálalos con alternativas, sin decidir (RI-20/11).
5. Consolida **preguntas cerradas** para lo que falte.

## Salida

Guarda en `expedientes/<NOMBRE>/01_analisis/solvencia.md`. Actualiza el `README.md`. Si detectas un incumplimiento de solvencia que podría impedir concurrir, dilo con claridad como elemento de decisión del usuario.
