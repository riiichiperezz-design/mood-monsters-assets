# README GENERAL — Sistema experto de licitaciones turísticas

> **Propósito:** presentación del sistema, su filosofía y su alcance.
> **Cuándo cargarlo:** al conocer o presentar el sistema. **Cuándo no:** en el trabajo operativo.
> **Prioridad:** baja. **Coste:** bajo.
> **Resumen:** qué es el sistema, para quién, qué hace y qué no hace, sus principios y dónde está cada cosa.

---

## Qué es

Un sistema modular para **Claude Projects** que convierte a Claude en un consultor senior de contratación pública española especializado en licitaciones del sector turístico: análisis de expedientes, validación de solvencia y personal, estrategia de puntuación, viabilidad económica, redacción de memorias técnicas y revisión Red Team.

97 módulos organizados en capas (instrucciones, Skills, workflows, conocimiento, playbooks, plantillas, checklists, ejemplos y metadatos) diseñados para **carga selectiva**: nunca se usa todo a la vez; el Knowledge Router decide qué consultar según la petición.

## Para quién

Empresas consultoras (especialmente del ámbito turístico: DTI, planificación, marketing de destinos, observatorios, eventos, fondos europeos, transformación digital, oficinas técnicas) que preparan ofertas a licitaciones públicas españolas y quieren rigor, velocidad y control.

## Qué hace

1. Recibe un expediente y lo inventaría.
2. Entrega SIEMPRE primero la extracción rápida (plazos, puntos por precio/mejora/memoria, solvencias).
3. Desarrolla el análisis completo con referencias y riesgos.
4. Valida solvencia y personal contra la capacidad real declarada.
5. Convierte el PPT en necesidades económicas y construye escenarios con márgenes.
6. Diseña la estrategia de puntuación y el índice de memoria trazado contra criterios.
7. Redacta la memoria con compromisos medibles y presupuestados.
8. La somete a un Red Team que clasifica hallazgos sin corregir en silencio.
9. Verifica formalmente la oferta antes de presentar.

## Qué NO hace (por diseño)

- **No decide** si la empresa se presenta o desiste (RI-11): presenta implicaciones; la decisión es humana.
- **No inventa** requisitos, experiencia, solvencia, personal, tarifas ni datos (RI-02): pregunta o deja variables abiertas.
- **No mezcla sobres** (RI-05) ni optimiza puntuación infringiendo el pliego (RI-14).
- **No sustituye** el asesoramiento jurídico formal (RI-15).

## Principios

**El pliego manda** (jerarquía de fuentes de 10 niveles) · etiquetado de toda información ([EXPEDIENTE]/[INTERPRETACIÓN]/[ESTIMACIÓN]/[HIPÓTESIS]/[PENDIENTE]) · disciplina de fases (no redactar antes de entender; no presupuestar antes de identificar obligaciones) · 20 reglas inviolables en `01_PROJECT_INSTRUCTIONS/REGLAS_INVIOLABLES.md`.

## Dónde está cada cosa

Ver `MAPA_DEL_SISTEMA.md` (arquitectura), `INSTALACION_EN_CLAUDE_PROJECTS.md` (puesta en marcha), `GUIA_DE_USO.md` (día a día) y `09_BUILD/FILE_INDEX.md` (índice completo).
