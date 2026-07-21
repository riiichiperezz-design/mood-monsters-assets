# SKILL 00 — KNOWLEDGE_ROUTER

> **Propósito:** clasificar cada petición del usuario, decidir qué Skills y documentos cargar, controlar el orden de fases e impedir cargas y respuestas innecesarias.
> **Cuándo cargarlo:** siempre, al inicio de cada petición; es la primera Skill que se ejecuta.
> **Cuándo no cargarlo:** nunca se omite; su coste es bajo.
> **Skills que lo utilizan:** todas dependen de su enrutado.
> **Palabras clave de activación:** cualquier petición (enrutador universal).
> **Dependencias:** 09_BUILD/MANIFEST.json, 09_BUILD/FILE_INDEX.md, 03_WORKFLOWS/WF_MASTER.md.
> **Prioridad:** crítica. **Coste de contexto:** bajo.
> **Resumen:** Skill orquestadora. Clasifica la petición en una de las 10 clases operativas, identifica la fase del expediente según WF_MASTER, selecciona el conjunto mínimo de Skills y documentos, excluye módulos irrelevantes, detecta archivos faltantes, impide saltos de fase (memoria sin análisis, presupuesto sin obligaciones) y regula la longitud de la respuesta. Contiene la tabla de enrutado completa y el árbol de decisión que ejecuta antes de cualquier trabajo de fondo.

---

## 1. Nombre
KNOWLEDGE_ROUTER.

## 2. Propósito
Garantizar que cada petición se atiende con las Skills y los documentos estrictamente necesarios, en la fase correcta del workflow y con el formato de salida adecuado.

## 3. Responsabilidad única
Clasificar, seleccionar, ordenar y limitar. No analiza expedientes, no redacta, no presupuesta.

## 4. Cuándo se activa
En toda petición, como primer paso silencioso.

## 5. Cuándo no se activa
Nunca deja de activarse; en peticiones triviales (saludo, aclaración breve) resuelve sin cargar ningún módulo.

## 6. Entradas obligatorias
Petición del usuario; estado actual del expediente (si existe trabajo previo en la conversación).

## 7. Entradas opcionales
MANIFEST.json / FILE_INDEX.md; lista de archivos subidos.

## 8. Salidas
Plan de ejecución interno: clase de petición, fase WF, Skills activadas, documentos a consultar, documentos excluidos, formato de salida, bloqueos detectados.

## 9. Flujo interno
1. Leer la petición y el historial inmediato. 2. Clasificar en una clase operativa (tabla §10). 3. Determinar la fase del expediente (estados WF_MASTER 0-17). 4. Verificar precondiciones de fase (§11 reglas P). 5. Seleccionar Skills y documentos (tabla §10). 6. Excluir explícitamente lo irrelevante. 7. Comprobar archivos faltantes. 8. Fijar formato y extensión de salida. 9. Ceder el control a la primera Skill del plan.

## 10. Árbol de decisión y tabla de enrutado

| Clase de petición | Señales típicas | Skills (orden) | Documentos a consultar | Excluir siempre |
|---|---|---|---|---|
| A. Subida de expediente / «analiza» | archivos PCAP/PPT, «analiza este pliego» | 01_ANALYZER | WF_01-02, TPL_EXTRACCION, TPL_RESUMEN, CHK_DOCUMENTOS | Red Team, memoria, visuales, playbooks no identificados aún, legislación |
| B. Solvencia / personal | «¿cumplimos solvencia?», «equipo exigido» | 01_ANALYZER (+13_PROCUREMENT si hay duda jurídica) | WF_03, K-07, K-08, TPL_MATRIZ_SOLVENCIA/PERSONAL, CHK_SOLVENCIA | Visuales, presupuesto, memorias, playbooks |
| C. Criterios / estrategia de puntos | «criterios», «cómo se puntúa», «estrategia» | 04_SCORING | WF_04, K-05, K-06, TPL_MATRIZ_CRITERIOS | Presupuesto detallado, Red Team, visuales |
| D. Costes / presupuesto / viabilidad | «presupuesto», «costes», «margen», «¿es rentable?» | 02_BUDGET | WF_05-06, K-09, TPL_BASE_ECONOMICA, CHK_COSTES | Playbooks, memoria, visuales, legislación |
| E. Memoria (índice o redacción) | «memoria», «índice», «redacta el apartado» | 04_SCORING → 03_MEMORY (+07/08/09/10/11 según apartado) | WF_07, K-02, K-03, TPL_MEMORIA, playbook del sector (solo uno), EJEMPLO si primera vez | Legislación (salvo duda), Red Team (hasta borrador), playbooks ajenos |
| F. Mejoras / criterios automáticos | «mejoras», «sobre 3», «oferta económica» | 04_SCORING + 02_BUDGET | WF_08, K-06, CHK_SOBRES | Memoria, playbooks, visuales |
| G. Revisión / Red Team | «revisa», «red team», «audita la memoria» | 05_RED_TEAM (+14_EDITORIAL para hallazgos editoriales) | WF_09, K-14, TPL_RED_TEAM, CHK_RED_TEAM, CHK_SOBRES | Playbooks, presupuesto (salvo promesas no presupuestadas), visuales |
| H. Visuales | «SVG», «diagrama», «Gantt», «organigrama» | 06_VISUAL | K-16 (+datos del módulo de origen) | Legislación, presupuesto, solvencia, Red Team, playbooks |
| I. Cuestión jurídica | «¿es legal?», «recurso», «LCSP», «plazo de subsanación» | 13_PROCUREMENT | K-18 | Playbooks, visuales, presupuesto, memoria |
| J. Edición / estilo | «pule», «acorta», «mejora la redacción» | 14_EDITORIAL | K-17 | Todo lo demás |

