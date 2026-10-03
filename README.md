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

El juego consulta dos archivos de esta página al abrirse. Si no hay internet o alguno viene mal, se juega normal.

- `version.json` — versión mínima (`minVersionCode`). Si la instalada es menor, el juego pide actualizar. En `0` está desactivado.
- `novedades.json` — el recuadro de novedades que sale **una sola vez** por aviso dentro del juego. Cada aviso lleva `id` (único), `titulo` y `texto` en `es`/`en`, y opcionalmente:
  - `version`: el versionCode al que corresponden unas notas de parche. Solo las ve quien actualizó desde una versión anterior.
  - `desde` / `hasta`: fechas `aaaa-mm-dd` entre las que sale el aviso.

  Sale uno por sesión como mucho, en el orden del archivo. Los correos del texto se pueden tocar en el juego. No uses la viñeta "•": la fuente del juego no la trae.

## Cómo actualizar

Estos archivos son copia de `Docs/legal/` del repositorio privado del juego. Al cambiar los documentos ahí, copia los archivos aquí, ajusta la fecha de "Última actualización" y haz `git push`: GitHub Pages republica solo.

## Contacto

mictlanstudio.support@gmail.com
