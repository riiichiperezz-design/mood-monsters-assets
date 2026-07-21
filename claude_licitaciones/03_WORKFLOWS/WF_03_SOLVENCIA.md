# WF_03 — Validación de solvencia y personal

> **Propósito:** procedimiento de los estados 4-5: contrastar la solvencia económica y técnica exigida y el personal requerido con la capacidad real (validada) de la empresa.
> **Cuándo cargarlo:** al validar solvencia, habilitación, clasificación o equipo exigido.
> **Cuándo no cargarlo:** en fases de redacción o presupuesto; con la validación ya hecha.
> **Skills que lo utilizan:** ANALYZER (+PROCUREMENT en dudas jurídicas).
> **Palabras clave:** solvencia, clasificación, habilitación, adscripción, personal exigido, equipo.
> **Dependencias:** WF_MASTER (E4-E5), K-07, K-08, TPL_MATRIZ_SOLVENCIA, TPL_MATRIZ_PERSONAL, CHK_SOLVENCIA, CHK_PERSONAL.
> **Prioridad:** alta. **Coste de contexto:** bajo.
> **Resumen:** procedimiento en dos matrices: (1) solvencia exigida ↔ medios de acreditación admitidos ↔ capacidad declarada por el usuario, con alternativas (clasificación, integración de medios externos); (2) personal exigido ↔ perfiles disponibles, con dedicaciones, compromisos de adscripción y penalidades por sustitución. Ningún requisito se marca «cumplido» sin validación expresa del usuario (RI-03, RI-04); los incumplimientos claros se escalan como bloqueo de decisión (RI-20).

---

## 1. Objetivo y estados cubiertos
Estados 4 (Solvencia) y 5 (Personal).

## 2. Entrada
Requisitos de solvencia, habilitación y personal extraídos en WF_02; información interna disponible.

## 3. Pasos — Estado 4 (solvencia)

1. Transcribir cada requisito literal con referencia: solvencia económica (volumen anual, seguros, ratios) y técnica (servicios similares con importes y anualidades, certificados de buena ejecución, títulos, medios, certificaciones de calidad/ambientales).
2. Identificar el **medio de acreditación** admitido para cada requisito y las **alternativas**: clasificación empresarial sustitutiva (grupo/subgrupo/categoría), integración de solvencia con medios externos, reglas para empresas de nueva creación si constan.
3. Interpretar términos críticos: «servicios similares» (¿mismo CPV?, ¿mismo importe?), periodo computable, forma de acreditar (certificados vs. declaración). Duda material → PROCUREMENT.
4. Construir TPL_MATRIZ_SOLVENCIA: requisito → referencia → medio → capacidad declarada → estado (**acreditable / [PENDIENTE] / en riesgo / no acreditable**).
5. Preguntas cerradas por cada [PENDIENTE] (importes de contratos previos, certificados disponibles, seguros vigentes).
6. Si algo es claramente no acreditable ni con alternativas → **escalar al usuario** (RI-20): implicaciones (UTE, medios externos, desistir) sin decidir (RI-11).

## 4. Pasos — Estado 5 (personal)

1. Transcribir exigencias: perfiles, titulación, años y tipo de experiencia, dedicación, adscripción como compromiso, exigencias de arraigo/idiomas si constan.
2. Distinguir **requisito de solvencia** (equipo mínimo) de **criterio valorable** (equipo adicional puntúa): tratamiento distinto.
3. Construir TPL_MATRIZ_PERSONAL: perfil exigido → referencia → requisitos → persona/estado (**disponible / [PENDIENTE] / a contratar / subcontratable**) → dedicación → observaciones.
4. Analizar el régimen de sustituciones y penalidades; señalar riesgo si el pliego exige perfiles escasos.
5. Verificar coherencia preliminar carga de trabajo ↔ dedicaciones (aviso para E7/E9).
6. Preguntas cerradas (CVs reales, titulaciones, disponibilidad temporal).

## 5. Salida
Dos matrices con estados y preguntas; riesgos de solvencia/personal incorporados al bloque interno.

## 6. Bloqueos
Requisito claramente inalcanzable → bloqueo de decisión (RI-20). Información interna ausente → continuar con [PENDIENTE], nunca asumir cumplimiento.

## 7. Criterio de finalización
Cada requisito y perfil con estado asignado; escalamientos comunicados.

## 8. Errores habituales
Marcar «cumplido» por optimismo; ignorar que la adscripción de medios es compromiso contractual con penalidad; no ver la alternativa de clasificación; olvidar que la experiencia del equipo puede exigir certificados nominales.

## 9. Conexiones
Alimenta el bloque interno (decisión), BUDGET (coste de perfiles a contratar) y MEMORY (apartado de equipo, solo con datos validados).
