# K-06 — Criterios automáticos y mejoras

> **Propósito:** doctrina sobre criterios evaluables mediante fórmula (precio y otros) y sobre el tratamiento de mejoras, con la separación de sobres como eje.
> **Cuándo cargarlo:** análisis de criterios (estado 6), estrategia de mejoras (WF_08) y decisiones de precio.
> **Cuándo no cargarlo:** en redacción de memoria (salvo verificación de sobres) o fases documentales.
> **Skills que lo utilizan:** 04_SCORING_OPTIMIZER, 02_BUDGET_BUILDER.
> **Palabras clave:** fórmula de precio, mejoras, criterios automáticos, sobres, baja.
> **Dependencias:** K-09 (economía), CHK_SOBRES, REGLAS_INVIOLABLES (RI-05, RI-06, RI-07).
> **Prioridad:** media. **Coste de contexto:** medio.
> **Resumen:** análisis operativo de los criterios de fórmula: tipos de fórmulas de precio y su comportamiento real (valor del punto por tramo de baja), parámetros de oferta anormalmente baja y sus consecuencias, criterios automáticos no-precio como compromisos contractuales con coste, régimen de las mejoras (definición, límites, sobre y valoración) y la disciplina de separación de sobres cuya vulneración causa exclusión. Incluye el método coste-por-punto para decidir racionalmente entre bajar precio y ofertar mejoras.

---

## 1. Fórmulas de precio: leerlas con calculadora

Tipos frecuentes y comportamiento:

- **Proporcional inversa** (P = Pmax × mejor oferta / oferta): recorrido corto; grandes bajas mueven pocos puntos.
- **Proporcional a la baja** (P = Pmax × baja propia / baja máxima): recorrido total; el más agresivo se lleva todo y arrastra la referencia. Alta presión al precio.
- **Lineal sobre presupuesto** (puntos por cada % de baja hasta un tope): valor del punto constante y predecible.
- **Con umbral de saciedad o media:** bajas por encima de X no puntúan más, o se puntúa contra la media (comportamiento estratégico, resultado incierto).

Análisis obligatorio (estado 6): puntos que otorga cada nivel de baja plausible (0 %, 5 %, 10 %, 15 %), y cuántos puntos de memoria compensan cada 5 % de baja. Esa equivalencia es la base de la decisión económica del usuario.

## 2. Ofertas anormalmente bajas

- Parámetros típicos: baja superior en X puntos a la media de las ofertas, o umbral fijo. Identificarlos siempre en el PCAP/anexos.
- Consecuencia: no exclusión automática sino **trámite de justificación** (costes desglosados, condiciones ventajosas). Es defendible con una base económica sólida (WF_06) — otra razón para no inventar números.
- Estrategia: conocer la zona de riesgo antes de fijar precio; si se entra a sabiendas, preparar la justificación desde el primer día.

## 3. Criterios automáticos no-precio

Ampliación de garantía, reducción de plazo, bolsa de horas, personal adicional, certificaciones: puntúan por declaración pero **obligan contractualmente** y tienen coste (BUDGET los valora siempre) y penalidad por incumplimiento. Regla: solo se ofertan los que la base económica absorbe (RI-07/08).

## 4. Mejoras: régimen y disciplina

- Solo cabe valorar mejoras **definidas por el pliego** con requisitos, límites y forma de valoración; las «mejoras libres» son terreno resbaladizo: prudencia y PROCUREMENT si hay dudas.
- Determinar SIEMPRE: en qué sobre se presentan, con qué modelo, y si su contenido puede o no mencionarse en la memoria. **Por defecto: mejora valorable automáticamente = fuera de la memoria** (RI-06).
- La mejora aceptada es exigible: se ejecuta, se penaliza si no. Nada es «gratis» (RI-07).

## 5. Método coste-por-punto

Para cada palanca (baja de precio, mejora A, mejora B, compromiso C): coste total de la palanca / puntos que otorga = **€/punto**. Ordenar de menor a mayor y componer la combinación óptima dentro del margen aceptado por el usuario. Refinamientos: riesgo de ejecución de cada palanca (una mejora compleja tiene coste de riesgo), y saturación (puntos con tope).

## 6. Separación de sobres (desarrolla RI-05)

- Nada evaluable por fórmula puede constar —ni deducirse— del sobre de juicio de valor: ni precio, ni % de baja, ni la existencia o alcance de mejoras automáticas, ni plazos ofertados por fórmula.
- Vulneraciones sutiles a vigilar: cronogramas que revelan el plazo reducido ofertado; organigramas con el personal adicional de la mejora; presupuestos «orientativos» en la memoria; visuales con cifras del sobre económico.
- Verificación: CHK_SOBRES en redacción (WF_07), en mejoras (WF_08) y en Red Team (pasada 2).

## 7. Documentación de la oferta automática

Usar los modelos oficiales sin alterarlos; ofertar exactamente en las unidades que pide la fórmula (¡% vs. importe!); revisar coherencia aritmética (IVA, decimales, letras vs. cifras: prevalece lo que diga el pliego); una incoherencia aquí puede excluir.
