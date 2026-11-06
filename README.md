# Página legal de Kiri Arcade

Política de privacidad y condiciones del servicio de la app como páginas web
estáticas, sin JavaScript, sin recursos externos y sin rastreadores. Google Play
exige una URL pública para la política.

> **Aviso:** esto no es asesoría legal. El texto es un borrador escrito a partir
> del código de la app. Haz que alguien cualificado lo revise antes de publicarlo.

## Archivos

- `index.html`: enlaces a los dos documentos en los dos idiomas.
- `privacy-es.html` y `privacy-en.html`: la política.
- `terms-es.html` y `terms-en.html`: las condiciones del servicio.
- `styles.css`: colores del tema Suave.

## 1. Completar los textos

Haz estos cambios en las cuatro páginas (`privacy-*.html` y `terms-*.html`):

1. Sustituye `clusterkiri@gmail.com`, `Kiri Cluster`, `Venezuela` y `[FECHA]`.
2. Comprueba cada nota `VERIFICAR` y borra la nota.
3. Tras la revisión, borra la frase que dice que el documento es un borrador
   (la primera, bajo el título).

Haz los mismos cambios en `docs/store/privacy-policy.md` y
`docs/store/terms-of-service.md`, para que las versiones sigan iguales. Si un
documento cambia más adelante, actualiza también sus páginas y la fecha.

## 2. Comprobar

Desde la raíz de este proyecto:

```
npm run legal:check
```

Falla si falta alguna página, y lista archivo y línea mientras quede algo de lo
anterior. También falla si el texto de una página difiere del borrador en
`docs/store/` (solo esa comparación: `npm run legal:parity`; ignora el formato y
la nota interna). No publiques hasta que pase. Este README queda fuera de la
comprobación porque nombra los marcadores a propósito.

## 3. Publicar en GitHub Pages

El correo y el nombre de desarrollador quedarán públicos. El repositorio también muestra
el correo del autor de cada commit: revisa cuál usas, porque sigue visible en
el historial.

1. En GitHub, crea un repositorio **público** aparte, por ejemplo
   `kiri-arcade-legal`. No uses el repositorio de la app.
2. Copia en la raíz de ese repositorio `index.html`, `privacy-es.html`,
   `privacy-en.html`, `terms-es.html`, `terms-en.html` y `styles.css`. Este
   README no hace falta.
3. Haz commit y push a la rama `main`.
4. En el repositorio, ve a **Settings > Pages**. En "Build and deployment",
   elige **Deploy from a branch**, rama **main**, carpeta **/ (root)**, y pulsa
   **Save**.
5. Espera unos minutos y abre la URL que muestra esa pantalla.

## 4. La URL resultante

```
https://<usuario>.github.io/<repositorio>/
https://<usuario>.github.io/<repositorio>/privacy-es.html
https://<usuario>.github.io/<repositorio>/privacy-en.html
https://<usuario>.github.io/<repositorio>/terms-es.html
https://<usuario>.github.io/<repositorio>/terms-en.html
```

Abre las cinco URL en el móvil, sin iniciar sesión, y comprueba que cargan por
`https://`.

Como URL de cada documento, usa la página directa del idioma principal de tu
ficha de Play, no el índice: así quien revise llega directo al texto. Cada
página enlaza al otro idioma.

## 5. Copiar las URL

**En la app:** pega la de la política en `PRIVACY_POLICY_URL` y la de las
condiciones en `TERMS_URL`, en `src/core/support/support.config.ts`. Tienen que
empezar por `https://`, o `build:live` falla. Vuelve a generar la app y comprueba
los enlaces en Ajustes > Ayuda y datos.

**En Play Console:** pega la de la política en **Contenido de la app > Política
de privacidad**. La de las condiciones se usa al pasar a comerciante
(`docs/store/release-checklist.md`, paso 9).
