# WF_04 — Análisis de criterios de adjudicación

> **Propósito:** procedimiento del estado 6: descomponer el baremo, analizar la fórmula de precio y construir la matriz de criterios con evidencias y prioridades.
> **Cuándo cargarlo:** al analizar criterios, umbrales, fórmulas o estrategia de puntos.
> **Cuándo no cargarlo:** antes de extraer los criterios; en redacción o revisión.
> **Skills que lo utilizan:** SCORING.
> **Palabras clave:** criterios, baremo, umbral, fórmula, puntos.
> **Dependencias:** WF_MASTER (E6), K-05, K-06, TPL_MATRIZ_CRITERIOS, CHK_SOBRES.
> **Prioridad:** alta. **Coste de contexto:** bajo.
> **Resumen:** procedimiento para convertir el baremo en estrategia: clasificación de cada criterio (fórmula/juicio, sobre, umbral), análisis cuantitativo de la fórmula de precio (valor del punto por porcentaje de baja, zona de baja anormal), inferencia de la evidencia que espera el evaluador en cada criterio de juicio, y construcción de la matriz de 7 columnas con prioridades por puntos en juego. Incluye la verificación temprana de separación de sobres.

---

## 1. Objetivo y estado cubierto
Estado 6 (Análisis de criterios).

## 2. Entrada
Criterios completos extraídos (WF_02): puntos, subcriterios, fórmulas, umbrales, definición de mejoras, estructura de sobres.

## 3. Pasos

1. **Verificar la suma:** los puntos listados deben cuadrar con el total del pliego; si no cuadran, buscar el anexo que falta.
2. **Clasificar cada criterio:** tipo (fórmula automática / juicio de valor), sobre al que pertenece, umbral mínimo si existe (¡los umbrales convierten criterios en eliminatorios de facto!).
3. **Analizar la fórmula de precio:** comportamiento (lineal, proporcional, con corte), puntos por cada 1 % / 5 % de baja, baja de referencia, parámetros de oferta anormalmente baja (individual o respecto de la media). Conclusión operativa: cuánto pesa realmente el precio.
4. **Analizar mejoras:** definición exacta del pliego, límites, forma de valoración (automática/juicio), sobre. Aplicar la taxonomía de SCORING §11.
5. **Inferir evidencia esperada** por criterio de juicio (K-05): qué querrá ver el evaluador para dar la puntuación alta (concreción, método nombrado, medios, indicadores, ejemplos).
6. **Construir TPL_MATRIZ_CRITERIOS** (criterio → puntos → evidencia esperada → cobertura actual → debilidad → acción → prioridad), con cobertura [PENDIENTE] donde falte validación.
7. **Mapa de sobres** y verificación temprana CHK_SOBRES: qué contenido irá en cada sobre y qué no puede aparecer en la memoria (RI-05).
8. **Síntesis estratégica:** dónde se gana y se pierde el concurso (reparto puntos fórmula/juicio, umbrales, sensibilidad al precio).

## 4. Salida
Matriz de criterios completa + análisis de fórmula + mapa de sobres + síntesis estratégica.

## 5. Bloqueos
Anexo de criterios ausente → solicitar antes de continuar; criterios que no cuadran → advertir y trabajar con lo disponible marcado.

## 6. Criterio de finalización
Suma verificada, todos los criterios clasificados, matriz priorizada entregada.

## 7. Errores habituales
Ignorar umbrales mínimos; leer solo los títulos de los criterios y no su desglose; no calcular el valor real del punto de precio; tratar las mejoras sin leer su definición exacta; olvidar criterios de desempate.

## 8. Conexiones
Alimenta E9 (la fórmula condiciona el precio), E10-E11 (estrategia e índice) y CHK_SOBRES durante toda la redacción.
