# Sitio personal (Quarto)

Tarjeta de perfil tipo "link in bio": nombre centrado, descripción y
enlaces a redes sociales, con fondo de pantalla (por ahora una imagen
estática).

## Estructura
- `_quarto.yml` — configuración del proyecto y del sitio.
- `index.qmd` — contenido de la página (nombre, descripción, iconos).
- `styles.css` — estilos (fondo, tarjeta, iconos).
- `head.html` — carga Font Awesome (iconos) y la fuente Poppins.
- `background.jpg` — **agrégala tú**: la imagen de fondo (cualquier
  nombre sirve, solo actualiza la ruta en `styles.css`).

## Antes de publicar
En `index.qmd`, reemplaza:
- `TU-USUARIO` (LinkedIn) por tu usuario real de LinkedIn.
- `TU-USUARIO` (GitHub) por tu usuario real de GitHub.
- `tu-correo@ejemplo.com` por tu correo.

## Cómo previsualizar en local
```bash
quarto render index.qmd
```
(abre el `index.html` que se genera con doble clic, o arrástralo a tu
navegador)

## Cómo publicar en GitHub Pages
1. Crea un repositorio en GitHub (por ejemplo `tu-usuario.github.io`
   o cualquier otro nombre).
2. Renderiza el sitio:
   ```bash
   quarto render index.qmd
   ```
   Esto crea `index.html` y una carpeta `index_files/` junto a tus
   demás archivos.
3. Sube TODO a la rama `main`: `index.qmd`, `index.html`,
   `index_files/`, `styles.css`, `head.html`.
4. En GitHub → Settings → Pages → Source, elige la rama `main` y la
   carpeta `/ (root)` — no `/docs`.
5. Tu sitio quedará en `https://tu-usuario.github.io/nombre-repo/`.

Nota: normalmente `quarto render` (sin nombre de archivo) procesa
todo el proyecto y respeta `output-dir: docs` de `_quarto.yml`, pero
en esta máquina ese modo no genera ningún archivo por un motivo aún
sin identificar. Por eso usamos `quarto render index.qmd` (que sí
funciona) y publicamos desde la raíz en vez de `/docs`. Si en algún
momento el render de proyecto completo empieza a funcionar, se puede
volver a ese flujo.

## Fondo interactivo (a futuro)
Ahora mismo `.hero` en `styles.css` usa una imagen estática. Cuando
quieras algo interactivo (partículas, ondas, three.js, etc.), basta
con añadir un `<canvas>` o `<div>` detrás de `.card` dentro de
`index.qmd` y cargar la librería correspondiente en `head.html`.
