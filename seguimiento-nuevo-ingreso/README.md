# Seguimiento a Ejecutivos de Nuevo Ingreso · QiORA Telecom

Tablero estático (un solo `index.html`, sin instalaciones) que lee en vivo la hoja **SEGUIMIENTO** de Google Sheets.

## Publicar en GitHub Pages
1. Crea un repositorio en tu GitHub y sube **todo el contenido de esta carpeta** (incluida `.github/` y `datos/`).
2. En el repositorio: **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)` → Save**.
3. En un par de minutos el tablero queda en `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/`.

## Actualización automática
- Al abrir la página, cada 5 minutos y con el botón **Actualizar**, el tablero vuelve a leer Google Sheets.
- La hoja debe estar compartida como **«Cualquier persona con el enlace · Lector»**.
- Indicador junto al botón Actualizar: **En vivo** = leyó Google Sheets; **Datos de respaldo** = usó `datos/seguimiento.csv`.
- `.github/workflows/actualizar-datos.yml` (opcional) refresca esa copia de respaldo cada 30 min. Actívalo en la pestaña **Actions** del repo.

## Si cambia algo en la hoja
- Los encabezados se reconocen por nombre; mover columnas no rompe nada.
- Para apuntar a otra hoja o pestaña, edita `CONFIG` al inicio del `<script>` de `index.html` (`SHEET_ID`, `SHEET_NAME`, `REFRESH_MIN`).

## Privacidad
El tablero muestra nombres y calificaciones de colaboradores. En un repo público, cualquiera con el enlace (y el CSV de respaldo) puede verlos.
