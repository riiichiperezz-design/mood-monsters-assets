# SKILL 03 — MEMORY_WRITER

> **Propósito:** redactar la memoria técnica (índice y apartados) trazada contra los criterios de adjudicación.
> **Cuándo cargarlo:** cuando el usuario solicite expresamente índice o redacción de memoria (clase E del Router).
> **Cuándo no cargarlo:** análisis, solvencia, presupuesto, revisión, visuales sueltos o cuestiones jurídicas.
> **Skills que lo utilizan:** ROUTER la activa tras SCORING; invoca a GOVERNANCE, PLANNING, RISK, DELIVERABLES, KPI y VISUAL para apartados específicos; EDITORIAL pule su salida; RED_TEAM la revisa.
> **Palabras clave:** memoria, redactar, índice, oferta técnica, apartado.
> **Dependencias:** matriz de criterios de SCORING (obligatoria), análisis de ANALYZER, base económica de BUDGET (para RI-07), K-02, K-03, TPL_MEMORIA_TECNICA, playbook del sector (uno), CHK_MEMORIA.
> **Prioridad:** alta. **Coste de contexto:** alto durante redacción.
> **Resumen:** redacta memorias específicas, diferenciales, operativas, persuasivas, trazables, realistas, medibles y ejecutables. Trabaja siempre sobre un índice aprobado y trazado contra los criterios, respeta límites formales (páginas, tipografía, estructura), aplica la ficha estándar de apartado y nunca introduce experiencia, herramientas, personal, certificaciones o compromisos no validados o no presupuestados. Mantiene la separación estricta de sobres.

---

## 1. Nombre
MEMORY_WRITER.

## 2. Propósito
Producir el contenido del sobre de criterios de juicio de valor con la máxima puntuación defendible sin infringir el pliego.

## 3. Responsabilidad única
Redacción de la memoria. No define la estrategia de puntos (SCORING), no presupuesta (BUDGET), no se autorrevisa como Red Team.

## 4. Cuándo se activa
Solo a petición expresa del usuario (RI y flujo: la memoria nunca se redacta espontáneamente) y tras análisis de criterios (P1).

## 5. Cuándo no se activa
Sin matriz de criterios; sin decisión del usuario de avanzar; para mejoras o contenido de sobres automáticos (RI-05, RI-06).

## 6. Entradas obligatorias
Matriz de criterios (SCORING); requisitos y obligaciones (ANALYZER); límites formales del pliego (páginas, tipografía, estructura exigida); información interna validada disponible.

## 7. Entradas opcionales
Base económica (para verificar RI-07), playbook del sector, ejemplos calibrados, materiales internos acreditados de la empresa.

## 8. Salidas
(a) Propuesta de índice trazado criterio→apartado con reparto orientativo de páginas; (b) lista de información interna pendiente; (c) apartados redactados con la ficha estándar; (d) avisos de necesidades visuales para VISUAL_DESIGNER.

## 9. Flujo interno
1. Verificar precondiciones (P1; límites formales identificados; decisión del usuario). 2. Separar memoria / mejoras / criterios automáticos (RI-05, RI-06). 3. Construir índice: cada criterio y subcriterio tiene apartado(s) responsable(s); reparto de páginas proporcional a puntos. 4. Someter índice al usuario y recoger información interna pendiente. 5. Redactar apartado a apartado con la ficha estándar (VERSION_COMPLETA §5). 6. Invocar Skills de apartado (gobernanza, plan, riesgos, entregables, KPI, visuales) según el índice. 7. Autochequeo CHK_MEMORIA. 8. Entregar para Red Team.

## 10. Árbol de decisión
- ¿Índice aprobado? → No: proponer índice y parar (RI-20).
- ¿El pliego impone estructura? → Sí: la estructura del pliego manda sobre cualquier plantilla (RI-01, RI-14).
- ¿Dato interno sin validar? → `[PENDIENTE]` visible en borrador; nunca inventado en versión final.
- ¿Compromiso con coste? → Verificar contra base económica; si no está presupuestado, avisar (RI-07) y pedir decisión.
- ¿Contenido roza sobre automático? → Retirar y avisar (RI-05).

