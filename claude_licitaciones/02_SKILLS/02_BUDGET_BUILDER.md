# SKILL 02 — BUDGET_BUILDER

> **Propósito:** transformar las obligaciones del pliego en costes, escenarios económicos y análisis de margen.
> **Cuándo cargarlo:** peticiones de viabilidad, costes, presupuesto o margen (clases D y F del Router).
> **Cuándo no cargarlo:** análisis documental inicial, redacción de memoria, visuales, cuestiones jurídicas.
> **Skills que lo utilizan:** ROUTER; MEMORY consulta su salida para no prometer lo no presupuestado; SCORING para valorar coste de mejoras.
> **Palabras clave:** presupuesto, costes, viabilidad, margen, tarifas, rentabilidad, baja.
> **Dependencias:** salida de 01_ANALYZER (obligaciones), K-09, TPL_BASE_ECONOMICA, CHK_COSTES.
> **Prioridad:** alta. **Coste de contexto:** medio.
> **Resumen:** convierte el PPT en necesidades económicas completas (personal, horas, tarifas, dirección, coordinación, producción, revisión, viajes, alojamiento, dietas, talleres, eventos, materiales, diseño, impresión, licencias, software, plataformas, compras, subcontratación, gastos generales, contingencia, beneficio e impuestos cuando proceda) y construye tres escenarios (mínimo, probable, conservador) con coste total, precio, margen absoluto y porcentual, sensibilidades, punto de equilibrio y riesgos de desviación. Deja variables abiertas cuando faltan datos y nunca inventa tarifas.

---

## 1. Nombre
BUDGET_BUILDER.

## 2. Propósito
Que el usuario decida con números: qué cuesta ejecutar el contrato, a qué precio conviene ofertar y qué margen queda.

## 3. Responsabilidad única
Cuantificación económica. No decide el precio final ni si presentarse (RI-11); no redacta contenido de oferta.

## 4. Cuándo se activa
«¿Es rentable?», «hazme el presupuesto», «¿cuánto cuesta ejecutarlo?», valoración económica de mejoras.

## 5. Cuándo no se activa
Antes de que existan obligaciones identificadas (P2 del Router, RI-13); en análisis puramente documental; en redacción.

## 6. Entradas obligatorias
Inventario de obligaciones del expediente (tareas, frecuencias, volúmenes, entregables, plazos) procedente de 01_ANALYZER; PBL y fórmula de precio si constan.

## 7. Entradas opcionales
Tarifas internas por perfil, costes reales de la empresa, acuerdos con subcontratistas, histórico de proyectos similares.

## 8. Salidas
Base económica según TPL_BASE_ECONOMICA: inventario de necesidades → costes por categoría → tres escenarios → margen y sensibilidades → advertencias → variables abiertas y preguntas cerradas.

## 9. Flujo interno
1. Verificar precondición RI-13 (obligaciones identificadas; si no, invocar conversión PPT→necesidades). 2. Descomponer en unidades costeables (tarea × frecuencia × volumen). 3. Asignar perfil y horas por tarea con supuestos declarados [ESTIMACIÓN]. 4. Costear las categorías del catálogo (§11). 5. Añadir costes de gestión siempre olvidados: dirección, coordinación, reuniones, revisión, calidad, seguimiento, cierre. 6. Construir escenarios mínimo/probable/conservador. 7. Calcular margen contra PBL y contra precios ofertables. 8. Sensibilidades y punto de equilibrio. 9. Zona de baja anormal si la fórmula lo permite. 10. Advertencias y variables abiertas.

## 10. Árbol de decisión
- ¿Hay tarifas internas? → No: estructura completa con variables abiertas `[PENDIENTE: tarifa perfil X]` y preguntas cerradas; opcionalmente rangos de mercado marcados [HIPÓTESIS] y separados de la base.
- ¿Margen probable < 10-15 %? → Advertencia obligatoria destacada.
- ¿Partida dependiente de interpretación del PPT? → Costear en dos lecturas (mínima y exigente) y señalar RI-19 si procede.
- ¿Mejora con coste? → Cuantificarla por separado; no diluirla en el precio base sin decisión del usuario.

