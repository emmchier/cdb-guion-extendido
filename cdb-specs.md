# CDB — Specs del proyecto

> **Claude: leé este archivo completo antes de tocar nada cada vez que retomamos el trabajo.**
> Para retomar en un chat nuevo, Emmanuel dice: *"Retomemos CDB, leé cdb-specs.md"*.

Última actualización de estos specs: 2026-11-11

## 1. Qué es el proyecto

Digitalización del guion extendido del libro **CDB** (historia de Ariana y su código de barras en el pie izquierdo). Emmanuel lo escribió a mano en cuadernillos. Pasa fotos de las páginas y Claude las transcribe y las agrega al texto.

## 2. Destinos (dónde vive cada cosa)

| Destino | Ubicación | Rol |
| --- | --- | --- |
| Artefacto de Claude | Doc "Ariana": https://claude.ai/artifact/HH5EmiRow84EM2itfTAJkh | **Fuente de verdad.** Acá se trabaja el texto. |
| Carpeta local | `~/Documents/CDB-libro-final/` (Mac de Emmanuel) | Copia en .md de todo el proyecto |
| GitHub | https://github.com/emmchier/cdb-guion-extendido (rama `main`) | Historial de versiones |
| Google Doc | https://docs.google.com/document/d/1mzcBxUibVCwZ03pzMYfAlEVoiz9BkVXCBWy0HRn1PLE/edit | Espejo del guion; Emmanuel lo refina ahí en el futuro |

## 3. Archivos

| Archivo | Contenido |
| --- | --- |
| `cdb-guion-extendido.md` | Texto completo del guion, idéntico al artefacto |
| `cdb-specs.md` | Este archivo: reglas y flujo de trabajo |
| `cdb-scenes.md` | Lista de frases candidatas a escenas para ilustrar |

Los tres archivos van en la carpeta local y en GitHub. En el artefacto, las escenas viven en la pestaña **Scenes**.

## 4. Al retomar el trabajo

1. Leer este archivo.
2. Leer el artefacto "Ariana" completo (puede tener ediciones manuales de Emmanuel desde la última vez).
3. Ubicar el último marcador `>>> NUEVO (tanda N)` para saber por dónde vamos.
4. Si el artefacto difiere de `cdb-guion-extendido.md`, gana el artefacto: no pisar nunca ediciones de Emmanuel.

## 5. Transcribir una tanda nueva

Emmanuel pasa imágenes de páginas manuscritas. Para cada tanda:

1. Transcribir el texto **tal cual está escrito**. No corregir estilo, no reescribir, no completar frases cortadas, no "mejorar".
2. Palabra dudosa o ilegible: escribir la mejor lectura seguida de `[?]`. No inventar.
3. Agregar el texto **al final** del artefacto, precedido por un párrafo marcador en negrita:
   `>>> NUEVO (tanda N) — sigue desde «…últimas palabras de la tanda anterior» >>>`
4. No modificar texto ya existente salvo que Emmanuel lo pida de forma explícita.
5. Después de agregar al artefacto, actualizar `cdb-guion-extendido.md` en la carpeta local **exportando el artefacto a Markdown** (nunca retipeando el texto a mano).
6. Avisar en el chat qué palabras quedaron con `[?]`.

Convenciones ya presentes en el texto: título `# Ariana`, capítulos como párrafo en negrita (`**CAPÍTULO 2**`), cortes de escena con línea horizontal (`---`).

**A confirmar con Emmanuel** (no estaba documentado al crear este archivo): si la ortografía y los acentos se corrigen al transcribir o se dejan como en el manuscrito. Hasta que lo confirme, dejar como en el manuscrito.

## 6. "Agregá esto a scenes"

Cuando Emmanuel dice *agregá "[FRASE]" a scenes*:

1. Agregar la frase textual a la lista de `cdb-scenes.md` (carpeta local), con la fecha.
2. Agregar la misma frase a la pestaña **Scenes** del artefacto.
3. No tocar el guion.

## 7. "Subí los cambios a github"

Emmanuel lo pide al terminar la jornada. Pasos, en orden:

1. Exportar el artefacto a Markdown y actualizar `cdb-guion-extendido.md` en la carpeta local.
2. Verificar que `cdb-scenes.md` y `cdb-specs.md` locales estén al día.
3. Copiar los tres archivos al repo y hacer commit en `main` con la fecha de la versión en el mensaje:
   `Versión AAAA-MM-DD — resumen corto de lo agregado`
   (si hay más de una subida el mismo día: `Versión AAAA-MM-DD (2) — …`)
4. `git push` a `origin main`.
5. Actualizar el Google Doc con el texto actual del guion (ver sección 8).
6. Confirmar en el chat: commit subido, y si el Google Doc quedó actualizado o no.

## 8. Google Doc — cómo se sincroniza y límites

- **Estado al 2026-11-11: conectado.** El conector de Google Docs está activo y el doc tiene el guion completo hasta la tanda 8 (título como Encabezado 1, `CAPÍTULO 2` y el marcador de tanda en negrita, cortes de escena como `* * *` centrado).
- **No existe espejo en tiempo real** entre el artefacto y Google Docs. Claude copia el texto al Google Doc cuando trabaja: al cerrar cada tanda y en cada "subí los cambios a github".
- **Cómo sincronizar una tanda nueva:** agregar al final del Google Doc solo los párrafos nuevos (marcador en negrita + texto), sin tocar lo anterior. No borrar y reescribir el doc entero.
- **Cómo sincronizar una edición de texto existente:** cambiar en el Google Doc solo las palabras que cambiaron en el artefacto.
- **Verificación obligatoria:** después de escribir, leer el Google Doc y comparar el largo de cada párrafo contra `cdb-guion-extendido.md`. Si algo no coincide, corregir antes de dar por terminado.
- La sincronización va en un solo sentido: artefacto → Google Doc. Si Emmanuel edita el Google Doc directamente, tiene que avisar antes de la próxima sincronización.
- Cuando Emmanuel pase a refinar el texto en Google Docs, hay que cortar esta sincronización y actualizar estos specs.
- **Scenes en Google Docs:** todavía no hay pestaña. Crearla (pestaña "Scenes") cuando se agregue la primera frase.
- Si el conector de Google Docs no está disponible en el chat, avisar a Emmanuel y seguir con el resto; no reemplazarlo por otro archivo.

## 9. Reglas generales

- El texto es de Emmanuel: Claude transcribe, no edita.
- Nunca borrar ni reescribir contenido existente sin pedido explícito.
- Mantener este archivo al día: si cambia el flujo o Emmanuel da una regla nueva, actualizar acá y subirlo en la próxima versión.

## 10. Registro de tandas

| Tanda | Fecha | Hasta dónde llega |
| --- | --- | --- |
| 1–8 | antes del 2026-11-11 | «…si este lector no me sabe descubrir algo nuevo, no lo pienso seguir usando.» |
