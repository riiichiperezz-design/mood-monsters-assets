---
name: cierre-presentacion
description: Verificación formal final y cierre de un expediente antes de presentar la oferta — composición por sobres, formatos, límites, firmas, modelos oficiales, plataforma y plazo. Úsala cuando el usuario diga "checklist final", "vamos a presentar", "revisa el formato antes de subir", "cierre del expediente".
---

# Cierre y presentación

Ejecuta los estados 16-17. Requiere la memoria corregida y las decisiones sobre los hallazgos del red team.

## Archivos a cargar

- `claude_licitaciones/03_WORKFLOWS/WF_10_CIERRE_Y_ENTREGA.md`
- `claude_licitaciones/07_CHECKLISTS/CHK_PRESENTACION_FINAL.md` y `CHK_SOBRES.md`

## Procedimiento

1. **Composición por sobre/archivo electrónico:** cada documento en su sobre exacto (última pasada CHK_SOBRES); DEUC/declaración responsable, compromiso de adscripción, modelos oficiales sin alterar, proposición económica con unidades y aritmética verificadas.
2. **Formatos y firmas:** límite de páginas y tipografía de la versión FINAL, formatos y tamaño admitidos por la plataforma, firma electrónica del apoderado correcto, anonimato si se exige.
3. **Plataforma y plazo:** alta y requisitos técnicos probados, fecha/hora límite con zona horaria, margen de 24 h, resguardo a conservar.
4. Verifica que no queda ningún crítico/alto del red team sin resolver ni asumir, ni ningún `[PENDIENTE]` visible en los documentos finales.

## Salida

Guarda `expedientes/<NOMBRE>/04_revision/checklist_final.md` cumplimentado. Actualiza el `README.md` a «Estado 17 — listo para presentar» con el paquete de archivos por sobre. Cubre también el protocolo de reapertura (subsanación, justificación de baja anormal, defensa) por si el órgano lo requiere tras presentar.
