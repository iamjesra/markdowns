# Snippets Code WordPress

* [Plantilla HTML5 básica](#plantilla-html5-básica)
* [Plantilla WordPress básica](#plantilla-wordpress-básica)
* [Comentarios style.css](#comentarios-style.css)
* [Comentarios functions.php](#comentarios-functions.php)
* [Ancho máximo](#ancho-máximo)
* [Inyectar archivos CSS y JS](#inyectar-archivos-css-y-js)
* [The Loop](#the-loop)
* [Paginación](#paginación)
* [Menús](#menús)
* [Widgets](#widgets)
* [Soporte al tema](#soporte-al-tema)
* [Datos autor](#datos-autor)
* [Plantilla comentarios](#plantilla-comentarios)
* [Traducciones](#traducciones)
* [Cabecera configurable](#cabecera-configurable)
* [Customizer](#customizer)
* [Custom login](#custom-login)
* [Custom admin](#custom-admin)
* [Clase WP_Query](#clase-wp_query)
* [Child Themes](#child-themes)

## Plantilla HTML5 básica

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Título del Sitio</title>
  <meta name="description" content="Descripción del Sitio">
</head>
<body>
    <header class="Header">
      <section class="Header-container">
        <div class="Logo">
          <a href="#">Logo</a>
        </div>
        <button class="Menu-btn">Menú Principal</button>
        <nav class="Menu">
          <ul>
            <li><a href="#">Sección 1</a></li>
            <li><a href="#">Sección 2</a></li>
            <li><a href="#">Sección 3</a></li>
            <li><a href="#">Sección 4</a></li>
            <li><a href="#">Sección 5</a></li>
          </ul>
        </nav>
      </section>
    </header>
    <section class="Content">
      <div class="Content-container">
        <main class="Main">
          <h2>Contenido Principal</h2>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
          </p>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
          </p>
          <img src="https://placeimg.com/400/400/any">
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
          </p>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
          </p>
          <img src="https://placeimg.com/400/400/any">
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
          </p>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
          </p>
          <img src="https://placeimg.com/400/400/any">
        </main>
        <aside class="Sidebar">
          <h2>Contenido Lateral</h2>
          <article class="Widget">
            <h3>Buscar:</h3>
            <form>
              <input type="text">
              <input type="submit" value="Buscar">
            </form>
          </article>
          <article class="Widget">
            <h3>Últimas Entradas:</h3>
            <ul>
              <li><a href="#">Entrada 1</a></li>
              <li><a href="#">Entrada 2</a></li>
              <li><a href="#">Entrada 3</a></li>
              <li><a href="#">Entrada 4</a></li>
              <li><a href="#">Entrada 5</a></li>
            </ul>
          </article>
          <article class="Widget">
            <h3>Otro Widget:</h3>
            <div>
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum, blanditiis aut? Placeat veniam iste quae molestias eius asperiores voluptatibus, quis voluptatum accusantium alias praesentium, et eum exercitationem accusamus, delectus repellendus?</p>
              <img src="https://placeimg.com/400/400/any">
            </div>
          </article>
        </aside>
      </div>
    </section>
    <footer class="Footer">
      <section class="Footer-container">
        <div>
          <nav class="SocialMedia">
            <ul>
              <li><a href="https://facebook.com" target="_blank">facebook</a></li>
              <li><a href="https://twitter.com" target="_blank">twitter</a></li>
              <li><a href="https://github.com" target="_blank">github</a></li>
              <li><a href="https://codepen.io" target="_blank">codepen</a></li>
              <li><a href="https://youtube.com" target="_blank">youtube</a></li>
              <li><a href="https://instagram.com" target="_blank">instagram</a></li>
            </ul>
          </nav>
        </div>
        <div>
          <p>
            &copy; 2018 Copyright
            <a href="https://jonmircha.com" target="_blank">@jonmircha</a>.
          </p>
        </div>
      </section>
    </footer>
</body>
</html>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Plantilla WordPress básica

```html
<!DOCTYPE html>
<html <?php language_attributes(); ?>>
<head>
  <meta charset="<?php bloginfo( 'charset' ); ?>">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title><?php bloginfo( 'name' ); ?></title>
  <meta name="description" content="<?php bloginfo( 'description' ); ?>">
  <?php wp_head(); ?>
</head>
<body <?php body_class(); ?>>
  <header class="Header">
    <section class="Header-container">
      <div class="Logo">
        <a href="<?php echo esc_url( home_url( '/' ) ); ?>">Logo</a>
      </div>
      <button class="Menu-btn"><?php _e('Menú Principal', 'mawt'); ?></button>
      <nav class="Menu">
        <ul>
          <?php wp_list_pages('title_li'); ?>
        </ul>
      </nav>
    </section>
  </header>
  <section class="Content">
    <div class="Content-container">
      <main class="Main">
        <h2>Contenido Principal</h2>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
        </p>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
        </p>
        <img src="https://placeimg.com/400/400/any">
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
        </p>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
        </p>
        <img src="https://placeimg.com/400/400/any">
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
        </p>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
        </p>
        <img src="https://placeimg.com/400/400/any">
      </main>
      <aside class="Sidebar">
        <h2>Contenido Lateral</h2>
        <article class="Widget">
          <h3>Buscar:</h3>
          <form>
            <input type="text">
            <input type="submit" value="Buscar">
          </form>
        </article>
        <article class="Widget">
          <h3>Últimas Entradas:</h3>
          <ul>
            <li><a href="#">Entrada 1</a></li>
            <li><a href="#">Entrada 2</a></li>
            <li><a href="#">Entrada 3</a></li>
            <li><a href="#">Entrada 4</a></li>
            <li><a href="#">Entrada 5</a></li>
          </ul>
        </article>
        <article class="Widget">
          <h3>Otro Widget:</h3>
          <div>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum, blanditiis aut? Placeat veniam iste quae molestias eius asperiores voluptatibus, quis voluptatum accusantium alias praesentium, et eum exercitationem accusamus, delectus repellendus?</p>
            <img src="https://placeimg.com/400/400/any">
          </div>
        </article>
      </aside>
    </div>
  </section>
  <footer class="Footer">
    <section class="Footer-container">
      <div>
        <nav class="SocialMedia">
          <ul>
            <li><a href="https://facebook.com" target="_blank">facebook</a></li>
            <li><a href="https://twitter.com" target="_blank">twitter</a></li>
            <li><a href="https://github.com" target="_blank">github</a></li>
            <li><a href="https://codepen.io" target="_blank">codepen</a></li>
            <li><a href="https://youtube.com" target="_blank">youtube</a></li>
            <li><a href="https://instagram.com" target="_blank">instagram</a></li>
          </ul>
        </nav>
      </div>
      <div>
        <p>
          &copy; <?php echo date('Y'); ?> Copyright
          <a href="https://jonmircha.com" target="_blank">@jonmircha</a>.
        </p>
      </div>
    </section>
  </footer>
  <?php wp_footer(); ?>
</body>
</html>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Comentarios style.css

```css
/*!
Theme Name: My Awesome WP Theme
Theme URI: https://jonmircha.com/mawt/
Author: Jonathan MirCha
Author URI: https://jonmircha.com/
Description: Una breve descripción de las características que tu tema ofrece a nivel de diseño, programación y personalización. Escríbela en inglés.
Version: 1.0.0
License: GNU General Public License v2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html
Tags: one-column, two-columns, right-sidebar, left-sidebar, full-width, flexible-header, accessibility-ready, custom-colors, custom-header, custom-menu, custom-logo, editor-style, featured-images, footer-widgets, post-formats, theme-options, translation-ready
Text Domain: mawt
*/
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Comentarios functions.php

```php
<?php
/**
 * My Awesome WordPress Theme functions and definitions
 *
 * @link https://developer.wordpress.org/themes/basics/theme-functions/
 *
 * @package WordPress
 * @subpackage mawt
 * @since 1.0.0
 * @version 1.0.0
 */
?>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Ancho máximo

```php
//https://codex.wordpress.org/Content_Width
//Establecer el ancho máximo permitido para cualquier contenido en el tema, como oEmbeds e imágenes
if ( !isset( $content_width ) ) {
  $content_width = 800;
}
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Inyectar archivos CSS y JS

```php
global $google_fonts;
$google_fonts = 'https://fonts.googleapis.com/css?family=Raleway:400,700';

function mawt_scripts () {
  global $google_fonts;

  wp_enqueue_style( 'google-fonts', $google_fonts, array(), '1.0.0', 'all' );
  wp_enqueue_style( 'custom-properties', get_template_directory_uri() . '/css/custom_properties.css', array('google-fonts'), '1.0.0', 'all' );
  wp_enqueue_style( 'toggle-nav-css', get_template_directory_uri() . '/css/toggle_nav.css', array(), '1.0.0', 'all' );
  wp_enqueue_style( 'style', get_stylesheet_uri(), array('google-fonts', 'custom-properties'), '1.0.0', 'all' );

  wp_enqueue_script( 'jquery' );
  wp_enqueue_script( 'toggle-nav-js', get_template_directory_uri() . '/js/toggle_nav.js', array(), '1.0.0', true );
  wp_enqueue_script( 'script', get_template_directory_uri() . '/script.js', array('jquery'), '1.0.0', true );
}

add_action('wp_enqueue_scripts', 'mawt_scripts');
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## The Loop

```php
if( have_posts() ):
  while( have_posts() ):
    the_post();
    //mostrar el contenido
    the_title();
    the_post_thumbnail();
    the_permalink();
    the_excerpt();
    the_category(', ');
    the_tags();
    the_time( get_option('date_format') );
    the_author_posts_link();
    the_content();
  endwhile;
else:
  //no hay contenido que mostrar
  // __() para que WP detecte que es un texto traducido
  // _e() para que WP detecte que es un texto traducido y lo imprima en pantalla
  _e('Contenido inexistente', 'mawt');
  _e('Realiza una búsqueda para encontrar lo que deseas.', 'mawt');
  get_search_form();
endif;
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Paginación

```php
<?php if ( get_next_posts_link() || get_previous_posts_link() ): ?>
  <div class="Pagination">
    <nav>
      <?php
      echo paginate_links(array(
        'prev_text' => __('<span>&laquo; Anteriores</span>', 'mawt'),
        'next_text' => __('<span>Siguientes &raquo;</span>', 'mawt')
      ));
      ?>
    </nav>
  </div>
<?php endif; ?>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Menús

```php
function mawt_menus () {
  register_nav_menus(array(
    'main_menu' => __('Menú Principal', 'mawt'),
    'social_menu' => __('Menú Redes Sociales', 'mawt')
  ));
}

add_action( 'init', 'mawt_menus' );

/*   **********   **********   **********   */

<?php
if ( has_nav_menu( 'main_menu' ) ):
  wp_nav_menu(array(
    'theme_location' => 'main_menu',
    'container' => 'nav',
    'container_class' => 'Menu'
  ));
else:
?>
  <nav class="Menu">
    <ul>
      <?php wp_list_pages('title_li'); ?>
    </ul>
  </nav>
<?php endif; ?>

/*   **********   **********   **********   */

<?php
  if ( has_nav_menu( 'social_menu' ) ):
    wp_nav_menu(array(
      'theme_location' => 'social_menu',
      'container' => 'nav',
      'container_class' => 'SocialMedia',
      'link_before' => '<span class="sr-text">',
      'link_after' => '</span>'
    ));
  endif;
?>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Widgets

```php
function mawt_register_sidebars () {
  register_sidebar(array(
    'name' => __('Sidebar principal', 'mawt') ,
    'id' => 'main_sidebar',
    'description' => __('Este es el sidebar principal', 'mawt'),
    'before_widget' => '<article id="%1$s" class="Widget  %2$s">',
    'after_widget' => '</article>',
    'before_title' => '<h3>',
    'after_title' => '</h3>',
  ));
}

add_action('widgets_init', 'mawt_register_sidebars');

/*   **********   **********   **********   */

<aside class="Sidebar">
  <?php
  if ( is_active_sidebar( 'main_sidebar' ) ):
    dynamic_sidebar( 'main_sidebar' );
  else:
  ?>
    <article class="Widget">
      <h3><?php _e('Buscar', 'mawt'); ?></h3>
      <?php get_search_form(); ?>
    </article>
  <?php endif; ?>
</aside>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Soporte al tema

```php
function mawt_setup () {
  //https://developer.wordpress.org/reference/functions/add_theme_support/
  add_theme_support( 'post-thumbnails' );
  //add_image_size( name, width, height, crop );

  add_theme_support('html5', array(
    'comment-list',
    'comment-form',
    'search-form',
    'gallery',
    'caption'
  ));

  //https://codex.wordpress.org/Post_Formats
  add_theme_support('post-formats',  array (
    'aside',
    'gallery',
    'link',
    'image',
    'quote',
    'status',
    'video',
    'audio',
    'chat'
  ) );

  //Permite que los themes y plugins administren el título, si se activa, no debe usarse wp_title()
  add_theme_support( 'title-tag' );

  //Activar Feeds RSS
  add_theme_support( 'automatic-feed-links' );

  //Ocultar Tags innecesarios del head
  //Versión de WordPress
  remove_action('wp_head', 'wp_generator');
  //Imprime sugerencias de recursos para los navegadores para precargar, pre-renderizar y pre-conectarse a sitios web
  remove_action('wp_head', 'wp_resource_hints', 2);
  //Muestre el enlace al punto final del servicio Really Simple Discovery
  remove_action('wp_head', 'rsd_link');
  //Muestre el enlace al archivo de manifiesto de Windows Live Writer
  remove_action('wp_head', 'wlwmanifest_link');
  //Inyecta rel = shortlink en el encabezado si se define un shortlink para la página actual.
  remove_action('wp_head', 'wp_shortlink_wp_head');

  //Quitar scripts para soporte a emojis
  //remove_action('wp_print_styles', 'print_emoji_styles');
  //remove_action('wp_head', 'print_emoji_detection_script', 7);

  //Quitar la barra de administración en el Frontend
  //add_filter('show_admin_bar', '__return_false');
}

add_action( 'after_setup_theme', 'mawt_setup' );
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Datos autor

```html
<aside class="AuthorInfo">
  <h3><?php _e('Información del Autor:', 'mawt'); ?></h3>
  <ul>
    <li>
      <?php _e('Usuario: ', 'mawt'); the_author(); ?>
    </li>
    <li>
      <?php _e('Nombre: ', 'mawt'); echo get_the_author_meta('first_name') . ' ' . get_the_author_meta('last_name'); ?>
    </li>
    <li>
      <?php _e('Correo: ', 'mawt'); echo get_the_author_meta('user_email'); ?>
    </li>
    <li>
      <?php _e('Url: ', 'mawt'); ?>
      <a href="<?php echo get_the_author_meta('user_url'); ?>" target="_blank">
        <?php echo get_the_author_meta('user_url'); ?>
      </a>
    </li>
    <li>
      <?php _e('Fecha de registro: ', 'mawt'); echo get_the_author_meta('user_registered'); ?>
    </li>
    <li>
      <?php _e('Rol del usuario: ', 'mawt'); echo get_the_author_meta('roles')[0]; ?>
    </li>
    <li>
      <?php _e('Descripción: ', 'mawt'); echo get_the_author_meta('description'); ?>
    </li>
    <li>
      <?php _e('Número de publicaciones: ', 'mawt'); echo get_the_author_posts(); ?>
    </li>
    <li>
      <?php _e('Avatar: ', 'mawt'); echo get_avatar( get_the_author_meta('ID'), 500 ); ?>
    </li>
  </ul>
</aside>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Plantilla comentarios

```html
<aside class="Comments">
  <?php if ( have_comments() ): ?>
    <h3>
      <?php
        comments_number(
          __('No hay comentarios aún', 'mawt'),
          __('Hay un comentario publicado', 'mawt'),
          __('Hay % comentarios', 'mawt')
        );
      ?>
    </h3>
    <ol class="commentlist">
      <?php wp_list_comments(); ?>
    </ol>
  <?php endif; ?>
  <?php comment_form(); ?>
</aside>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Traducciones

```php
//Soporte para traducciones
  //https://developer.wordpress.org/themes/functionality/internationalization/
  //https://make.wordpress.org/polyglots/handbook/
//Herramientas
  //https://www.icanlocalize.com/tools/php_scanner
  //https://poedit.net/

  load_theme_textdomain( 'mawt', get_template_directory() . '/languages' );
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Cabecera configurable

```php
/*   **********   functions.php   **********   */
<?php
function mawt_custom_header () {
  //Activar logo configurable
  add_theme_support( 'custom-logo', array (
    'height' => 100,
    'width' => 100,
    'flex-height' => true,
    'flex-width' => true
  ) );

  //Activar fondo configurable
  add_theme_support( 'custom-background', array (
    'default-color' => 'FFF',
    'default-image' => get_template_directory_uri() . '/img/background-image.png',
    'default-repeat' => 'repeat',
    'default-position-x' => '',
    'default-position-y' => '',
    'default-size' => '',
    'default-attachment' => 'fixed'
  ) );

  //Activa la actualización selectiva de widgets en el personalizador
  add_theme_support( 'customize-selective-refresh-widgets' );

  //Activar cabecera configurable
  //https://developer.wordpress.org/themes/functionality/custom-headers/
  add_theme_support( 'custom-header', apply_filters( 'mawt_custom_header_args', array (
    'default-image' => get_template_directory_uri() . '/img/header-image.jpg',
    'default-text-color' => '0096D9',
    'width' => 1200,
    'height' => 720,
    'flex-width' => true,
    'flex-height' => true,
    'video' => true,
    'wp-head-callback' => 'mawt_wp_header_style'
  )) );
}

add_action( 'after_setup_theme', 'mawt_custom_header' );

function mawt_wp_header_style () {
  $header_text_color = get_header_textcolor();
?>
  <style>
    .WP-Header-branding * { color: #<?php echo esc_attr( $header_text_color ); ?>; }
  </style>
<?php } ?>
```

```html
/*   **********   logo   **********   */
<div class="Logo">
  <?php
    if ( has_custom_logo() ):
      the_custom_logo();
    else:
  ?>
    <a href="<?php echo esc_url( home_url( '/' ) ); ?>">
      <img src="<?php echo get_template_directory_uri() . '/img/custom-logo.png'; ?>" alt="<?php bloginfo( 'name' ); ?>">
    </a>
  <?php endif; ?>
</div>
```

```html
/*   **********   cabecera   **********   */
<?php
  //header_image();
  //get_header_image();
  //the_header_video_url();
  //get_header_video_url();
  //the_header_image_tag();
  //the_custom_header_markup();
?>
<?php if ( is_home() || is_front_page() ): ?>
  <header class="WP-Header">
    <?php
      if ( has_custom_header()  ):
        the_custom_header_markup();
      endif;
    ?>
    <div class="WP-Header-branding">
      <h1 class="WP-Header-title">
        <a href="<?php echo esc_url( home_url( '/' ) ); ?>">
          <?php bloginfo( 'name' ); ?>
        </a>
      </h1>
      <p  class="WP-Header-description">
        <?php bloginfo( 'description' ); ?>
      </p>
    </div>
  </header>
<?php endif; ?>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Customizer

```php
<?php
function mawt_customize_register( $wp_customize ) {
  $wp_customize->get_setting( 'blogname' )->transport = 'postMessage';
  $wp_customize->get_setting( 'blogdescription' )->transport = 'postMessage';

  if ( isset( $wp_customize->selective_refresh ) ) {
    $wp_customize->selective_refresh->add_partial( 'blogname', array(
      'selector' => '.WP-Header-title',
      'render_callback' => 'mawt_customize_blogname'
    ) );
    $wp_customize->selective_refresh->add_partial( 'blogdescription', array(
      'selector' => '.WP-Header-description',
      'render_callback' => 'mawt_customize_blogdescription',
    ) );
  }
}

add_action( 'customize_register', 'mawt_customize_register' );

function mawt_customize_blogname () {
  bloginfo( 'name' );
}

function mawt_customize_blogdescription () {
  bloginfo( 'description' );
}
?>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Custom login

```php
<?php
//https://codex.wordpress.org/Customizing_the_Login_Form
function mawt_login_scripts () {
  wp_enqueue_style( 'custom-properties', get_stylesheet_directory_uri() . '/css/custom_properties.css', array(), '1.0.0', 'all' );
  wp_enqueue_style( 'login-page-css', get_template_directory_uri() . '/css/login_page.css', array('custom-properties'), '1.0.0', 'all' );

  wp_enqueue_script( 'jquery' );
  wp_enqueue_script( 'login-page-js', get_template_directory_uri() . '/js/login_page.js', array('jquery'), '1.0.0', true );
}

add_action( 'login_enqueue_scripts', 'mawt_login_scripts' );

function mawt_login_logo_url () {
  return home_url();
}

add_filter( 'login_headerurl', 'mawt_login_logo_url' );

function mawt_login_logo_url_title() {
  return get_bloginfo( 'title' ) . ' | ' .  get_bloginfo( 'description' );
}

add_filter( 'login_headertitle', 'mawt_login_logo_url_title' );
?>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Custom admin

```php
<?php
//https://codex.wordpress.org/Dashboard_Widgets_API
//https://codex.wordpress.org/Plugin_API/Admin_Screen_Reference
//https://codex.wordpress.org/Administration_Screens
//https://codex.wordpress.org/Adding_Administration_Menus

function mawt_add_editor_styles () {
  global $google_fonts;
  add_editor_style( $google_fonts );
  add_editor_style( 'css/custom_properties.css' );
  add_editor_style( 'css/custom_editor_style.css' );
}

add_action( 'admin_init', 'mawt_add_editor_styles' );

function mawt_user_contactmethods ($data_user) {
  $data_user['facebook']=__('Facebook', 'mawt');
  $data_user['twitter']=__('Twitter', 'mawt');

  return $data_user;
}

add_filter( 'user_contactmethods', 'mawt_user_contactmethods' );
?>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Clase WP_Query

```php
//https://developer.wordpress.org/reference/classes/wp_query/
//https://codex.wordpress.org/Class_Reference/WP_Query
//https://developer.wordpress.org/reference/functions/query_posts/
//https://developer.wordpress.org/reference/functions/wp_reset_query/

$wp_query = new WP_Query( array(
  'posts_per_page' => 6,
  'orderby' => 'rand'
) );

if( $wp_query->have_posts() ):
  while( have_posts() ):
    $wp_query->the_post();
    //mostrar el contenido
    the_title();
    the_post_thumbnail();
    the_permalink();
    the_excerpt();
    the_category(', ');
    the_tags();
    the_date();
    the_time( get_option('date_format') );
    the_author_posts_link();
    the_content();
  endwhile;
else:
  _e('Contenido inexistente', 'mawt');
  _e('Realiza una búsqueda para encontrar lo que deseas.', 'mawt');
  get_search_form();
endif;
wp_reset_postdata();
wp_reset_query();
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Child Themes

```css
/*!
Theme Name: My Awesome WP Child Theme
Theme URI: https://jonmircha.com/mawt-child/
Description: Child Theme. Parent Theme: My Awesome WP Theme
Author: Jonathan MirCha
Author URI: https://jonmircha.com/
Template: mawt
Version: 1.0.0
License: GNU General Public License v2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html
Tags: one-column, two-columns, right-sidebar, flexible-header, accessibility-ready, custom-colors, custom-header, custom-menu, custom-logo, editor-style, featured-images, footer-widgets, post-formats, rtl-language-support, sticky-post, theme-options, threaded-comments, translation-ready
Text Domain: child_mawt
*/
@import url('../mawt/style.css');
```

```php
<?php
/**
 * My Awesome WordPress Child Theme functions and definitions
 *
 * @link https://developer.wordpress.org/themes/basics/theme-functions/
 *
 * @package mawt
 * @subpackage child_mawt
 * @since 1.0.0
 * @version 1.0.0
 */

 //Más info
  //https://codex.wordpress.org/Child_Themes
  //https://make.wordpress.org/training/handbook/theme-school/child-themes/
  //https://developer.wordpress.org/themes/advanced-topics/child-themes/

//Funciones importantes
  //get_template_directory_uri() – URL para acceder al tema padre
  //get_stylesheet_directory_uri() – URL para acceder al tema hijo

function child_mawt_scripts () {
  wp_enqueue_style( 'parent-style', get_template_directory_uri() . '/style.css', array(), '1.0.0', 'all' );
  wp_enqueue_style( 'child-style', get_stylesheet_directory_uri() . '/style.css', array('parent-style'), '1.0.0', 'all' );

  wp_enqueue_script( 'child-script', get_stylesheet_directory_uri() . '/script.js', array('jquery'), '1.0.0', true );
}

add_action('wp_enqueue_scripts', 'child_mawt_scripts');

function child_mawt_setup () {
  load_child_theme_textdomain( 'child_mawt', get_stylesheet_directory_uri() . '/languages' );
}

add_action( 'after_setup_theme', 'child_mawt_setup' );
?>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**