## 11. Reglas prioritarias de redacción
- Específica: nombres, números, frecuencias, responsables del contrato concreto.
- Diferencial: qué hacemos distinto y por qué puntúa (con K-05).
- Trazable: cada apartado cita la cláusula/criterio al que responde.
- Realista y ejecutable: nada que el equipo no pueda cumplir en plazo.
- Medible: compromisos con indicador y meta.
- Extensión: respeta límites del pliego; reparte páginas por puntos, no por facilidad.

## 12. Prohibiciones
Inventar experiencia, herramientas, personal o certificaciones (RI-02, RI-03, RI-04); crear mejoras gratuitas no aprobadas (RI-06, RI-07); introducir información de sobres automáticos (RI-05); asumir compromisos no presupuestados (RI-07); texto genérico de consultoría (RI-16); copiar memorias de referencia (RI-09).

## 13. Procedimiento paso a paso
Ver §9. Redacción por lotes de apartados (2-4 por turno) para mantener calidad y contexto.

## 14. Casos especiales
- **Límite de páginas severo:** priorizar por puntos; comprimir con tablas y visuales; recortar lo no evaluable.
- **Plantilla obligatoria del órgano:** rellenarla literalmente; no «mejorar» su estructura (RI-14).
- **UTE:** atribuir capacidades a cada miembro según lo validado.
- **Memoria + defensa oral:** marcar qué apartados alimentan la presentación.

## 15. Gestión de ambigüedad
Criterio ambiguo («calidad de la metodología»): descomponerlo en sub-elementos evaluables usando K-05 y el propio tenor del pliego; declarar la lectura adoptada.

## 16. Gestión de información faltante
Bloques `[PENDIENTE: dato interno]` listados al final de cada entrega; la memoria no se declara terminada con pendientes abiertos.

## 17. Errores habituales
Prosa institucional sin compromisos; describir la empresa en lugar de resolver el contrato; prometer talleres/productos no presupuestados; ignorar el umbral mínimo de puntos de la memoria; repetir el PPT parafraseado sin valor añadido.

## 18. Checklist
☐ Índice trazado y aprobado ☐ Límites formales respetados ☐ Ficha estándar aplicada ☐ Cero datos inventados ☐ Cero contenido de otros sobres ☐ Compromisos presupuestados ☐ Pendientes listados ☐ Listo para Red Team.

## 19. Prompt operativo interno
«Con la matriz de criterios y los límites formales, propone índice trazado con reparto de páginas; tras aprobación, redacta cada apartado con la ficha estándar, específico y medible, citando la trazabilidad con el pliego; marca [PENDIENTE] lo no validado; verifica RI-05/06/07 antes de entregar.»

## 20. Ejemplos de activación
«Prepárame el índice de la memoria»; «redacta el apartado de metodología»; «desarrolla el plan de trabajo de la memoria».

## 21. Ejemplos de salida
Ver EJEMPLO_INDICE_MEMORIA.md y EJEMPLO_APARTADO_MEMORIA.md.

## 22. Relación con otras Skills
Aguas arriba: SCORING (matriz), ANALYZER (requisitos), BUDGET (límite de compromisos). Aguas abajo: VISUAL, GOVERNANCE, PLANNING, RISK, DELIVERABLES, KPI (apartados), EDITORIAL (pulido), RED_TEAM (revisión).

## 23. Datos que puede compartir
Índice, borradores, trazabilidad, pendientes.

## 24. Datos que no puede compartir
Precio, mejoras cuantificadas y cualquier dato evaluable por fórmula (RI-05); tarifas y márgenes internos.

## 25. Consumo de contexto
Alto: matriz + requisitos + plantilla + playbook + apartados en curso. Mitigación en §26.

## 26. Estrategia de ahorro de tokens
Redactar por lotes; no recargar los pliegos completos (usar el análisis); cargar un único playbook; invocar Skills de apartado solo cuando toque su apartado.

## 27. Criterios de calidad
Cada criterio con cobertura proporcional a sus puntos; cada apartado con compromisos concretos y trazabilidad; lectura fluida para un evaluador con poco tiempo.

## 28. Criterios de parada
Todos los apartados del índice entregados y CHK_MEMORIA superado (pasa a Red Team); o parada por pendientes críticos (RI-20).
