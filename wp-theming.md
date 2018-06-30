# Creación de Temas en WordPress

* [Documentación](#documentación)
* [Estructura de Archivos](#estructura-de-archivos)
* [Hooks](#hooks)
* [The Loop](#the-loop)
* [Jerarquía de Plantillas](#jerarquía-de-plantillas)

## Documentación:

* [Buenas prácticas PHP en WordPress](https://make.wordpress.org/core/handbook/coding-standards/php/)
* [Codex WordPress](http://codex.wordpress.org/)
* [Developers WordPress](https://developer.wordpress.org/)
* [Glosario de conceptos importantes en WP](https://codex.wordpress.org/Glossary)
* [API de Hooks WP](http://codex.wordpress.org/Plugin_API/Hooks)
  * [Lista de Acciones WP](http://codex.wordpress.org/Plugin_API/Action_Reference)
  * [Lista de Filtros WP](http://codex.wordpress.org/Plugin_API/Filter_Reference)
* [API de Plugins WP](http://codex.wordpress.org/Plugin_API)
* [API de Widgets WP](https://codex.wordpress.org/Widgets_API)
* [Jerarquía de Plantillas WP](https://wphierarchy.com/)
  * [por Templates Files](https://developer.wordpress.org/themes/basics/template-hierarchy/)
  * [por Conditional Tags](https://codex.wordpress.org/Conditional_Tags)

**[🔙 Regresar](#creación-de-temas-en-wordpress)**

## Estructura de Archivos

Un Tema es una colección de archivos que trabajan juntos para producir un interfaz gráfica con un diseño unificado para el sitio. Estos archivos se llaman archivos de plantilla.

Un tema modifica el modo en que el sitio es mostrado, sin modificar el código fuente de WordPress.

Los temas pueden incluir archivos de plantilla personalizados, archivos de imagen, hojas de estilo, scripts (.php o .js), así como cualquier otro archivo necesario.

### Archivos básicos:

* **index.php**: Plantilla principal.
* **style.css**: Hoja de estilos principal.
* **functions.php**: Archivo de funciones.
* **screenshot.png**: Imagen de captura de pantalla.

### Archivos para contenido común:

* **header.php**: Contiene la cabecera.
* **footer.php**: Contiene el pié de página.
* **sidebar.php**: Contiene la barra lateral.

**[🔙 Regresar](#creación-de-temas-en-wordpress)**

## Hooks:

El archivo **functions.php**  es la biblioteca particular de funciones del tema en cuestión, es una manera fácil de agregar o modificar el comportamiento por defecto de WordPress.

Se comporta exactamente igual que un plugin, añadiendo características y funcionalidad al tema, se puede utilizar tanto para definir nuevas funciones PHP como para modificar las que ya incorpora WordPress.

El comportamiento de WordPress se modifica mediante **hooks**, que son eventos que se ejecutan por la invocación de **acciones** o la aplicación de **filtros**. También se puede modificar a través de **widgets** y **plugins**.

### Funciones de inclusión obligatoria:

Para el correcto funcionamiento de hooks propios, de wordpress y/o de plugins de terceros en el tema, es necesario activar las siguientes funciones:

* **`wp_head()`** debe colocarse antes de `</head>`.
* **`wp_footer()`** debe colocarse antes de `</body>`.

 De esta manera WordPress permite inyectar de forma dinámica el código html, css y/o js que se requiera para cada funcionalidad.

 **[🔙 Regresar](#creación-de-temas-en-wordpress)**

## The Loop

[The Loop](https://developer.wordpress.org/themes/basics/the-loop/) es el código PHP usado por WordPress para mostrar el contenido solicitado:

```php
if( have_posts() ):
  while( have_posts() ):
    the_post();
    //mostrar el contenido
  endwhile;
else:
  //no hay contenido que mostrar
endif;
```

**[🔙 Regresar](#creación-de-temas-en-wordpress)**

## Jerarquía de Plantillas

Dependiendo del contenido a mostrar en el navegador, WordPress buscará dentro de la carpeta del tema el archivo indicado para cada ocasión, si no lo encuentra disponible siempre mostrará el **index.php**.

Se puede tomar ventaja de la jerarquía de plantillas creando diferentes archivos para presentar los contenidos de formas diferentes dependiendo las circunstancias y necesidades tanto de contenido, como de diseño.

![Jerarquía de Plantillas en WordPress](https://developer.wordpress.org/files/2014/10/wp-hierarchy.png)

**[🔙 Regresar](#creación-de-temas-en-wordpress)**
