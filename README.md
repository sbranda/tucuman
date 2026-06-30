# Tucumán en 5 días — Guía interactiva (PWA)

Guía de viaje instalable: itinerario día por día, mapa interactivo, curiosidades, tips y checklist offline.

## Estructura

```
index.html      → la app completa
manifest.json   → metadata de la PWA (nombre, ícono, colores)
sw.js           → service worker para funcionamiento offline
icon-192.svg    → ícono chico
icon-512.svg    → ícono grande
```

## Deploy en GitHub Pages (gratis, 5 minutos)

1. Creá un repo nuevo en GitHub, por ejemplo `tucuman-5-dias`.
2. Subí estos 5 archivos a la raíz del repo (no en una subcarpeta).
3. Andá a **Settings → Pages**.
4. En "Source" elegí la rama `main` y carpeta `/ (root)`. Guardá.
5. Esperá 1-2 minutos. La URL queda en:
   `https://TU-USUARIO.github.io/tucuman-5-dias/`

## Instalar como app

- **Android (Chrome)**: abrí la URL, va a aparecer un cartel para "Instalar app" o lo hacés manual desde el menú ⋮ → "Instalar app" / "Agregar a pantalla de inicio".
- **iPhone (Safari)**: abrí la URL → botón compartir (□↑) → "Agregar a pantalla de inicio".

Una vez instalada, abre en pantalla completa sin barra del navegador y el service worker cachea la app para que funcione aunque no haya señal (las fotos y el mapa sí necesitan internet la primera vez que se cargan).

## Actualizar contenido

Todo el contenido (itinerario, curiosidades, tips, checklist) está en el array `DAYS` y `TIPS` dentro de `index.html`, dentro del bloque `<script>`. Para editar, basta con tocar esos textos y volver a subir el archivo al repo — GitHub Pages se actualiza solo.

Si cambiás `sw.js` o agregás archivos nuevos al "app shell", subí también la versión del `CACHE_NAME` en `sw.js` (por ejemplo de `v1` a `v2`) para que los usuarios que ya instalaron la app reciban la actualización.
