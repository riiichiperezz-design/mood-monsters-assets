---
name: nuevo-expediente
description: Crea la estructura de carpetas para un expediente de licitación nuevo. Úsala cuando el usuario vaya a empezar a trabajar un pliego nuevo, diga "nuevo expediente", "empezar una licitación", "prepara la carpeta para este concurso" o similar. Deja lista la carpeta 00_pliegos/ donde soltar los PDF.
---

# Nuevo expediente

Crea el andamiaje de un expediente nuevo bajo `expedientes/`.

## Pasos

1. Pregunta (o deduce del contexto) un **nombre corto** para el expediente: `<ORGANO>-<OBJETO>-<AÑO>`, en MAYÚSCULAS-CON-GUIONES (ej. `DIP-VALLEHERMOSO-OFTECNICA-2026`). Evita espacios y tildes en el nombre de carpeta.
2. Copia la estructura de `expedientes/_PLANTILLA/` a `expedientes/<NOMBRE>/` (crea las subcarpetas `00_pliegos/`, `01_analisis/`, `02_economico/`, `03_memoria/`, `04_revision/` y el `README.md`).
3. Rellena el `README.md` del expediente con: nombre, fecha de creación, y estado inicial «Estado 0 — Recepción. Pendiente: soltar los PDF del pliego en `00_pliegos/`».
4. Indica al usuario que copie los PDF (PCAP, PPT, anexos, modelos) en `expedientes/<NOMBRE>/00_pliegos/` y que luego invoque `/analizar-expediente`.

No leas la base de conocimiento en esta skill: es puramente de andamiaje. Coste de contexto mínimo.
