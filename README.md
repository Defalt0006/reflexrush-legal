# Reflex Rush — Documentos legales

Política de Privacidad y Términos de Uso de **Reflex Rush** (`com.mictlanstudio.reflexrush`), de Mictlan Studio.

Este repositorio existe únicamente para publicar esos documentos en una URL pública, como exige Google Play. **No contiene el código del juego.**

## Página publicada

https://defalt0006.github.io/reflexrush-legal/

| Documento | Enlace directo |
|---|---|
| Política de Privacidad (ES) | https://defalt0006.github.io/reflexrush-legal/#privacy-es |
| Privacy Policy (EN) | https://defalt0006.github.io/reflexrush-legal/#privacy-en |
| Términos de Uso (ES) | https://defalt0006.github.io/reflexrush-legal/#terms-es |
| Terms of Use (EN) | https://defalt0006.github.io/reflexrush-legal/#terms-en |
| Eliminar mis datos (ES) | https://defalt0006.github.io/reflexrush-legal/#delete-es |
| Delete my data (EN) | https://defalt0006.github.io/reflexrush-legal/#delete-en |

La página detecta el idioma del navegador y permite cambiarlo manualmente.

## Archivos

- `index.html` — la página publicada (los seis documentos en uno, sin dependencias externas).
- `PrivacyPolicy.md` / `PrivacyPolicy.en.md` — texto completo de la política.
- `TermsOfUse.md` / `TermsOfUse.en.md` — texto completo de los términos.
- `DataDeletion.md` / `DataDeletion.en.md` — procedimiento de eliminación de cuenta y datos.

## Archivos que lee el juego

El juego consulta estos archivos de esta página al abrirse. Si no hay internet o alguno viene mal, se juega normal.

- `version.json` — versión mínima (`minVersionCode`). Si la instalada es menor, el juego pide actualizar. En `0` está desactivado.
- `novedades.json` — el recuadro de novedades que sale **una sola vez** por aviso dentro del juego. Cada aviso lleva `id` (único), `titulo` y `texto` en `es`/`en`, y opcionalmente:
  - `version`: el versionCode al que corresponden unas notas de parche. Solo las ve quien actualizó desde una versión anterior.
  - `desde` / `hasta`: fechas `aaaa-mm-dd` entre las que sale el aviso.

  Sale uno por sesión como mucho, en el orden del archivo. Los correos del texto se pueden tocar en el juego. No uses la viñeta "•": la fuente del juego no la trae.
- `recompensas.json` — recompensas para testers. Cada entrada lleva una `huella` (SHA-256 de `"reflexrush-tester:"` + el ID del jugador; nunca el ID) y sus `premios`: `circulo`, `cuadrado`, `triangulo`, `fondo`. El juego calcula la huella de su propio ID, la busca, entrega lo que falte y da las gracias una sola vez.
- `buzon.json` — el buzón de testers dentro del juego (desde la versión 1.3.0). `activo` lo enciende o lo apaga: apagado, el botón Buzón y la tarjeta que pregunta "¿Cómo va el juego?" no salen. `formulario` es la dirección `.../formResponse` del Formulario de Google donde caen los mensajes (el juego solo envía a direcciones de `https://docs.google.com/forms/`). `campos` dice qué pregunta del formulario (`entry.NNN`) recibe cada dato: `id`, `version`, `tipo`, `mensaje`, `idioma` y `dispositivo`. Si se borra o se vuelve a crear una pregunta del formulario, su número cambia y hay que actualizarlo aquí.
- `eventos.json` — los eventos del juego (desde la versión 1.3.0). Cada evento lleva:
  - `id` (único), `desde` y `hasta`: fechas `aaaa-mm-dd`, de día completo y con la hora del teléfono.
  - `boosts`: `false` es partida directa sin boosts; `true` pasa por la pantalla de antes de jugar.
  - `titulo` y `texto` en `es`/`en`.
  - `vidas`: con cuántas veladoras empieza la partida (si falta, 3).
  - `caminos`: el recorrido, en orden, que se juega en una sola partida y sin reloj. Cada camino lleva:
    - `id`;
    - `objeto`: lo que aparece dentro de las figuras (`veladora`, `cempasuchil` o `pan`);
    - `figuras`: cuántas hay que tocar;
    - `segundos`: cuánto dura cada figura antes de irse y apagar una veladora;
    - `skin`: lo que se gana al completarlo por primera vez (un id del catálogo que ya exista en el juego);
    - `titulo` en `es`/`en`.

    Al terminar el último camino la partida sigue, cada vez más rápida, hasta que se apagan las veladoras.
  - `fondo`: el id del fondo que se gana al completar todo el recorrido.
  - Opcionales: `acento` y `panel` (`#RRGGBB`), los colores de sus ventanas.

  Fuera de fechas o sin archivo, el botón de Eventos dice «Próximamente», y la pestaña de Eventos de la tabla de puntajes se queda cerrada. Cambiar fechas, textos o números no necesita sacar build; una skin u objeto nuevo sí.

## Cómo actualizar

Estos archivos son copia de `Docs/legal/` del repositorio privado del juego. Al cambiar los documentos ahí, copia los archivos aquí, ajusta la fecha de "Última actualización" y haz `git push`: GitHub Pages republica solo.

## Contacto

mictlanstudio.support@gmail.com
