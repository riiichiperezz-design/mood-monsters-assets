# WF_08 — Mejoras y criterios automáticos

> **Propósito:** procedimiento transversal para el tratamiento de mejoras y del contenido de sobres automáticos sin contaminar la memoria.
> **Cuándo cargarlo:** al decidir, cuantificar o documentar mejoras y ofertas de criterios automáticos.
> **Cuándo no cargarlo:** cuando el pliego no contempla mejoras ni criterios automáticos distintos del precio.
> **Skills que lo utilizan:** SCORING (clasificación y valor), BUDGET (coste).
> **Palabras clave:** mejoras, criterios automáticos, sobre económico, oferta.
> **Dependencias:** WF_MASTER (transversal a E6-E12), K-06, CHK_SOBRES.
> **Prioridad:** alta. **Coste de contexto:** bajo.
> **Resumen:** aísla el circuito de las mejoras: leer su definición literal, clasificarlas con la taxonomía de SCORING, cuantificar coste y valor en puntos de cada una, someterlas a decisión del usuario, documentarlas en el sobre correcto con el modelo oficial y verificar que ni la memoria ni sus visuales las anticipan. Cubre también el resto de criterios automáticos (plazos, garantías ampliadas, bolsas de horas) y su coste oculto.

---

## 1. Objetivo
Maximizar puntos automáticos con coste controlado y **riesgo cero de mezcla de sobres** (RI-05, RI-06).

## 2. Entrada
Definición literal de mejoras y criterios automáticos (E6); base económica (E9).

## 3. Pasos

1. **Leer la letra pequeña de cada mejora:** qué se admite exactamente, límites (número, alcance), cómo se valora (fórmula, escalón, sí/no), en qué sobre se presenta y con qué modelo.
2. **Clasificar** (taxonomía SCORING §11): automática / legítima de calidad técnica / compromiso adicional; detectar mejoras-trampa (coste alto, puntos marginales).
3. **Cuantificar cada mejora:** coste completo (BUDGET: producción + gestión + riesgo) ↔ puntos que otorga ↔ coste por punto. Comparar con el coste por punto de bajar precio: es la referencia racional.
4. **Criterios automáticos no-precio** (ampliación de garantía, reducción de plazo, bolsa de horas, personal adicional): tratar como compromisos contractuales con coste; valorar penalidades por incumplimiento.
5. **Decisión del usuario** mejora a mejora (RI-11): ofertar / no ofertar / ofertar parcial.
6. **Documentar en el sobre correcto:** usar el modelo/formulario oficial si existe; redactar la mejora de forma autocontenida (el evaluador de ese sobre no ve la memoria).
7. **Verificación cruzada CHK_SOBRES:** la memoria y sus visuales no mencionan, cuantifican ni permiten deducir las mejoras automáticas ni el precio; las mejoras no revelan contenido evaluable del otro sobre si el pliego lo prohíbe.

## 4. Salida
Cuadro de mejoras (mejora → clasificación → coste → puntos → coste/punto → decisión → sobre) + documentos de mejora listos + verificación de separación.

## 5. Bloqueos
Mejora con coste relevante sin decisión del usuario (RI-20); definición ambigua de mejora → consulta al órgano si el plazo lo permite (PROCUREMENT).

## 6. Criterio de finalización
Todas las mejoras decididas, costeadas, documentadas en su sobre y verificadas contra la memoria.

## 7. Errores habituales
Ofertar todas las mejoras «porque puntúan» sin costearlas (RI-07/08); describir la mejora en la memoria «para reforzar» (exclusión, RI-05); ignorar que la mejora aceptada es obligación contractual; olvidar el modelo oficial de proposición.

## 8. Conexiones
Corre en paralelo a WF_07; sus decisiones actualizan la base económica (WF_06) y el Red Team la verifica (WF_09).
