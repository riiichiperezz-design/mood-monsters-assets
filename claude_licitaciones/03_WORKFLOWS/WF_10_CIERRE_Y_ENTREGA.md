# WF_10 — Validación formal, cierre y entrega

> **Propósito:** procedimiento de los estados 16-17: verificación formal final de la oferta y cierre ordenado del expediente.
> **Cuándo cargarlo:** con la oferta corregida, en la antesala de la presentación.
> **Cuándo no cargarlo:** en cualquier fase anterior.
> **Skills que lo utilizan:** RED_TEAM (pasada formal), ROUTER (cierre).
> **Palabras clave:** cierre, entrega, presentación, validación formal.
> **Dependencias:** WF_MASTER (E16-E17), CHK_PRESENTACION_FINAL.
> **Prioridad:** alta. **Coste de contexto:** bajo.
> **Resumen:** último control antes de presentar: verificación formal exhaustiva (documentos por sobre, formatos, límites, firmas electrónicas, DEUC/declaraciones, modelos oficiales, plataforma, plazo con margen técnico) y cierre del expediente con paquete final, recordatorios operativos y lecciones aprendidas opcionales. Incluye el protocolo de reapertura ante subsanaciones, aclaraciones de mesa o defensa de baja anormal.

---

## 1. Objetivo y estados cubiertos
Estados 16 (Validación formal) y 17 (Cierre).

## 2. Entrada
Versión corregida (E15) con registro de hallazgos; requisitos formales del PCAP.

## 3. Pasos — Estado 16 (validación formal)

1. **Composición por sobre/archivo electrónico:** cada documento exigido en su sobre exacto; nada cruzado (última pasada CHK_SOBRES).
2. **Formatos:** páginas, tipografía y tamaño, interlineado, anexos permitidos, idioma, límites de tamaño de archivo de la plataforma, formatos admitidos (PDF firmado, etc.).
3. **Documentación administrativa:** DEUC/declaración responsable, compromiso de adscripción, compromiso de UTE si procede, garantía provisional si se exige, modelos oficiales cumplimentados sin editar su estructura.
4. **Firmas:** quién firma (apoderamiento), firma electrónica válida, todas las páginas si se exige.
5. **Plataforma y plazo:** alta y credenciales operativas, requisitos técnicos probados, margen de al menos 24 h para incidencias; huella electrónica/registro si la plataforma lo emite.
6. Cumplimentar **CHK_PRESENTACION_FINAL**; cualquier fallo devuelve a E15.

## 4. Pasos — Estado 17 (cierre)

1. Paquete final: lista de archivos por sobre con su estado, versión y responsable de subida.
2. Recordatorios: fecha/hora límite (zona horaria), quién presenta, resguardo de presentación a conservar.
3. Lecciones aprendidas (opcional): qué funcionó, costes reales de preparación, huecos de capacidad detectados — alimenta futuros expedientes.
4. Archivo del expediente: análisis, base económica y decisiones quedan como referencia interna.

## 5. Protocolo de reapertura

- **Requerimiento de subsanación:** identificar qué se pide exactamente, plazo (habitualmente 3 días), responder solo lo requerido.
- **Justificación de baja anormal:** reabrir base económica (WF_06) para construir la justificación con costes reales; PROCUREMENT para el marco.
- **Aclaraciones de mesa o defensa oral:** preparar con la memoria y la matriz de criterios.

## 6. Salida
Checklist final limpio + paquete de entrega + cierre documentado.

## 7. Criterio de finalización
Oferta presentada (o lista para presentar) y expediente archivado.

## 8. Errores habituales
Dejar la subida a la última hora; firma de persona sin poder; PDF que excede el tamaño de la plataforma; modelo oficial «mejorado» que la mesa rechaza; no guardar el resguardo.

## 9. Conexiones
Fin del ciclo WF_MASTER; las reaperturas enlazan con WF_06 y PROCUREMENT según el caso.
