# SKILL 08 — PLANNING_ENGINE

> **Propósito:** desarrollar la planificación del contrato: fases, actividades, dependencias, duraciones, hitos, entregables, validaciones, ruta crítica, holguras, responsables y riesgos temporales.
> **Cuándo cargarlo:** apartados de plan de trabajo/cronograma de la memoria o peticiones expresas de planificación.
> **Cuándo no cargarlo:** análisis documental, solvencia, presupuesto puro, revisión.
> **Skills que lo utilizan:** MEMORY (plan de trabajo), VISUAL (Gantt), RISK (riesgos temporales), DELIVERABLES (momentos de entrega).
> **Palabras clave:** plan de trabajo, cronograma, fases, hitos, ruta crítica, planificación.
> **Dependencias:** K-12, TPL_PLAN_DE_TRABAJO, TPL_CRONOGRAMA; plazos y tareas del expediente (ANALYZER).
> **Prioridad:** alta. **Coste de contexto:** medio.
> **Resumen:** convierte tareas y plazos del pliego en un plan defendible: descomposición en fases y actividades con dependencias explícitas, duraciones justificadas, hitos alineados con los plazos parciales del PCAP, validaciones del cliente como actividades con duración propia, ruta crítica identificada y holguras declaradas. Detecta plazos poco realistas y los señala como riesgo en lugar de disimularlos.

---

## 1. Nombre
PLANNING_ENGINE.

## 2. Propósito
Un plan que demuestre dominio de la ejecución y resista el contraste con los plazos del pliego.

## 3. Responsabilidad única
Planificación temporal y estructura de trabajo. No costea (BUDGET), no define gobernanza (GOVERNANCE), no dibuja (VISUAL).

## 4. Cuándo se activa
«Haz el plan de trabajo/cronograma»; MEMORY llega al apartado de planificación.

## 5. Cuándo no se activa
Sin tareas ni plazos extraídos; en fases de análisis inicial.

## 6. Entradas obligatorias
Plazo total, plazos parciales e hitos del PCAP; tareas y entregables del PPT; fecha estimada de inicio.

## 7. Entradas opcionales
Equipo y dedicaciones, calendario de eventos del destino (temporada alta, ferias), condicionantes estacionales.

## 8. Salidas
Plan por fases (TPL_PLAN_DE_TRABAJO): fase → actividades → dependencias → duración → responsables → entregables → validaciones; tabla de hitos; ruta crítica y holguras; riesgos temporales; datos listos para Gantt (VISUAL).

## 9. Flujo interno
1. Fijar el marco temporal (inicio, fin, hitos del pliego). 2. Descomponer en fases con lógica del servicio (arranque → diagnóstico/producción → despliegue → seguimiento → cierre/transferencia). 3. Descomponer fases en actividades con verbo de acción. 4. Establecer dependencias (fin-inicio por defecto; solapes declarados). 5. Duraciones justificadas [ESTIMACIÓN]. 6. Insertar validaciones del cliente como actividades (con plazo de revisión). 7. Calcular ruta crítica y holguras. 8. Contrastar contra plazos del pliego; señalar tensiones. 9. Alinear hitos de facturación/entrega si el PCAP los fija.

## 10. Árbol de decisión
- ¿Plazo del pliego insuficiente para el alcance? → No comprimir en silencio: plan realista + riesgo temporal señalado + medidas de aceleración explícitas.
- ¿Actividades estacionales (eventos, temporada)? → Anclarlas al calendario real.
- ¿Dependencias de terceros (datos del cliente, permisos)? → Actividades de espera visibles + supuestos declarados.
- ¿Arranque incierto (fecha de formalización)? → Cronograma en semanas/meses relativos (M1, M2…).

## 11. Reglas prioritarias
Todo entregable del PPT aparece en el plan; toda validación del cliente consume tiempo visible; la ruta crítica se declara; las holguras no se rellenan con promesas; coherencia total con equipo (GOVERNANCE) y dedicaciones (BUDGET, RI-07).

## 12. Prohibiciones
Planes imposibles para puntuar (RI-14 y realismo de MEMORY); duraciones sin justificar; omitir tareas del PPT; hitos incompatibles con los plazos parciales del PCAP.

## 13. Procedimiento paso a paso
Ver §9.

## 14. Casos especiales
Contratos plurianuales (plan detallado año 1 + marco años siguientes); oficinas técnicas (plan por flujos recurrentes + bolsa de peticiones); eventos (cuenta atrás con hitos duros inamovibles).

## 15. Gestión de ambigüedad
Plazo ambiguo («a lo largo del contrato»): proponer calendario concreto [INTERPRETACIÓN] y declarar el criterio.

## 16. Gestión de información faltante
Sin fecha de inicio → tiempo relativo; sin volumen de tareas → escenarios de carga con supuestos.

## 17. Errores habituales
Olvidar las validaciones del cliente; Gantt incoherente con el texto; actividades de cierre y transferencia ausentes; ruta crítica no identificada; ignorar agosto y periodos electorales en contratos públicos.

## 18. Checklist
☐ Marco temporal del pliego respetado ☐ Todas las tareas del PPT en el plan ☐ Dependencias explícitas ☐ Validaciones con duración ☐ Ruta crítica y holguras ☐ Riesgos temporales señalados ☐ Coherencia equipo/presupuesto.

## 19. Prompt operativo interno
«Con plazos e hitos del PCAP y tareas del PPT, construye fases → actividades → dependencias → duraciones justificadas; inserta validaciones; calcula ruta crítica y holguras; señala tensiones de plazo; entrega plan + datos de Gantt.»

## 20. Ejemplos de activación
«Plan de trabajo para los 12 meses»; «cronograma del plan de marketing»; «¿da tiempo a hacer esto en 6 meses?».

## 21. Ejemplos de salida
Tabla de fases/actividades + tabla de hitos + «Ruta crítica: A1.2 → A2.1 → A3.4; holgura total 3 semanas concentrada en la fase 2».

## 22. Relación con otras Skills
Consume ANALYZER (plazos, tareas); alimenta VISUAL (Gantt), RISK (riesgos temporales), DELIVERABLES (momentos), MEMORY (apartado).

## 23. Datos que puede compartir
Plan completo, ruta crítica, tensiones detectadas.

## 24. Datos que no puede compartir
Horas/costes internos por actividad (eso es de BUDGET y no va a la memoria).

## 25. Consumo de contexto
Medio.

## 26. Estrategia de ahorro de tokens
Trabajar sobre tareas ya extraídas; tablas compactas; Gantt delegado a VISUAL solo si se pide.

## 27. Criterios de calidad
Un evaluador puede reconstruir la lógica del plan; cero incoherencias con plazos del pliego; realismo defendible en entrevista.

## 28. Criterios de parada
Plan entregado con ruta crítica y riesgos; o bloqueo por falta de plazos/tareas.
