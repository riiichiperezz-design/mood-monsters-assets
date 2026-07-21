# INSTALACIÓN EN CLAUDE PROJECTS

> **Propósito:** pasos para instalar el sistema en Claude Projects con carga selectiva.
> **Cuándo cargarlo:** durante la instalación o reconfiguración. **Cuándo no:** en el trabajo diario.
> **Prioridad:** baja. **Coste:** bajo.
> **Resumen:** qué va en las instrucciones, qué va en Project Knowledge, en qué orden subirlo, cómo verificar la instalación y cómo operar si el Project tiene límites de espacio.

---

## 1. Crear el Project

1. En claude.ai → **Projects** → *Create Project*. Nombre sugerido: «Licitaciones Turismo — [Empresa]».
2. Descripción breve: «Análisis y preparación de licitaciones públicas españolas del sector turístico».

## 2. Instrucciones del Project (el paso crítico)

1. Abrir `01_PROJECT_INSTRUCTIONS/CLAUDE_PROJECT_INSTRUCTIONS.md`.
2. Copiar **solo el contenido entre los marcadores** «INICIO DE INSTRUCCIONES» y «FIN DE INSTRUCCIONES».
3. Pegarlo en el campo *Instructions* del Project.
4. Alternativa con poco espacio: usar `VERSION_CORTA.md` (mismos marcadores) — entonces es **obligatorio** subir `REGLAS_INVIOLABLES.md` a Project Knowledge.

## 3. Project Knowledge (subida por orden de prioridad)

Subir los archivos .md conservando sus nombres. Orden recomendado (si hay límite de capacidad, cortar por el final):

| Prioridad | Archivos | Motivo |
|---|---|---|
| 1 | `REGLAS_INVIOLABLES.md`, `02_SKILLS/00_KNOWLEDGE_ROUTER.md`, `09_BUILD/FILE_INDEX.md`, `09_BUILD/CONTEXT_LOADING_GUIDE.md`, `03_WORKFLOWS/WF_MASTER.md` | Núcleo de gobierno y enrutado |
| 2 | Resto de `02_SKILLS/` | Capacidades |
| 3 | `06_TEMPLATES/` y `07_CHECKLISTS/` | Formatos de salida y control |
| 4 | `03_WORKFLOWS/` restantes | Detalle de tramos |
| 5 | `04_KNOWLEDGE/` | Doctrina (consulta selectiva) |
| 6 | `05_PLAYBOOKS_TURISMO/` (al menos PB_11 + los de las tipologías que la empresa licita) | Sector |
| 7 | `08_OUTPUT_EXAMPLES/` | Calibración |
| Opcional | `00_README/`, `09_BUILD/MANIFEST.json`, `CHANGELOG.md`, `VALIDATION_REPORT.md` | Referencia/mantenimiento |

**No subir** `01_PROJECT_INSTRUCTIONS/CLAUDE_PROJECT_INSTRUCTIONS.md` ni `VERSION_CORTA.md` a Knowledge si ya están en las instrucciones (duplicaría gobierno). `VERSION_COMPLETA.md` sí puede subirse: es la referencia de detalle.

## 4. Verificación de la instalación (5 minutos)

1. Nueva conversación en el Project: «¿Qué sistema tienes instalado y qué reglas te gobiernan?» → debe citar el rol, «el pliego manda» y las reglas inviolables.
2. «Si te subo un PCAP y un PPT, ¿qué me darás primero?» → debe describir la extracción rápida de 6 puntos en orden.
3. «Redáctame ya una memoria para un pliego que te subiré luego» → debe negarse y explicar el orden de fases (RI-12).
4. Subir un expediente real y comprobar que la extracción rápida llega antes que todo y con referencias.

## 5. Instalación mínima (Projects muy limitados)

Instrucciones = `VERSION_CORTA.md` + Knowledge = prioridad 1 + `02_SKILLS/01`, `02`, `03`, `04`, `05` + `06_TEMPLATES/TPL_EXTRACCION_RAPIDA`, `TPL_RESUMEN_EXPEDIENTE`, `TPL_BASE_ECONOMICA`, `TPL_MEMORIA_TECNICA`, `TPL_RED_TEAM` + `PB_11`. El resto se pega en la conversación cuando haga falta.

## 6. Datos de la empresa (recomendado)

Crear y subir un documento propio «DATOS_EMPRESA.md» con: tarifas internas por perfil, equipo real (perfiles, titulaciones, dedicaciones), referencias acreditables con importes y certificados disponibles, certificaciones vigentes, política de margen mínimo. Reduce el 80 % de las preguntas del sistema. **Mantenerlo actualizado**: el sistema solo tratará como validado lo que conste ahí o confirme el usuario.

## 7. Mantenimiento

Altas/bajas de archivos → reflejar en `MANIFEST.json`, `FILE_INDEX.md` y `CHANGELOG.md`. Al incorporar memorias de referencia reales: abstraer patrones hacia `04_KNOWLEDGE`/`05_PLAYBOOKS` (RI-09: nunca subir memorias de clientes como plantilla literal con datos).