Peticiones mixtas: descomponer en subtareas y enrutar cada una; ejecutar en el orden del workflow, no en el orden de la frase.

## 11. Reglas prioritarias
- **P1 (RI-12):** no activar 03_MEMORY si no existe análisis de criterios; ejecutar antes clase C y proponer índice.
- **P2 (RI-13):** no activar escenarios de 02_BUDGET sin inventario de obligaciones económicas; ejecutar antes la conversión PPT→necesidades.
- **P3:** la extracción rápida precede a cualquier otra salida en clase A.
- **P4 (RI-20):** ante decisión interna crítica pendiente, detener y preguntar; no avanzar fases.
- **P5:** Red Team informa, no reescribe; las correcciones las aplica 03_MEMORY tras aprobación del usuario.
- **P6 (RI-17):** máximo orientativo por turno: 1 workflow + 3 Skills + 3 documentos de conocimiento + 1 playbook + plantillas necesarias.
- **P7:** pedir confirmación solo cuando el árbol lo exija (decisiones del usuario), no por cortesía.
- **P8 (RI-18):** fijar extensión objetivo de la respuesta proporcional a la petición; impedir respuestas infladas.

## 12. Prohibiciones
Cargar la base completa; cargar más de un playbook sin justificación; activar Red Team en primera lectura; redactar memoria en clase A-D; decidir por el usuario (RI-11); responder a peticiones triviales con módulos cargados.

## 13. Procedimiento paso a paso
Ver §9; ante ambigüedad de clase, aplicar §15.

## 14. Casos especiales
- **Expediente con lotes:** enrutar por lote elegido; si no hay elección, vista comparada + pregunta cerrada.
- **Usuario pide «todo»:** ejecutar el workflow en orden, anunciando el plan y entregando por fases.
- **Petición fuera de dominio** (no licitación): atender sin cargar ningún módulo del sistema.
- **Archivos ilegibles o incompletos:** informar y listar qué falta antes de analizar (CHK_DOCUMENTOS).

## 15. Gestión de ambigüedad
Si la petición admite dos clases, elegir la más temprana en el workflow y decirlo («empiezo por X porque Y depende de ello»). Solo preguntar si las interpretaciones llevan a entregables incompatibles.

## 16. Gestión de información faltante
Detectar documentos ausentes típicos (cuadro de características, anexo de criterios, modelo de proposición) y solicitarlos en lista cerrada; continuar con lo disponible marcando [PENDIENTE].

## 17. Errores habituales
Cargar playbooks «por si acaso»; saltar a memoria porque el usuario la menciona de pasada; repetir análisis ya hechos en la conversación; preguntar lo que ya consta.

## 18. Checklist
☐ Clase identificada ☐ Fase WF identificada ☐ Precondiciones P1-P4 verificadas ☐ Skills mínimas seleccionadas ☐ Exclusiones aplicadas ☐ Faltantes detectados ☐ Formato y extensión fijados.

## 19. Prompt operativo interno
«Clasifica la petición (A-J), identifica el estado WF (0-17), verifica P1-P8, selecciona el conjunto mínimo de módulos según la tabla §10, lista lo excluido, y cede el control a la primera Skill con el formato de salida fijado.»

## 20. Ejemplos de activación
«Te subo el PCAP y el PPT de la Diputación» → clase A. «¿Podemos acreditar la solvencia técnica?» → clase B. «Hazme el Gantt del plan» → clase H.

## 21. Ejemplos de salida
(Interna, no visible): «Clase E; estado WF 10; falta matriz de criterios → ejecutar clase C primero (P1); cargar K-02, K-05, TPL_MEMORIA, PB_04 (observatorio); excluir K-18, Red Team.»

## 22. Relación con otras Skills
Precede a todas; recibe de WF_MASTER el mapa de estados; devuelve el control al terminar cada Skill para decidir el siguiente paso.

## 23. Datos que puede compartir
Clase, fase, plan de módulos, bloqueos.

## 24. Datos que no puede compartir
No expone razonamientos de enrutado extensos al usuario; el plan se comunica en una línea solo cuando aporta claridad.

## 25. Consumo de contexto
Bajo (esta Skill + índice).

## 26. Estrategia de ahorro de tokens
Usar FILE_INDEX en lugar de MANIFEST completo; no citar documentos, solo referenciarlos; reutilizar análisis previos de la conversación en lugar de recargar fuentes.

## 27. Criterios de calidad
Ningún módulo irrelevante cargado; ninguna fase saltada; extracción rápida siempre primera en clase A; bloqueos comunicados con opciones.

## 28. Criterios de parada
El plan está fijado y la primera Skill toma el control; o existe un bloqueo RI-20 comunicado al usuario.
