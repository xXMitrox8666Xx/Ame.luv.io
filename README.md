# Ame.luv.io

Página de una sola pantalla (tipo "historia"), pensada para verse en un teléfono, con 5 ventanas que se recorren tocando la pantalla o con botones. Todo el CSS y JS va embebido dentro de `index.html`, no hay archivos aparte.

## Archivos que necesitas subir al repo (todos en la raíz, mismo nivel)
- `index.html`
- `img-verde-2.png`
- `img-verde-4.jpg`
- `video-easter-egg.mp4`

Los nombres tienen que ser **exactamente esos**, tal cual como los llama el `<img>` / `<video>` dentro del HTML. GitHub Pages distingue mayúsculas de minúsculas, así que `Img-Verde-2.png` o `IMG-verde-2.png` no van a funcionar.

## Cómo funciona cada ventana
1. **Portada (negra)** — título "Espero te guste", un anillo dorado decorativo y el botón "Para ti Ame" (el único botón amarillo). Tocar en cualquier parte de la pantalla o el botón avanza.
2. **Imagen `img-verde-2.png`** — la foto de fondo cubre toda la pantalla con un velo oscuro abajo para que el texto se lea. Tocar la pantalla avanza (hay una flecha "toca para seguir" como pista).
3. **Luciérnagas** — fondo negro con puntitos morados (`#8717A9`) animados, aquí va la declaración larga. El botón "Ya casi termino" aparece solo, automáticamente, 5 segundos después de entrar — no se puede saltar antes tocando la pantalla.
4. **Imagen `img-verde-4.jpg`** — cierre del mensaje principal + "Te amo, América". En algún punto de la foto (posición aleatoria cada vez que carga) hay un círculo casi invisible que respira suavemente: es el botón escondido tipo easter egg. Tocar la pantalla en cualquier otro punto no hace nada — solo ese círculo lleva a la siguiente ventana.
5. **Video (easter egg)** — solo se llega encontrando el botón escondido de la ventana 4. Reproduce `video-easter-egg.mp4` en loop y silenciado por defecto (los navegadores móviles no dejan autoreproducir con sonido); hay un botón 🔇/🔊 arriba a la derecha para activar el audio, y tocar el video lo pausa o reanuda.

La barra de progreso de arriba solo cuenta las ventanas 1 a 4 — la ventana 5 queda fuera a propósito, porque es secreta.

## Cómo subirlo a GitHub Pages
1. Crea el repositorio `Ame.luv.io` en tu cuenta de GitHub (público, o privado si tienes GitHub Pro).
2. Sube `index.html`, `img-verde-2.png`, `img-verde-4.jpg` y `video-easter-egg.mp4` a la raíz del repositorio, rama `main`.
3. Ve a **Settings → Pages**, en "Source" elige la rama `main` y la carpeta `/ (root)`.
4. Espera uno o dos minutos y tu página quedará en:
   `https://<tu-usuario>.github.io/Ame.luv.io/`
5. Si más adelante configuras el dominio `ame.luv.io`, agrega un archivo `CNAME` (sin extensión) con ese dominio adentro, y apunta tu DNS con un registro CNAME hacia `<tu-usuario>.github.io`.

## Cosas a tener en cuenta
- El video de fondo (`video-easter-egg.mp4`) puede pesar bastante — si notas que carga lento en datos móviles, conviene comprimirlo (por ejemplo con HandBrake, apuntando a 720p y bitrate bajo) antes de subirlo, porque GitHub Pages no lo comprime por ti.
- Como todo el código vive en un solo archivo, cualquier ajuste de texto, color o tiempos lo haces directo dentro de `index.html`: los textos están en las etiquetas `<p class="texto-media">` / `<p class="texto-luz">`, los colores en las variables `:root` al inicio del `<style>`, y el retraso de 5 segundos del botón de luciérnagas está en el `setTimeout` dentro del `<script>`.
