# TPL_RESUMEN_EXPEDIENTE — Formato del análisis completo

> **Propósito:** estructura del análisis completo del expediente (formato predeterminado del sistema).
> **Cuándo cargarlo:** estado 3 (análisis). **Cuándo no:** en otras fases.
> **Skills:** 01_EXPEDIENT_ANALYZER. **Prioridad:** alta. **Coste:** bajo.
> **Resumen:** esqueleto de las secciones 0-10 del formato predeterminado, alineado con las 13 secciones del análisis (VERSION_COMPLETA §2). Todo dato lleva referencia y etiqueta RI-10; la conclusión nunca decide.

---

## Formato

```markdown
# Análisis del expediente — [Objeto] (Exp. [número], [órgano])

# 0. Extracción rápida
[TPL_EXTRACCION_RAPIDA]

# 1. Resumen
[5-10 líneas: qué se contrata, importe (PBL/VE), plazo, cómo se gana, qué lo hace exigente]
- Datos básicos: tipo de contrato · CPV · procedimiento · lotes · lugar de ejecución · plataforma

# 2. Requisitos
| Requisito | Fuente | Tipo (adm./técnico/formal) | Implicación |
[Incluye: forma de presentación, estructura de sobres, límites formales de la memoria, subcontratación, condiciones especiales de ejecución, garantías, penalidades clave]

# 3. Solvencia
## 3.1 Económica  ## 3.2 Técnica
[Umbrales literales, medios de acreditación, alternativas (clasificación/medios externos); estado: acreditable/[PENDIENTE]/en riesgo]

# 4. Personal
[Perfiles exigidos con titulación/experiencia/dedicación; adscripción de medios; régimen de sustituciones; estado por perfil]

# 5. Costes potenciales
[Inventario por categorías (sin valorar si faltan tarifas): tareas y entregables del PPT contados; reuniones/talleres/viajes; materiales/licencias/tecnología; subcontratación]

# 6. Riesgos
[Los 13 de catálogo evaluados; desarrollados solo los presentes, con severidad]

# 7. Análisis económico
[PBL vs. alcance; fórmula de precio y valor del punto; zona de baja anormal; primera lectura de viabilidad — sin escenarios todavía si no hay tarifas]

# 8. Preguntas
[Cerradas, máx. 12, por criticidad; cada una con lo que desbloquea]

# 9. Conclusión operativa
[TPL_CONCLUSION_INTERNA — implicaciones y condiciones, SIN decisión de presentarse (RI-11)]

# 10. Siguiente paso
[Qué estado del workflow sigue y qué necesita del usuario]
```

## Reglas de uso

Referencia en cada dato · etiquetas RI-10 en todo lo no literal · contradicciones con doble cita (RI-19) · secciones sin contenido en el expediente se declaran («el pliego no regula X»), no se omiten.
