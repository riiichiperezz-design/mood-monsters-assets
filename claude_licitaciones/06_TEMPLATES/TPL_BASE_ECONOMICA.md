# TPL_BASE_ECONOMICA — Estructura de la base económica

> **Propósito:** formato de la base económica con escenarios, márgenes, sensibilidades y advertencias.
> **Cuándo cargarlo:** estado 9 (base económica).
> **Skills:** 02_BUDGET_BUILDER. **Prioridad:** alta. **Coste:** bajo.
> **Resumen:** estructura completa: inventario valorado por categorías, tres escenarios, contraste con PBL y fórmula, sensibilidades, punto de equilibrio, advertencias obligatorias y cuadro de decisión para el usuario. Uso estrictamente interno: jamás se traslada a la memoria (RI-05).

---

## Formato

```markdown
# Base económica — [Objeto] (interna, no trasladar a la oferta)

## 1. Supuestos e hipótesis declaradas
[Lista: interpretación de volúmenes, tarifas usadas y su origen, [HIPÓTESIS] autorizadas]

## 2. Inventario valorado
| Partida | Origen (obligación) | Ud. | Cant. | Perfil/recurso | Tarifa | Coste | Etiqueta |
|---|---|---|---|---|---|---|---|
[categorías: personal por perfil · dirección/coordinación · producción · revisión · viajes/alojamiento/dietas · talleres/eventos · materiales/diseño/impresión · licencias/software/plataformas · compras · subcontratación]
[Tarifas ausentes: `[PENDIENTE: tarifa X]` visibles]

## 3. Escenarios
| Concepto | Mínimo | Probable | Conservador |
|---|---|---|---|
| Costes directos | | | |
| Gastos generales ([X] %) | | | |
| Contingencia ([X] %) | | | |
| **Coste total** | | | |
| Beneficio objetivo ([X] %) | | | |
| **Precio resultante (sin IVA)** | | | |
[Nota por escenario: qué supuestos cambian]

## 4. Contraste con el concurso
- PBL (sin IVA): [X] · ¿Cabe el escenario probable?: [sí/no, holgura]
- Fórmula de precio: tabla baja % → puntos → margen resultante
- Zona de baja anormal estimada: [X %] [ESTIMACIÓN]

## 5. Sensibilidades y punto de equilibrio
| Variación | Impacto en coste | Impacto en margen |
[±10-15 % horas · +1 viaje/taller mes · retraso 2 meses · perfil a contratar más caro]
- Punto de equilibrio: baja máxima con margen ≥ [objetivo] = [X %]

## 6. Advertencias
[OBLIGATORIA si margen probable < 10-15 % · partidas [PENDIENTE] críticas · riesgo de baja anormal · dependencias de hipótesis sensibles]

## 7. Cuadro de decisión (usuario)
| Opción | Implicaciones |
| Avanzar a oferta | |
| Ajustar (alcance/tarifas/equipo) | |
| Desestimar | |
[SIN recomendación de decisión — RI-11. Preguntas pendientes de E8 listadas.]
```
