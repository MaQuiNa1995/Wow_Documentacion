# Utilidades de WoW

Sitio web estático en español con herramientas para preparar notas de raid y guías de cooldowns de sanación.

## Estructura

- `index.html`: página principal del sitio.
- `herramientas/`: conversor y notas guardadas en el navegador.
- `documentacion/`: guía para crear notas y avisos en NSRT.
- `Wow_healers/`: fichas de cooldowns para siete especializaciones healer.

No requiere dependencias ni proceso de compilación. Las notas guardadas se almacenan en el navegador donde se crean.

## Publicar en GitHub Pages

En el repositorio, abre **Settings → Pages** y configura **Deploy from a branch**, seleccionando `main` y la carpeta `/(root)`. Guarda los cambios; GitHub Pages publicará el sitio desde `index.html`.
