# SKILL 12 — TOURISM_PLAYBOOKS

> **Propósito:** identificar la tipología turística del contrato y aplicar el playbook sectorial correspondiente (05_PLAYBOOKS_TURISMO) al análisis y a la memoria.
> **Cuándo cargarlo:** cuando el objeto del contrato sea turístico y se necesite conocimiento sectorial (análisis avanzado, índice o redacción de memoria).
> **Cuándo no cargarlo:** contratos no turísticos; fases puramente administrativas o económicas; nunca cargar varios playbooks a la vez sin justificación.
> **Skills que lo utilizan:** MEMORY (contenido sectorial), ANALYZER (comprensión del objeto), SCORING (diferenciales sectoriales).
> **Palabras clave:** turismo, DTI, destino, observatorio, promoción, plan turístico, playbook.
> **Dependencias:** PB_11 (tabla de enrutado) y el playbook seleccionado.
> **Prioridad:** alta. **Coste de contexto:** alto (el playbook cargado es denso).
> **Resumen:** Skill puente entre el sistema y la biblioteca sectorial. Clasifica el contrato en una de las tipologías turísticas (DTI, planificación, marketing, observatorios, eventos, transformación digital, fondos europeos, oficinas técnicas, participación, comunicación), carga únicamente el playbook pertinente y traduce sus patrones (metodologías de referencia, estructura típica de servicios, errores del sector, vocabulario del evaluador, diferenciales que puntúan) al contrato concreto, siempre subordinados al pliego (RI-01).

---

## 1. Nombre
TOURISM_PLAYBOOKS.

## 2. Propósito
Aportar profundidad sectorial real (métodos, estándares, vocabulario, diferenciales) sin contaminar la oferta con contenido ajeno al pliego.

## 3. Responsabilidad única
Selección y aplicación de playbooks. No redacta apartados completos (MEMORY) ni analiza el expediente (ANALYZER).

## 4. Cuándo se activa
Objeto turístico identificado + fase de estrategia o redacción; preguntas sectoriales («¿qué ejes tiene un plan DTI?»).

## 5. Cuándo no se activa
Contratos no turísticos; extracción rápida; solvencia; presupuesto (salvo estructuras de coste típicas del sector si se piden).

## 6. Entradas obligatorias
Objeto y alcance del contrato (ANALYZER).

## 7. Entradas opcionales
CPV, memoria justificativa (revela la intención real del órgano), contexto del destino.

## 8. Salidas
Tipología asignada + playbook seleccionado + patrones aplicables traducidos al contrato: metodologías de referencia, estructura de servicios, estándares del sector (SEGITTUR, UNE, guías oficiales), diferenciales que puntúan, errores a evitar, vocabulario del evaluador.

## 9. Flujo interno
1. Clasificar el contrato con PB_11 (tabla objeto→tipología). 2. Cargar solo el playbook correspondiente. 3. Filtrar patrones aplicables al alcance real del pliego (RI-01: nada se incorpora solo porque esté en el playbook). 4. Entregar los patrones al módulo solicitante con la marca de su origen (metodología, no requisito).

## 10. Árbol de decisión
- ¿Objeto híbrido (p. ej. observatorio + plan de marketing)? → Playbook principal por peso en el objeto; el secundario solo para su apartado concreto y de forma consecutiva, no simultánea.
- ¿Tipología sin playbook propio? → PB_11 patrones generales por tipo de contrato.
- ¿Patrón del playbook contradice el pliego? → Gana el pliego, siempre (RI-01).

## 11. Reglas prioritarias
Un playbook por vez (RI-17); patrones marcados como metodología, nunca como requisito (RI-01); estándares citados solo si son reales y vigentes (RI-15: validar si hay duda).

## 12. Prohibiciones
Cargar la biblioteca completa; trasplantar contenido de otra tipología; presentar prácticas sectoriales como exigencias del pliego; inventar estándares o sellos (RI-02).

## 13. Procedimiento paso a paso
Ver §9.

## 14. Casos especiales
Contratos multi-destino (aplicar el playbook con capa territorial); contratos cofinanciados (PB_07 como playbook secundario para las obligaciones de fondos); pliegos que citan expresamente un método (ese método manda).

## 15. Gestión de ambigüedad
Tipología dudosa → clasificar por la prestación con más peso económico/de puntos y declararlo.

## 16. Gestión de información faltante
Sin memoria justificativa ni contexto → aplicar el playbook con prudencia y marcar los supuestos [HIPÓTESIS].

## 17. Errores habituales
Volcar el playbook entero en la memoria (RI-16); usar jerga sectorial sin sustancia; ignorar el playbook y redactar genérico; citar normas UNE derogadas.

## 18. Checklist
☐ Tipología asignada y justificada ☐ Un solo playbook cargado ☐ Patrones filtrados por el pliego ☐ Origen metodológico marcado ☐ Estándares verificados.

## 19. Prompt operativo interno
«Clasifica el contrato con PB_11; carga el playbook de la tipología; filtra los patrones aplicables al alcance del pliego; entrégalos marcados como metodología al módulo solicitante.»

## 20. Ejemplos de activación
«Es un contrato de oficina técnica DTI, ¿qué enfoque damos?»; «prepara el marco metodológico del observatorio».

## 21. Ejemplos de salida
«Tipología: PB_04 Observatorios. Patrones aplicables: sistema de indicadores en 4 capas (oferta, demanda, sostenibilidad, competitividad); fuentes INE/Turespaña/datos propios; entregable estrella: informe de coyuntura trimestral; diferencial que puntúa: cuadro de mando abierto al sector local…»

## 22. Relación con otras Skills
Sirve a MEMORY, SCORING y ANALYZER; se apoya en PB_11 para enrutar.

## 23. Datos que puede compartir
Patrones, metodologías, estándares, vocabulario.

## 24. Datos que no puede compartir
Contenido de playbooks no seleccionados (no debe estar cargado).

## 25. Consumo de contexto
Alto cuando el playbook está cargado; por eso solo se carga uno.

## 26. Estrategia de ahorro de tokens
PB_11 como filtro previo barato; extraer del playbook solo las secciones pertinentes a la petición.

## 27. Criterios de calidad
Los patrones entregados son específicos de la tipología, vigentes y subordinados al pliego.

## 28. Criterios de parada
Patrones entregados al módulo solicitante; o contrato clasificado como no turístico (la Skill se retira).
