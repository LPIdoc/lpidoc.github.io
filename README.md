# LPIdoc · Sitio web docente

Web estática del **Laboratorio de Procesado de Imágenes (LPI)**, preparada para GitHub Pages.

## Añadir una nueva asignatura o repositorio

La web de LPIdoc muestra automáticamente los repositorios públicos de la organización. Para incorporar una nueva asignatura o material docente al catálogo, basta con crear un repositorio y completar su información.

### 1. Crear el repositorio

1. Accede a la organización [LPIdoc](https://github.com/LPIdoc).
2. Selecciona **Repositories → New repository**.
3. Introduce un nombre representativo de la asignatura o del material docente.
4. Selecciona la visibilidad **Public**.
5. Crea el repositorio y sube los materiales correspondientes (apuntes, prácticas, notebooks, etc.).

### 2. Configurar el apartado About

Este paso es importante porque **la web obtiene automáticamente la información del apartado About de cada repositorio**.

En la página principal del repositorio, localiza la sección **About**, situada normalmente en la columna derecha, y pulsa el icono de configuración (⚙️).

Completa los siguientes campos:

- **Description:** breve descripción de la asignatura o del contenido del repositorio. Este texto aparecerá directamente en el catálogo de LPIdoc.
- **Website:** dirección de la página web de la asignatura, si existe. Puede ser, por ejemplo, una web creada con Jupyter Book, MyST o GitHub Pages.
- **Topics (opcional):** etiquetas relacionadas con los contenidos de la asignatura para facilitar su identificación en GitHub.

Guarda los cambios mediante **Save changes**.

Por ejemplo, para un repositorio llamado `Sistemas-Lineales`:

- **Repository:** `Sistemas-Lineales`
- **Description:** Material docente, prácticas y ejercicios de la asignatura Sistemas Lineales.
- **Website:** `https://ejemplo.github.io/sistemas-lineales/`

La web mostrará una entrada con el nombre del repositorio, su descripción y enlaces tanto a la página web (si existe) como al propio repositorio.

### 3. Actualización automática del catálogo

**No es necesario editar la web ni modificar ningún archivo para añadir una asignatura.**

Cada vez que alguien abre o recarga [https://lpidoc.github.io/](https://lpidoc.github.io/), la página consulta la API pública de GitHub para obtener la lista actualizada de repositorios.

Esto significa que:

- **Nuevo repositorio público:** aparece automáticamente en el catálogo.
- **Cambio de descripción:** se refleja automáticamente en la web.
- **Nueva página web:** al introducir su URL en el campo *Website* de About, aparece el enlace correspondiente.
- **Cambio de URL:** la web utiliza la nueva dirección.
- **Repositorio privado o archivado:** no aparece en el catálogo.

Los cambios son visibles al recargar la página, sujetos a los posibles tiempos de caché y límites de la API de GitHub.

## Cómo funciona el catálogo

- Lee los repositorios públicos directamente desde `https://api.github.com/orgs/LPIdoc/repos` al abrir la página.
- Para cada repositorio muestra su nombre, descripción (*About*), enlace a la web (*Website*, si existe) y enlace al repositorio.
- Excluye `.github`, `lpidoc.github.io` y los repositorios archivados.
- Incluye búsqueda en el navegador y carga varias páginas de resultados de GitHub.
- No necesita tokens ni permisos de escritura.

## Personalización

Los textos, colores y estilos están definidos en `index.html`.

Para modificar la organización, cambia `const ORG = 'LPIdoc'` al final del archivo.

No es necesario modificar `.github/profile/README.md`; el perfil de GitHub y esta web son independientes.

## Notas

- La API de GitHub aplica límites a las peticiones sin autenticación. Si se alcanza el límite, la página permite reintentar.
- Los nombres y las descripciones se incorporan como texto, sin interpretar HTML externo.
- La web no almacena información personal ni utiliza herramientas de analítica.

## Estilo visual

La web utiliza la paleta **Nord**:

- **Polar Night:** `#2E3440`
- **Snow Storm:** `#ECEFF4`, `#E5E9F0`, `#D8DEE9`
- **Frost:** `#88C0D0`, `#5E81AC`

Los colores se pueden modificar mediante las variables CSS `:root` de `index.html`.
