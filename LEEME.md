# Mi portafolio científico — V0.1

Una primera página local para aprender HTML y CSS con tus propios proyectos.

## 1. Abrir y editar

Esta carpeta contiene tres archivos:

```text
mi-web/
  index.html    Contenido y estructura de la página
  styles.css    Apariencia y distribución del contenido
  LEEME.md      Esta guía; no forma parte de la página
```

Abre `index.html` con doble clic para verlo en tu navegador. Funciona sin conexión a Internet y sin instalar herramientas. Mantén `styles.css` en la misma carpeta: el HTML lo busca allí.

Para editar, abre el archivo con un editor de texto (por ejemplo, Bloc de notas). Guarda con Ctrl+S y actualiza el navegador con Ctrl+R. Comprueba que el archivo siga llamándose `index.html` y no `index.html.txt`. Usa UTF-8 al guardar para conservar las tildes.

## 2. Qué hace HTML

HTML describe el contenido y su significado mediante **etiquetas**. Por ejemplo:

```html
<h1>Explorar el océano.</h1>
<p>Soy estudiante universitario.</p>
```

`h1` identifica el título principal; `p`, un párrafo. La mayoría de las etiquetas tienen apertura y cierre. El texto entre ellas es lo que verá el visitante. Elegimos etiquetas por su significado; después CSS cambia su aspecto.

Lee `index.html` de arriba abajo:

1. `<!DOCTYPE html>` indica que usamos HTML moderno.
2. `<html lang="es">` contiene el documento y declara su idioma.
3. `<head>` guarda información para el navegador: codificación, adaptación a móviles, descripción y título de la pestaña. El primer `link` conecta el CSS; el segundo contiene un pequeño icono para la pestaña. Puedes dejar ese icono sin cambios durante esta lección.
4. `<body>` contiene la parte visible.
5. `<header>` presenta la identidad del sitio; `<nav>` agrupa la navegación.
6. `<main>` contiene el contenido principal. Cada `<section>` reúne un tema con su título.
7. Cada `<article>` es el resumen de un proyecto. `h2` titula secciones y `h3` titula proyectos dentro de ellas.
8. `<footer>` cierra la página.

Los comentarios `<!-- ... -->` son notas para quien lee el código; no se muestran en la página.

### Cómo funciona la navegación

```html
<a href="#proyectos">Proyectos</a>
<section id="proyectos">
```

`a` crea un enlace. `href="#proyectos"` señala el elemento cuyo `id` es `proyectos` dentro de esta misma página. No necesita JavaScript. Cada `id` debe ser único.

Los atributos `aria-label` y `aria-labelledby` ayudan a identificar la navegación y las secciones con tecnologías de asistencia. El enlace «Saltar al contenido» aparece al usar Tab y permite pasar directamente al contenido principal.

## 3. Qué hace CSS

CSS aplica reglas de presentación a los elementos del HTML:

```css
.portada {
  background-color: #0e3545;
  color: #ffffff;
}
```

`.portada` es el **selector**: elige elementos que tienen `class="portada"`. Dentro de las llaves, cada **propiedad** recibe un **valor**. Aquí damos fondo azul oscuro y texto blanco. El punto indica una clase; `body` o `h1`, sin punto, seleccionan etiquetas. Una clase se puede usar en varios elementos.

El archivo está comentado y sigue el orden visual de la página: base, cabecera, portada, secciones y adaptación a pantallas estrechas. Los comentarios en CSS se escriben `/* así */`.

Conceptos que encontrarás:

- `margin`: espacio por fuera de un elemento. `padding`: espacio por dentro, entre el contenido y el borde.
- `box-sizing: border-box`: hace que el ancho declarado incluya el relleno y el borde.
- `max-width`: limita el ancho para que los textos no recorran toda una pantalla grande. `margin: 0 auto` centra ese bloque.
- `rem`: unidad relativa al tamaño de letra raíz del navegador; suele equivaler a 16 píxeles por defecto. Respeta mejor las preferencias de tamaño del lector.
- `display: flex`: distribuye la cabecera y los enlaces en filas que pueden ajustarse al espacio disponible.
- `display: grid`: crea columnas. `1fr 1fr` reparte el espacio en dos partes iguales; `1fr 2fr`, en proporción uno a dos.
- `gap`: espacio entre elementos de Flexbox o Grid.
- `@media (max-width: 700px)`: aplica estas reglas cuando la ventana mide 700 píxeles o menos. Allí los proyectos pasan a una columna.
- `:hover` y `:focus-visible`: muestran estados al pasar el cursor o navegar con teclado.

La cascada significa que varias reglas pueden afectar al mismo elemento. Entre reglas de igual prioridad y especificidad, prevalece la que aparece después. Por eso el tamaño de `h1` del bloque `@media` reemplaza al anterior en pantallas estrechas.

## 4. Por qué esta primera versión es así

Tenemos una sola página para concentrarnos en la estructura. Separar HTML y CSS permite cambiar el contenido sin tocar los estilos, y viceversa. Las clases están en español para facilitar la lectura. Las tipografías ya están disponibles en el equipo, y no hay imágenes ni dependencias que descargar.

La portada usa azul oscuro y un acento turquesa relacionado con el tema marino. Los proyectos comparten una clase para mantener un diseño consistente con pocas reglas. No tienen enlaces aún porque sus páginas todavía no existen. «Ficha del proyecto por incorporar» se refiere al contenido del sitio, no al estado de tu investigación.

«Tu nombre» es un marcador que debes reemplazar. La presentación es un borrador editable. No se han añadido universidad, resultados, publicaciones ni cifras que no hayas proporcionado.

## 5. Tu primer ejercicio: un cambio de contenido y uno de estilo

1. Abre la página en el navegador y deja abierto también el código.
2. En `index.html`, sustituye las dos apariciones visibles/funcionales de «Tu nombre»: dentro de `title` y dentro del enlace de la cabecera. El comentario no afecta a la página.
3. Reescribe el párrafo de «Sobre mí» con dos o tres frases tuyas, conservando las etiquetas `<p>` y `</p>`.
4. Guarda y actualiza. Observa que cambia el texto, pero la distribución se conserva.
5. En `styles.css`, busca `.portada` y cambia su `background-color` de `#0e3545` a `#153f60`.
6. Guarda y actualiza. Esta vez cambia el aspecto, pero el contenido se conserva.
7. Estrecha la ventana: observa cómo los proyectos pasan de dos columnas a una. Pulsa Tab para recorrer los enlaces y Enter para activarlos.

Si algo no aparece, comprueba primero que guardaste el archivo, actualizaste el navegador y mantuviste las etiquetas, llaves y nombres de archivo. Ctrl+Z permite deshacer el último cambio en el editor.

Antes de avanzar, intenta explicar: ¿qué archivo cambias para corregir un título?, ¿cuál para darle otro color?, ¿cómo sabe un enlace a qué sección debe ir?

## Más adelante

Cuando te sientas cómodo modificando esta página, crearemos una ficha de proyecto con problema, metodología, resultados y limitaciones a partir de tu material real. Después aprenderemos Git/GitHub y publicación. Añadiremos JavaScript cuando una interacción concreta lo requiera, y el dominio propio puede llegar más adelante.
