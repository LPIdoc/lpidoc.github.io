# LPIdoc · Sitio web docente

Web estática del **Laboratorio de Procesado de Imágenes (LPI)**, preparada para GitHub Pages.

## Publicación

1. En la organización [LPIdoc](https://github.com/LPIdoc), crea un repositorio **público** llamado `lpidoc.github.io`.
2. Sube `index.html` y `.nojekyll` a la **raíz** de la rama `main`.
3. Ve a **Settings → Pages → Build and deployment** y selecciona **Deploy from a branch**, rama `main`, carpeta `/(root)`. Guarda los cambios.
4. La dirección del sitio será `https://lpidoc.github.io/` cuando termine la publicación.

No se necesita GitHub Actions ni instalar dependencias.

## Cómo funciona el catálogo

- Lee los repositorios públicos directamente desde `https://api.github.com/orgs/LPIdoc/repos` al abrir la página.
- Para cada uno muestra nombre, descripción (*About*), enlace a la web (*Website*, si existe) y enlace al repositorio.
- Excluye `.github`, `lpidoc.github.io` y los repositorios archivados.
- Incluye búsqueda en el navegador y carga varias páginas de resultados de GitHub.
- No necesita tokens ni permisos de escritura. Los cambios se reflejan al recargar la página, sujetos a caché y límites de la API de GitHub.

## Personalización

Los textos, colores y estilos están en `index.html`. Para editar la organización, cambia `const ORG = 'LPIdoc'` al final del archivo. No es necesario tocar `.github/profile/README.md`; ese perfil y esta web son independientes.

## Notas

- La API de GitHub aplica límites a peticiones sin autenticación. En ese caso, la página permite reintentar.
- Los nombres y las descripciones se incorporan como texto, sin interpretar HTML externo.
- La web no almacena información personal ni utiliza analíticas.
