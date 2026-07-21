# WF_09 — Revisión de cobertura, Red Team y correcciones

> **Propósito:** procedimiento de los estados 13-15: verificar cobertura de criterios, ejecutar la revisión adversarial y aplicar las correcciones aprobadas.
> **Cuándo cargarlo:** con borrador completo (o apartado terminado) listo para revisión.
> **Cuándo no cargarlo:** durante la redacción en curso o antes de existir borrador.
> **Skills que lo utilizan:** SCORING (E13), RED_TEAM (E14), MEMORY + EDITORIAL (E15).
> **Palabras clave:** revisión, red team, cobertura, correcciones.
> **Dependencias:** WF_MASTER (E13-E15), K-14, TPL_RED_TEAM, CHK_RED_TEAM, CHK_SOBRES.
> **Prioridad:** alta. **Coste de contexto:** bajo (el coste alto es releer el borrador).
> **Resumen:** cierra el ciclo de calidad en tres pasos encadenados: (1) revisión de cobertura contra la matriz de criterios, con huecos corregidos antes de nada; (2) Red Team completo de 8 pasadas con hallazgos clasificados y veredicto, sin corregir nada en silencio; (3) circuito de correcciones donde el usuario decide sobre cada hallazgo crítico/alto, MEMORY aplica los cambios de fondo, EDITORIAL los de estilo y se re-verifica lo corregido sin introducir regresiones.

---

## 1. Objetivo y estados cubiertos
Estados 13 (Cobertura), 14 (Red Team) y 15 (Correcciones).

## 2. Entrada
Borrador completo (E12); matriz de criterios; base económica; límites formales.

## 3. Pasos — Estado 13 (cobertura)

1. Contraste apartado↔criterio con la matriz: cada criterio y subcriterio tiene contenido proporcional a sus puntos.
2. Detectar: criterios sin cubrir, cubiertos de pasada, o cubiertos en el apartado equivocado (el evaluador puntúa por criterio, no por lectura completa).
3. Corregir huecos de cobertura **antes** del Red Team (evita ruido en la revisión).

## 4. Pasos — Estado 14 (Red Team)

1. Ejecutar las 8 pasadas de RED_TEAM §9 (formal, cumplimiento/sobres, evaluador, coherencia, económica, veracidad, editorial, clasificación).
2. Emitir TPL_RED_TEAM: hallazgos con ID, ubicación, evidencia, severidad (crítico/alto/medio/bajo/editorial), impacto y propuesta.
3. Veredicto explícito: «No presentar sin resolver los críticos C-01 y C-02» o «Sin hallazgos bloqueantes».
4. **Nada se corrige en esta fase** (RED_TEAM §3): el informe va al usuario.

## 5. Pasos — Estado 15 (correcciones)

1. El usuario decide sobre cada hallazgo crítico y alto (corregir / asumir expresamente); medios y bajos pueden delegarse.
2. MEMORY aplica las correcciones de fondo; EDITORIAL las de estilo (con sus invariantes).
3. **Re-verificación dirigida:** cada hallazgo corregido se comprueba; vigilar regresiones (páginas, sobres, coherencia).
4. Registro final: hallazgo → decisión → estado (resuelto/asumido).

## 6. Salida
Informe de cobertura → informe Red Team con veredicto → versión corregida + registro de hallazgos.

## 7. Bloqueos
Críticos sin resolver impiden pasar a E16; falta de matriz o base económica degrada el alcance del Red Team (se declara).

## 8. Criterio de finalización
Críticos resueltos; altos resueltos o asumidos por escrito del usuario; registro completo.

## 9. Errores habituales
Red Team hecho por el propio redactor sin cambiar de rol; corregir «de paso» cosas no señaladas (regresiones); pulir estilo antes de resolver fondo; no volver a contar páginas tras corregir.

## 10. Conexiones
Desemboca en WF_10 (validación formal y cierre). Un cambio de alcance detectado aquí puede reabrir estados anteriores vía WF_MASTER.
