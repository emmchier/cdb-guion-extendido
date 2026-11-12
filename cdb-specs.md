# CDB — Specs del proyecto

> **Claude: leé este archivo completo antes de tocar nada cada vez que retomamos el trabajo.**
> Para retomar en un chat nuevo, Emmanuel dice: *"Retomemos CDB, leé cdb-specs.md"*.

Última actualización de estos specs: 2026-11-12

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

1. Transcribir el texto fiel al manuscrito. **No detenerse en temas de ortografía:** corregir al pasar lo evidente (acentos, signos de apertura, errores claros), sin consultar a Emmanuel ni listar las correcciones. No cambiar palabras, estilo ni giros de Ariana (voseo, palabras inventadas, nombres propios); no reescribir, no completar frases cortadas, no "mejorar".
2. Lo que no se entiende o es ilegible: dejar `[...]` en ese lugar y seguir. No adivinar ni frenar la transcripción. Emmanuel revisa después el texto contra las imágenes y lo corrige él en el artefacto. (Las marcas `[?]` de tandas anteriores a esta regla quedan como están.)
3. Agregar el texto **al final** del artefacto, precedido por un párrafo marcador en negrita:
   `>>> NUEVO (tanda N) — sin ubicar >>>`
   Después proponerle a Emmanuel en qué capítulo va (ver sección 11) y moverlo ahí cuando lo confirme; al moverlo, borrar el marcador. Mover bloques, nunca retipearlos.
4. No modificar texto ya existente salvo que Emmanuel lo pida de forma explícita.
5. Después de agregar al artefacto, actualizar `cdb-guion-extendido.md` en la carpeta local **exportando el artefacto a Markdown** (nunca retipeando el texto a mano).
6. Al terminar, decir en el chat solo cuántos `[...]` quedaron, sin detallar correcciones de ortografía.

Convenciones del texto: título `# Ariana`, capítulos como encabezado de nivel 2 (`## Título`, sin número), cortes de escena dentro de un capítulo con línea horizontal (`---`; en el Google Doc, `* * *` centrado).

Reglas de ortografía y de `[...]` dadas por Emmanuel el 2026-11-11. Valen para texto transcripto de imágenes y para texto dictado o tipeado por él. El texto anterior no se corrige retroactivamente salvo que lo pida.

## 6. "Agregá esto a scenes"

Cuando Emmanuel dice *agregá "[FRASE]" a scenes*:

1. Agregar la frase textual a la lista de `cdb-scenes.md` (carpeta local), con la fecha.
2. Agregar la misma frase a la pestaña **Scenes** del artefacto.
3. No tocar el guion.

## 7. "Subí los cambios a github"

Emmanuel lo pide al terminar la jornada. Pasos, en orden:

1. Leer el Google Doc y traer al artefacto cualquier ajuste que Emmanuel haya hecho ahí (ver sección 8).
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
- **Ediciones de Emmanuel en el Google Doc:** Emmanuel puede editar el Google Doc a mano. Antes de cada sincronización y antes de cada subida a GitHub, leer el Google Doc y compararlo con el artefacto. Si hay diferencias que vienen de él:
    1. No pisarlas nunca en el Google Doc.
    2. Llevar cada ajuste al artefacto de Claude (cambiando solo las palabras que cambiaron).
    3. Actualizar `cdb-guion-extendido.md` exportando el artefacto.
    4. Recién entonces subir la nueva versión a GitHub.
    5. Avisar en el chat qué ajustes se trajeron del Google Doc.
- Si el mismo pasaje cambió en el Google Doc y en el artefacto de forma distinta, no elegir: preguntarle a Emmanuel cuál vale.
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
| 9 | 2026-11-11 | «—Porque me encanta el café.» (7 páginas: la presión, la cafetera y el aparato del Abo) |
| 10 | 2026-11-11 | «Se volvió ella misma su propio conejillo de indias.» (12 páginas: la flor de pinches, Cualajum, y pasaje en tercera persona sobre la app, la charla TED y el lector cuántico). La página inicial (pregunta sobre las manchas + Cualajum) se agregó después. |
| — | 2026-11-12 | Reordenamiento completo en 15 capítulos con título (sección 11). Se quitaron los marcadores de tanda 8, 9 y 10, el rótulo "CAPÍTULO 2" y una línea de corte que quedó reemplazada por un título. No se cambió ninguna palabra del texto. |

## 11. Estructura por capítulos (desde el 2026-11-12)

Orden y títulos puestos por Claude a pedido de Emmanuel: cronológico por la edad de Ariana, sin romper los pasajes que el texto encadena entre sí. Los títulos son provisorios; Emmanuel puede cambiarlos.

| # | Capítulo | Qué contiene | Edad / momento |
| --- | --- | --- | --- |
| 1 | El niño del sombrero rojo | Recuerdo inicial del niño y la nieve | Primer recuerdo |
| 2 | Mi nombre es Ariana | Presentación, las tías, la mácula | Presentación |
| 3 | Luces verdes | El supermercado, la patada ninja, "presión alta" | 7 años |
| 4 | Cosas que hablan de cosas | Campeonatos, la biblia de lectores | 10 años |
| 5 | La ferretería de Lamargue | La lámpara, el inventario, el deseo de un lector | 10 a 13 y medio |
| 6 | El regalo de Olina | El lector turquesa y los tokens | 11 años |
| 7 | Permítanme dudar | La sospecha de conspiración | "De más grande" |
| 8 | La presión | La cafetera y el aparato del Abo | 14 años |
| 9 | La tienda de ropa | La falda y el lector roto | Época en que muere el Abo |
| 10 | Cualajum y la flor de pinches | La broma de Oriana, la broma a Cualajum, el vivero | Contado a los 300 años; hechos de infancia |
| 11 | Señor Pinocchio | Carta a Pinocchio, la pared de códigos, luces azules | 14 años |
| 12 | Sueños de códigos | Sueños, el dolor en el pie, la crema | Adolescencia |
| 13 | Las bromas de Oriana | Apodos y bromas | Sin fecha |
| 14 | El radar | Tercera persona: la app, la charla TED, las fake news, el lector cuántico | 16 años en adelante |
| 15 | Conocerme | Reflexión final sobre los códigos y conocerse | 300 años |

Decisiones a revisar con Emmanuel: el capítulo 10 quedó después de la tienda de ropa porque empieza con "Pero no desesperé", que continúa esa escena, aunque los hechos de Cualajum son anteriores; el capítulo 14 está en tercera persona y el resto en primera.
