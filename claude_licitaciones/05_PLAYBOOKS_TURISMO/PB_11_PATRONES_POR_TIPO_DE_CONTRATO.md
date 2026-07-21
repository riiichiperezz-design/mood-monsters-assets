# PB_11 — Patrones por tipo de contrato (tabla de enrutado)

> **Propósito:** clasificar el objeto del contrato en su tipología turística y enrutar al playbook correcto; patrones generales para tipologías sin playbook propio.
> **Cuándo cargarlo:** siempre antes que cualquier otro playbook (filtro barato de la Skill 12).
> **Cuándo no cargarlo:** contratos claramente no turísticos.
> **Skills que lo utilizan:** 12_TOURISM_PLAYBOOKS, 00_KNOWLEDGE_ROUTER.
> **Palabras clave:** qué playbook, tipología, clasificar contrato.
> **Dependencias:** ninguna (es el punto de entrada de la biblioteca).
> **Prioridad:** media. **Coste de contexto:** bajo.
> **Resumen:** tabla de enrutado objeto→tipología→playbook con señales de reconocimiento (términos del objeto, CPV orientativos, entregables mencionados), reglas para contratos híbridos (playbook principal por peso + secundario por apartado), patrones transversales comunes a todo contrato turístico (estacionalidad, multiactor, dato escaso, sensibilidad política) y patrones mínimos para tipologías sin playbook dedicado (sostenibilidad y accesibilidad como objetos propios, gobernanza de destinos, producto turístico, señalización e interpretación).

---

## 1. Tabla de enrutado

| Señales en el objeto/PPT | Tipología | Playbook |
|---|---|---|
| «destino turístico inteligente», «DTI», «SEGITTUR», «autodiagnóstico», «plan director DTI» | DTI | PB_01 |
| «plan estratégico de turismo», «plan de sostenibilidad», «plan de producto», «diagnóstico y plan de acción» | Planificación | PB_02 |
| «promoción», «campaña», «marca», «publicidad», «plan de medios», «creatividades» | Marketing/promoción | PB_03 |
| «observatorio», «inteligencia turística», «sistema de indicadores», «cuadro de mando», «coyuntura» | Observatorio/datos | PB_04 |
| «organización de evento/feria/congreso», «stand», «fam trip», «press trip», «jornadas» | Eventos | PB_05 |
| «transformación digital», «digitalización de empresas», «plataforma», «capacitación digital» | Transformación digital | PB_06 |
| «PRTR», «Next Generation», «PSTD», «FEDER», «justificación», «oficina de gestión de fondos» | Fondos europeos | PB_07 |
| «oficina técnica», «asistencia técnica continuada», «secretaría técnica», «apoyo al servicio de turismo» | Oficina técnica | PB_08 |
| «proceso participativo», «mesas», «talleres», «dinamización de agentes», «foro» | Participación | PB_09 |
| «comunicación», «contenidos», «redes sociales», «gabinete», «community» | Comunicación | PB_10 |

CPV orientativos frecuentes: `79*` (servicios de consultoría/apoyo empresarial), `793*` (estudios/publicidad/comunicación), `7999*` (varios servicios), `72*` (TI, en plataformas), `92*` (cultura/turismo en algunos órganos). El CPV orienta, el objeto decide.

## 2. Contratos híbridos (reglas)

1. Clasificar por la prestación de **mayor peso** (económico o de puntos): ese es el playbook principal.
2. El secundario se carga **solo** al trabajar su apartado, y de forma consecutiva (RI-17).
3. Combinaciones frecuentes: plan (PB_02) + participación (PB_09) · oficina (PB_08) + fondos (PB_07) · DTI (PB_01) + datos (PB_04) · promoción (PB_03) + eventos (PB_05).
4. Los fondos europeos (PB_07) actúan de capa transversal cuando el contrato está cofinanciado, sea cual sea la tipología.

## 3. Patrones transversales del turismo (aplican siempre)

- **Estacionalidad:** el plan se ancla al ciclo del destino (K-12 §5).
- **Multiactor:** ningún contrato turístico se ejecuta solo con el órgano; el mapa de actores y la gobernanza extendida (K-11 §7) aparecen en casi toda memoria.
- **Dato escaso a escala local** (PB_04 §3): humildad metodológica.
- **Sensibilidad política:** el turismo es vitrina; los productos tienen lectura pública (resumen ejecutivo comunicable, prudencia en diagnósticos duros — decir la verdad con formas).
- **Territorio rural** (frecuente en el nicho): distancias = coste (E7), brecha digital, aforos pequeños y memoria larga de procesos anteriores.

## 4. Tipologías sin playbook dedicado (patrones mínimos)

- **Sostenibilidad/accesibilidad como objeto propio:** estructura de PB_02 (diagnóstico→plan) + marcos específicos (indicadores de sostenibilidad, normativa de accesibilidad vigente — verificar, RI-15); la accesibilidad se audita in situ (coste de campo).
- **Gobernanza de destinos (entes de gestión, OGD):** diseño institucional + PB_08 para la operación; referencia K-11 §7.
- **Creación de producto turístico (rutas, experiencias):** inventario de recursos → diseño de producto → pilotaje con operadores → comercialización (conecta PB_03); el pilotaje real es el diferencial.
- **Señalización e interpretación del patrimonio:** inventario → plan de señalética → contenidos interpretativos → dirección de arte/producción; coordinación con patrimonio (autorizaciones: riesgo de calendario).

En estos casos, la Skill 12 aplica estos patrones mínimos + los transversales de §3 sin cargar otros playbooks.
