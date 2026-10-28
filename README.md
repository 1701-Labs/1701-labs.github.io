# 1701 Labs — sitio web

> Un humano. Una IA. Contra el mundo.

Sitio oficial de **1701 Labs**, estudio independiente de videojuegos y software fundado por Ahiram1701 en Monterrey, MX.

Es un sitio estático (HTML + CSS, sin build). Se publica gratis con GitHub Pages en `https://1701-labs.github.io`.

## Cómo publicarlo (gratis)

1. **Crea la organización.** En GitHub ve a tu foto → *Your organizations* → *New organization* → plan **Free**. Nombre: `1701-Labs` (ya la tienes: https://github.com/1701-Labs).
2. **Crea el repositorio.** Dentro de la organización: *New repository*. Nombre exacto: `1701-labs.github.io` (todo en minúsculas). Público. Sin README.
3. **Sube los archivos.** En el repo vacío: *uploading an existing file* → arrastra `index.html`, `favicon.svg`, `og-image.png`, `og-image.svg` y este `README.md` → *Commit changes*.
4. **Activa Pages.** *Settings* → *Pages* → *Source: Deploy from a branch* → rama `main`, carpeta `/ (root)` → *Save*.
5. Espera 1–2 minutos y abre **https://1701-labs.github.io**.

## Qué editar en `index.html`

Las secciones son: **01 Juegos · 02 Apps · 03 Agentes IA · 04 Bots · 05 Para creadores**.

- **Agregar un proyecto:** copia una tarjeta `<a class="card">` (o una fila `<a class="lab-row">` en Bots), cambia el `href`, el nombre y el texto. Ponle a la descripción un `data-i18n="p.nombre"` nuevo y agrega esa clave en **los dos** idiomas del objeto `I18N` (al final del archivo, bloque `es` y bloque `en`). Sube en 1 el número de `PROYECTOS` en el hero (`data-count`) y agrégalo al `ItemList` del JSON-LD en el `<head>`.
- **Textos / idiomas:** el HTML está en español. La versión en inglés vive en `I18N.en`. Si cambias un texto en el HTML, cámbialo también en `I18N.es` y en `I18N.en`.
- **Etiqueta del enlace:** las apps que se usan en el navegador muestran `ABRIR`; las que solo tienen código muestran `GITHUB`.
- **Correo:** busca `CAMBIA ESTE CORREO`. Cámbialo también en el JSON-LD.
- **Redes:** busca `Agrega tus redes` y quita los comentarios `<!-- -->` cuando abras cada cuenta.
- **Color de acento:** en `:root`, cambia `--accent` (opciones: `#2EF2D6` cian, `#B6F23A` verde, `#FF5E3A` naranja, `#8C7CFF` violeta). Cambia también el color del `01` en `favicon.svg` y en `og-image.svg`.
- **Imagen para redes (`og-image.png`):** es lo que aparece al compartir el link en X, WhatsApp, etc. Si editas `og-image.svg`, regenera el PNG (Windows, PowerShell, en esta carpeta):

  ```powershell
  & "C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe" --headless=new --hide-scrollbars --window-size=1200,630 --screenshot="$PWD\og-image.png" "file:///$($PWD -replace '\\','/')/og-image.svg"
  ```

## Cuando tengas dominio propio

1. *Settings* → *Pages* → *Custom domain* → `1701labs.com` → *Save*.
2. En tu registrador, crea los registros DNS que indica GitHub (4 registros `A` para el dominio raíz y un `CNAME` de `www` a `1701-labs.github.io`).
3. Activa *Enforce HTTPS*.
4. En `index.html` reemplaza `https://1701-labs.github.io/` por tu dominio en `og:url`, `og:image`, `canonical` y el JSON-LD.

---

© 1701 Labs · Built by Ahiram1701 + IA