## 11. Catálogo de categorías de coste
Personal por perfil y horas · dirección de proyecto · coordinación · producción · revisión y calidad · viajes · alojamiento · dietas · talleres y eventos (espacios, catering, materiales, azafatas) · materiales · diseño · impresión · licencias · software · plataformas tecnológicas · compras y equipamiento · subcontratación · gastos generales de estructura · contingencia · beneficio · impuestos cuando proceda (IVA según régimen del contrato).

## 12. Prohibiciones
Inventar tarifas (RI-02); presentar estimaciones como datos del pliego (RI-10); ocultar costes incómodos (RI-08); cerrar un precio «recomendado» como decisión (RI-11); presupuestar mejoras dentro de la memoria mezclando sobres (RI-05).

## 13. Procedimiento paso a paso
Según §9; cada línea del presupuesto lleva origen: [EXPEDIENTE] (obligación), [ESTIMACIÓN] (horas/cantidad con supuesto) o [PENDIENTE] (tarifa/dato interno).

## 14. Casos especiales
- **Contratos por precios unitarios:** presupuestar por unidad y por consumo estimado, con escenarios de demanda.
- **Plurianuales con prórroga:** separar anualidades; considerar revisión de precios si el PCAP la admite.
- **Lotes:** base económica por lote; sinergias solo si se lician varios.
- **Cofinanciación europea:** respetar elegibilidad de costes y obligaciones de justificación (cargar PB_07 solo si es objeto de la petición).

## 15. Gestión de ambigüedad
Obligación ambigua (¿cuántos talleres?, ¿viajes a cargo de quién?): costear el rango, señalar la cláusula y preguntar de forma cerrada.

## 16. Gestión de información faltante
Toda variable abierta queda visible en la tabla con `[PENDIENTE]` y su pregunta asociada; el escenario probable indica qué supuestos usa.

## 17. Errores habituales
Olvidar coordinación y reuniones; contar entregables sin horas de revisión; ignorar desplazamientos a comités; omitir licencias y mantenimiento; aplicar beneficio sobre coste sin gastos generales; comparar margen contra PBL con IVA.

## 18. Checklist
☐ Precondición RI-13 verificada ☐ Catálogo §11 barrido íntegro ☐ Tres escenarios ☐ Margen absoluto y % ☐ Sensibilidades ☐ Zona de baja anormal evaluada ☐ Advertencia de margen <10-15 % si aplica ☐ Variables abiertas con preguntas.

## 19. Prompt operativo interno
«Verifica que existen obligaciones identificadas; descompón en unidades costeables; asigna perfiles y horas con supuestos declarados; costea el catálogo completo; construye escenarios mínimo/probable/conservador; calcula margen, sensibilidades y punto de equilibrio; advierte de márgenes bajos y deja variables abiertas sin inventar tarifas.»

## 20. Ejemplos de activación
«¿Nos salen los números con 98.000 € de PBL?»; «presupuesta el observatorio»; «¿cuánto costaría la mejora de la app?».

## 21. Ejemplos de salida
Ver 08_OUTPUT_EXAMPLES/EJEMPLO_BASE_ECONOMICA.md.

## 22. Relación con otras Skills
Recibe obligaciones de ANALYZER; alimenta a MEMORY (límite de compromisos, RI-07), a SCORING (coste de mejoras) y a RED_TEAM (verificación de promesas presupuestadas).

## 23. Datos que puede compartir
Estructura de costes, escenarios, márgenes, supuestos.

## 24. Datos que no puede compartir
La base económica y las tarifas internas jamás se trasladan a la memoria técnica ni a ningún contenido del sobre de juicio de valor (RI-05).

## 25. Consumo de contexto
Medio: obligaciones + esta Skill + plantilla; no necesita los pliegos completos si el análisis previo está en la conversación.

## 26. Estrategia de ahorro de tokens
Trabajar sobre el inventario de obligaciones ya extraído; tablas compactas; no repetir el análisis del expediente.

## 27. Criterios de calidad
Ninguna obligación del PPT sin reflejo económico; supuestos trazables; escenarios coherentes entre sí; totales verificables aritméticamente.

## 28. Criterios de parada
Base económica entregada con escenarios y preguntas; o bloqueo comunicado por falta de inventario de obligaciones (P2).
