# WF_06 — Base económica

> **Propósito:** procedimiento del estado 9: construir la base económica con escenarios, márgenes, sensibilidades y advertencias, hasta el punto de decisión del usuario.
> **Cuándo cargarlo:** al presupuestar con el inventario de necesidades ya disponible.
> **Cuándo no cargarlo:** sin inventario de E7 (usar WF_05 primero); en fases no económicas.
> **Skills que lo utilizan:** BUDGET.
> **Palabras clave:** base económica, presupuesto, escenarios, margen.
> **Dependencias:** WF_MASTER (E9), K-09, TPL_BASE_ECONOMICA.
> **Prioridad:** alta. **Coste de contexto:** bajo.
> **Resumen:** construye la base económica completa: valoración del inventario con tarifas reales o variables abiertas, tres escenarios (mínimo, probable, conservador), coste total, precio ofertable, margen absoluto y porcentual, sensibilidades, punto de equilibrio, contraste con la fórmula de precio y la zona de baja anormal, y advertencias obligatorias (margen < 10-15 %, partidas abiertas). Termina en el único punto de decisión obligatoria del usuario: avanzar, ajustar o desestimar.

---

## 1. Objetivo y estado cubierto
Estado 9 (Base económica). Es la frontera hacia la fase de oferta: de aquí no se pasa sin decisión del usuario (RI-11, RI-20).

## 2. Entrada
Inventario de necesidades (E7); respuestas del cuestionario o hipótesis autorizadas (E8); PBL y fórmula de precio (E6).

## 3. Pasos

1. **Valorar el inventario:** tarifa × horas por partida; partidas sin tarifa quedan `[PENDIENTE]` visibles con su pregunta. Nada se inventa (RI-02).
2. **Construir los tres escenarios** (TPL_BASE_ECONOMICA):
   - **Mínimo:** interpretación estricta de obligaciones, volúmenes a la baja.
   - **Probable:** interpretación realista; es el escenario de referencia.
   - **Conservador:** interpretación exigente + contingencias activadas.
3. **Totales por escenario:** costes directos → indirectos/gastos generales → contingencia → coste total → beneficio objetivo → precio resultante.
4. **Contraste con el mercado del concurso:** precio vs. PBL (¿cabe?); fórmula de precio (¿cuántos puntos deja cada nivel de baja?); **zona de baja anormal** estimada si la fórmula lo permite.
5. **Márgenes:** absoluto y porcentual por escenario y por nivel de baja plausible.
6. **Sensibilidades:** ±10-15 % en horas, un viaje/taller adicional al mes, retraso de 2 meses, perfil a contratar más caro. **Punto de equilibrio:** baja máxima que mantiene margen aceptable.
7. **Advertencias obligatorias:** margen probable < 10-15 % (destacado); dependencia de hipótesis sensibles; riesgo de baja anormal.
8. **Cierre para decisión:** cuadro resumen + implicaciones + opciones (avanzar / ajustar alcance / desestimar) **sin recomendación de decisión** (RI-11). Registrar la decisión del usuario antes de habilitar E10.

## 4. Salida
TPL_BASE_ECONOMICA completa + cuadro de decisión.

## 5. Bloqueos
Sin inventario E7 (RI-13); tarifas críticas sin respuesta ni hipótesis autorizada (RI-20).

## 6. Criterio de finalización
Escenarios, márgenes, sensibilidades y advertencias entregados; decisión del usuario solicitada expresamente.

## 7. Errores habituales
Comparar margen contra PBL con IVA; beneficio calculado antes de gastos generales; escenario «probable» que en realidad es el optimista; ignorar la anualidad de la prórroga; ocultar la advertencia de margen por no incomodar (RI-08).

## 8. Conexiones
La decisión positiva abre WF_07; la base económica queda como referencia para RI-07 durante toda la redacción y para el Red Team.
