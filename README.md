# Herramienta de licitaciones turísticas (workspace de Claude Code)

Herramienta interna para **analizar y preparar licitaciones públicas españolas del sector turístico**. Sueltas los pliegos en una carpeta y, con comandos, se ejecuta todo el flujo (análisis → solvencia → economía → memoria → red team → cierre), guardando cada salida como archivo.

Resuelve el límite de los Claude Projects: la base de conocimiento (97 módulos en `claude_licitaciones/`) **se lee bajo demanda desde disco**, nunca toda a la vez.

## Cómo se usa (flujo típico)

1. **Abre este repositorio en Claude Code** (terminal, app de escritorio o claude.ai/code).
2. **(Una vez)** Rellena `empresa/DATOS_EMPRESA.md` con tus tarifas, equipo, referencias y política de margen. Evita el 80 % de las preguntas.
3. **Nuevo expediente:** escribe `/nuevo-expediente`. Se crea `expedientes/<NOMBRE>/`.
4. **Copia los PDF del pliego** (PCAP, PPT, anexos, modelos) en `expedientes/<NOMBRE>/00_pliegos/`.
5. **Ejecuta las fases** (o pide "haz el ciclo completo" y se irá parando donde debas decidir):

   | Comando | Qué hace | Genera |
   |---|---|---|
   | `/analizar-expediente` | extracción rápida + análisis completo | `01_analisis/analisis.md` |
   | `/validar-solvencia` | solvencia y personal vs. tu capacidad | `01_analisis/solvencia.md` |
   | `/estrategia-puntuacion` | matriz de criterios y sobres | `01_analisis/criterios.md` |
   | `/base-economica` | costes, escenarios y márgenes | `02_economico/base_economica.md` |
   | *(decides tú: avanzar / ajustar / desestimar)* | | |
   | `/redactar-memoria` | índice + memoria técnica | `03_memoria/memoria.md` |
   | `/red-team` | revisión adversarial | `04_revision/red_team.md` |
   | `/cierre-presentacion` | verificación formal final | `04_revision/checklist_final.md` |

También puedes pedir cosas sueltas en lenguaje natural ("hazme el Gantt", "¿es subsanable esto?", "pule el apartado 4"): el sistema carga solo lo necesario.

## Lo que la herramienta NO hace (por diseño)

- **No decide** si te presentas: te da implicaciones y riesgos; la decisión es tuya.
- **No inventa** requisitos, experiencia, personal ni tarifas: pregunta o deja variables abiertas.
- **No mezcla sobres** ni optimiza puntuación infringiendo el pliego.
- **No sustituye** el asesoramiento jurídico formal.

Las 20 reglas completas están en `claude_licitaciones/01_PROJECT_INSTRUCTIONS/REGLAS_INVIOLABLES.md`.

## Estructura del repositorio

```
CLAUDE.md                     # gobierno del workspace (se lee siempre)
.claude/skills/               # los 8 comandos (skills de Claude Code)
empresa/DATOS_EMPRESA.md      # tus datos (fuente de verdad; rellénalo)
expedientes/                  # tu trabajo (un subdirectorio por licitación)
  _PLANTILLA/                 # plantilla que copia /nuevo-expediente
claude_licitaciones/          # base de conocimiento (97 módulos, lectura selectiva)
```

## Privacidad

Por defecto, `.gitignore` **no versiona** los expedientes reales (pliegos y economía interna): quedan solo en tu máquina. Si quieres respaldar uno, fuérzalo con `git add -f`. Nunca subas `DATOS_EMPRESA.md` ni la carpeta `02_economico/` a ningún sitio público ni los incluyas en una oferta.

## Detalle del sistema

Arquitectura, instalación alternativa en Claude Projects y validación: `claude_licitaciones/00_README/` y `claude_licitaciones/09_BUILD/`.
