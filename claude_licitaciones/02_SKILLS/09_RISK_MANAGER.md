# SKILL 09 — RISK_MANAGER

> **Propósito:** generar el análisis de riesgos del contrato con matriz completa: riesgo, causa, probabilidad, impacto, nivel, prevención, contingencia, responsable e indicador.
> **Cuándo cargarlo:** apartado de riesgos de la memoria, análisis de riesgos del expediente o peticiones expresas.
> **Cuándo no cargarlo:** extracción rápida, presupuesto puro, visuales, edición.
> **Skills que lo utilizan:** MEMORY (apartado de riesgos), ANALYZER (riesgos del expediente), PLANNING (riesgos temporales), RED_TEAM (contraste).
> **Palabras clave:** riesgos, contingencia, matriz de riesgos, mitigación.
> **Dependencias:** K-10, TPL_RIESGOS; análisis del expediente.
> **Prioridad:** alta. **Coste de contexto:** medio.
> **Resumen:** produce matrices de riesgos específicas del contrato (nunca catálogos genéricos): riesgos de ejecución, de plazo, de equipo, de datos, de terceros, reputacionales y contractuales, cada uno con causa concreta, valoración probabilidad×impacto, medida preventiva operativa, plan de contingencia activable, responsable nominal del equipo e indicador de alerta temprana. Distingue los riesgos internos (para decisión de la empresa) de los publicables en la memoria.

---

## 1. Nombre
RISK_MANAGER.

## 2. Propósito
Riesgos creíbles y gestionados que puntúen por madurez y protejan la ejecución.

## 3. Responsabilidad única
Identificación y tratamiento de riesgos. No decide si el riesgo global es aceptable (RI-11).

## 4. Cuándo se activa
Apartado de riesgos de memoria; «¿qué riesgos tiene este contrato?»; riesgos de una fase o mejora concreta.

## 5. Cuándo no se activa
Antes de conocer el expediente; para riesgos jurídicos de interpretación (van a 13_PROCUREMENT).

## 6. Entradas obligatorias
Análisis del expediente (alcance, plazos, equipo, dependencias); destino de la matriz (interna o memoria).

## 7. Entradas opcionales
Plan de trabajo, base económica, experiencia previa validada en contratos similares.

## 8. Salidas
Matriz TPL_RIESGOS:

| Riesgo | Causa | Probabilidad | Impacto | Nivel | Prevención | Contingencia | Responsable | Indicador |
|---|---|---|---|---|---|---|---|---|

más mapa de calor opcional (VISUAL) y, en versión interna, riesgos de negocio no publicables.

## 9. Flujo interno
1. Determinar el destino (interno vs. memoria: contenidos distintos). 2. Barrer categorías: alcance, plazo, equipo, datos/información, terceros/subcontratas, tecnología, participación/asistencia, estacionalidad, contractuales (penalidades, modificados), reputacionales. 3. Formular cada riesgo con causa específica del contrato. 4. Valorar P×I (escala 1-3 o 1-5 declarada) → nivel. 5. Prevención operativa (quién hace qué y cuándo). 6. Contingencia activable (disparador + acción). 7. Responsable del equipo real + indicador de alerta. 8. Ordenar por nivel.

## 10. Árbol de decisión
- ¿Matriz para la memoria? → Solo riesgos de ejecución gestionables; excluir riesgos de negocio propios (margen, solvencia) que debilitan la oferta.
- ¿Matriz interna? → Incluirlo todo, también los 13 riesgos de catálogo de las instrucciones centrales.
- ¿Riesgo sin prevención posible? → Decirlo y tratarlo por contingencia y transferencia (seguro, subcontrata).
- ¿Riesgo crítico estructural (plazo imposible, solvencia dudosa)? → Escalarlo al bloque interno para decisión del usuario (RI-20).

## 11. Reglas prioritarias
Riesgos formulados como evento incierto con causa («retraso en la cesión de datos del ayuntamiento por vacaciones del servicio», no «retrasos»); prevención ≠ contingencia; responsable = rol ofertado real (RI-04); indicador medible.

## 12. Prohibiciones
Catálogos genéricos copiables a cualquier contrato (RI-16); minimizar riesgos reales en la versión interna (RI-08, RI-19); publicar en memoria debilidades internas de la empresa; inventar historial de gestión de riesgos (RI-02).

## 13. Procedimiento paso a paso
Ver §9.

## 14. Casos especiales
Eventos (riesgos con hito duro: meteorología, permisos, proveedores); observatorios (calidad y disponibilidad de datos); fondos europeos (riesgos de elegibilidad y plazos de justificación); oficinas técnicas (picos de demanda).

## 15. Gestión de ambigüedad
Impacto dependiente de interpretación del pliego → dos valoraciones con la lectura de cada una.

## 16. Gestión de información faltante
Sin equipo validado → responsables por rol [PENDIENTE]; sin plan → riesgos temporales genéricos marcados para refinar tras PLANNING.

## 17. Errores habituales
Confundir riesgo con problema actual; matrices sin contingencia; responsables «el equipo»; olvidar riesgos de terceros y de datos; mismo nivel para todo.

## 18. Checklist
☐ Destino determinado ☐ Categorías barridas ☐ Causas específicas ☐ P×I con escala declarada ☐ Prevención y contingencia distintas ☐ Responsables reales ☐ Indicadores de alerta ☐ Orden por nivel.

## 19. Prompt operativo interno
«Determina el destino de la matriz; barre las categorías de riesgo del contrato concreto; formula evento+causa; valora P×I; define prevención, contingencia activable, responsable real e indicador; ordena por nivel.»

## 20. Ejemplos de activación
«Apartado de riesgos de la memoria»; «riesgos de ejecutar esto con 2 personas»; «¿qué puede salir mal en el evento?».

## 21. Ejemplos de salida
Matriz de 9 columnas con 8-15 riesgos específicos, agrupados por categoría y ordenados por nivel.

## 22. Relación con otras Skills
Consume ANALYZER y PLANNING; alimenta MEMORY, el bloque interno de decisión y RED_TEAM.

## 23. Datos que puede compartir
Matriz del destino solicitado.

## 24. Datos que no puede compartir
La matriz interna (con debilidades propias) nunca se vuelca en la memoria.

## 25. Consumo de contexto
Medio.

## 26. Estrategia de ahorro de tokens
Partir del análisis existente; no recargar pliegos; tabla directa sin prosa introductoria larga.

## 27. Criterios de calidad
Cada riesgo pasa la prueba «¿podría copiarse a otro contrato sin cambios?» — si sí, es genérico y se reescribe.

## 28. Criterios de parada
Matriz entregada y ordenada; riesgos críticos estructurales escalados al usuario.
