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
* [Cabecera configurable](#cabecera-configurable)
* [Customizer](#customizer)
* [Custom login](#custom-login)
* [Custom admin](#custom-admin)
* [Traducciones](#traducciones)
* [Child Themes](#child-themes)
* [Clase WP_Query](#clase-wp_query)

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
Tags: one-column, two-columns, right-sidebar, flexible-header, accessibility-ready, custom-colors, custom-header, custom-menu, custom-logo, editor-style, featured-images, footer-widgets, post-formats, rtl-language-support, sticky-post, theme-options, threaded-comments, translation-ready
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
if ( !function_exists( 'mawt_scripts' ) ):
  function mawt_scripts () {
    wp_register_style( 'google-fonts', 'https://fonts.googleapis.com/css?family=Raleway:400,700', array(), '1.0.0', 'all' );
    wp_register_style( 'style', get_stylesheet_uri(), array('google-fonts'), '1.0.0', 'all' );

    wp_enqueue_style( 'google-fonts' );
    wp_enqueue_style( 'style' );

    wp_register_script( 'script', get_template_directory_uri() . '/script.js', array('jquery'), '1.0.0', true );

    wp_enqueue_script( 'jquery' );
    wp_enqueue_script( 'script' );
  }
endif;

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
    the_date();
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
      <?php next_posts_link( __('<span>&laquo; Previos</span>', 'mawt') ); ?>
      <?php previous_posts_link( __('<span>Recientes  &raquo;</span>', 'mawt') ); ?>
      <br>
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
if ( !function_exists( 'mawt_menus' ) ):
  function mawt_menus () {
    register_nav_menus(array(
      'main_menu' => __('Menú Principal', 'mawt'),
      'social_menu' => __('Menú Redes Sociales', 'mawt')
    ));
  }
endif;

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
  wp_nav_menu(array(
    'theme_location' => 'social_menu',
    'container' => 'nav',
    'container_class' => 'SocialMedia',
    'link_before' => '<span class="sr-text">',
    'link_after' => '</span>'
  ));
?>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Widgets

```php
if ( !function_exists( 'mawt_register_sidebars' ) ):
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
endif;

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
if ( !function_exists( 'mawt_setup' ) ):
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
endif;

add_action( 'after_setup_theme', 'mawt_setup' );
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Datos autor

```html
<aside class="AuthorInfo">
  <h3>Información del Autor:</h3>
  <ul>
    <li>
      Usuario: <?php the_author(); ?>
    </li>
    <li>
      Nombre: <?php echo get_the_author_meta('first_name') . ' ' . get_the_author_meta('last_name'); ?>
    </li>
    <li>
      Correo: <?php echo get_the_author_meta('user_email'); ?>
    </li>
    <li>
      Url:
      <a href="<?php echo get_the_author_meta('user_url'); ?>" target="_blank">
        <?php echo get_the_author_meta('user_url'); ?>
      </a>
    </li>
    <li>
      Fecha de registro:
      <?php echo get_the_author_meta('user_registered'); ?>
    </li>
    <li>
      Rol del usuario:
      <?php echo get_the_author_meta('roles')[0]; ?>
    </li>
    <li>
      Descripción:
      <?php echo get_the_author_meta('description'); ?>
    </li>
    <li>
      Número de publicaciones:
      <?php echo get_the_author_posts(); ?>
    </li>
    <li>
      Avatar:
      <?php echo get_avatar( get_the_author_id(), 500 ); ?>
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
    <?php paginate_comments_links(); // más de 50 comentarios ?>
  <?php endif; ?>
  <?php comment_form(); ?>
</aside>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Cabecera configurable

```php
/*   **********   functions.php   **********   */
<?php
if ( !function_exists( 'mawt_custom_header' ) ):
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
endif;

add_action( 'after_setup_theme', 'mawt_custom_header' );

if ( !function_exists( 'mawt_wp_header_style' ) ) :
  function mawt_wp_header_style () {
    $header_text_color = get_header_textcolor();
?>
  <style>
    .WP-Header-branding * { color: #<?php echo esc_attr( $header_text_color ); ?>; }
  </style>
<?php
  }
endif;
?>
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
      <?php bloginfo( 'name' ); ?>
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
<header class="WP-Header">
  <?php
    if ( has_custom_header()  ):
      the_custom_header_markup();
    endif;

    if ( is_front_page() || is_home() ):
    $title_tag = 'h1';
    else:
      $title_tag = 'p';
    endif;
  ?>

  <div class="WP-Header-branding">
    <?php echo '<' . $title_tag . ' class="WP-Header-title">'; ?>
      <a href="<?php echo esc_url( home_url( '/' ) ); ?>">
        <?php bloginfo( 'name' ); ?>
      </a>
    <?php echo '</' . $title_tag . '>'; ?>
    <p  class="WP-Header-description">
      <?php bloginfo( 'description' ); ?>
    </p>
  </div>
</header>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Customizer

```php
<?php
if ( !function_exists('mawt_customize_register') ):
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
endif;

add_action( 'customize_register', 'mawt_customize_register' );


if ( !function_exists('mawt_customize_blogname') ):
  function mawt_customize_blogname () {
    bloginfo( 'name' );
  }
endif;

if ( !function_exists('mawt_customize_blogdescription') ):
  function mawt_customize_blogdescription () {
    bloginfo( 'description' );
  }
endif;
?>
```

**[⬆ regresar al índice](#snippets-code-wordpress)**

## Custom login

```php
<?php
//https://codex.wordpress.org/Customizing_the_Login_Form

if ( !function_exists( 'mawt_login_scripts' ) ):
  function mawt_login_scripts () {
    wp_register_style( 'custom-properties', get_stylesheet_directory_uri() . '/css/custom_properties.css', array(), '1.0.0', 'all' );
    wp_register_style( 'login-page-style', get_template_directory_uri() . '/css/login_page.css', array(), '1.0.0', 'all' );

    wp_enqueue_style( 'custom-properties' );
    wp_enqueue_style( 'login-page-style' );

    wp_register_script( 'login-page-script', get_template_directory_uri() . '/js/login_page.js', array('jquery'), '1.0.0', true );

    wp_enqueue_script( 'jquery' );
    wp_enqueue_script( 'login-page-script' );
  }
endif;

add_action( 'login_enqueue_scripts', 'mawt_login_scripts' );

if ( !function_exists( 'mawt_login_logo_url' ) ):
  function mawt_login_logo_url () {
    return home_url();
  }
endif;

add_filter( 'login_headerurl', 'mawt_login_logo_url' );

if ( !function_exists( 'mawt_login_logo_url_title' ) ):
  function mawt_login_logo_url_title() {
      return get_bloginfo( 'title' ) . ' | ' .  get_bloginfo( 'description' );
  }
endif;

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

if ( !function_exists( 'mawt_admin_scripts' ) ):
  function mawt_admin_scripts () {
    wp_register_style( 'custom-properties', get_stylesheet_directory_uri() . '/css/custom_properties.css', array(), '1.0.0', 'all' );
    wp_register_style( 'admin-page-style', get_template_directory_uri() . '/css/admin_page.css', array(), '1.0.0', 'all' );

    wp_enqueue_style( 'custom-properties' );
    wp_enqueue_style( 'admin-page-style' );

    wp_register_script( 'admin-page-script', get_template_directory_uri() . '/js/admin_page.js', array('jquery'), '1.0.0', true );

    wp_enqueue_script( 'jquery' );
    wp_enqueue_script( 'admin-page-script' );
  }
endif;

add_action( 'admin_enqueue_scripts', 'mawt_admin_scripts' );

if ( !function_exists( 'mawt_add_editor_styles' ) ):
  function mawt_add_editor_styles () {
    add_editor_style( 'https://fonts.googleapis.com/css?family=Raleway:400,700' );
    add_editor_style( 'css/custom_properties.css' );
    add_editor_style( 'css/custom_editor_style.css' );
  }
endif;

add_action( 'admin_init', 'mawt_add_editor_styles' );

if ( !function_exists( 'mawt_admin_menu' ) ):
  function mawt_admin_menu () {
    //remove_menu_page('edit.php'); // Entradas
    //remove_menu_page('upload.php'); // Multimedia
    //remove_menu_page('link-manager.php'); // Enlaces
    //remove_menu_page('edit.php?post_type=page'); // Páginas
    //remove_menu_page('edit-comments.php'); // Comentarios
    //remove_menu_page('themes.php'); // Apariencia
    //remove_menu_page('plugins.php'); // Plugins
    //remove_menu_page('users.php'); // Usuarios
    //remove_menu_page('tools.php'); // Herramientas
    //remove_menu_page('options-general.php'); // Ajustes
  }
endif;

add_action( 'admin_menu', 'mawt_admin_menu' );

if ( !function_exists( 'mawt_before_admin_bar' ) ):
  function mawt_before_admin_bar () {
    global $wp_admin_bar;

    /*
      search:para eliminar la caja de búsqueda
      comments:Para eliminar el aviso de comentarios
      updates:Eliminar el aviso de actualizaciones
      edit:Elimina editar entrada y páginas
      get-shortlink:Proporciona un enlace corto a esa página/post
      my-sites:Elimina el menu my sitios, si utilizas la función multisitios de wordpress
      site-name:Elimina el nombre de la web
      wp-logo:Elimina el logo(y el sub Menú)
      my-account:Elimina los enlaces a su cuenta. El ID depende de si usted tiene Avatar habilitado o no.
      view-site:Elimina el sub menú que aparece al pasar el cursor sobre el nombre de la web
      about:Elimina el enlace “Sobre WordPress
      wporg:Elimina el enlace a wordpress.org
      documentation:Elimina el enlace a la documentación oficial(Codex)
      support-forums:Elimina el enlace a los foros de ayuda
      feedback:Elimina el enlace Sugerencias
    */

    $wp_admin_bar->remove_menu('wp-logo');
    $wp_admin_bar->remove_menu('new-content');
    $wp_admin_bar->remove_menu('comments');
  }
endif;

add_action( 'wp_before_admin_bar_render', 'mawt_before_admin_bar' );

if ( !function_exists( 'mawt_admin_bar_menu' ) ):
  function mawt_admin_bar_menu () {
    global $wp_admin_bar;

    $wp_admin_bar->add_menu( array(
      'id' => 'mi_menu',
      'title' => __('Mi menu', 'mawt'),
      'href' => false
    ) );

    $wp_admin_bar->add_menu( array(
      'parent' => 'mi_menu',
      'id' => 'link-jonmircha',
      'title' => __('jonmircha', 'mawt'),
      'href' => __('https://jonmircha.com')
    ) );

    $wp_admin_bar->add_menu( array(
      'parent' => 'mi_menu',
      'id' => 'link-facebook',
      'title' => __('Facebook', 'mawt'),
      'href' => __('https://facebook.com/')
    ) );

    $wp_admin_bar->add_menu( array(
      'parent' => 'mi_menu',
      'id' => 'link-twitter',
      'title' => __('Twitter', 'mawt'),
      'href' => __('https://twitter.com/')
    ) );
  }
endif;

add_action( 'admin_bar_menu', 'mawt_admin_bar_menu' );

if ( !function_exists( 'mawt_wp_dashboard_setup' ) ):
  function mawt_wp_dashboard_setup () {
    //Actividad
    remove_meta_box( 'dashboard_activity', 'dashboard', 'normal' );
    //De un vistazo
    remove_meta_box('dashboard_right_now', 'dashboard', 'normal');
    // Comentarios recientes
    remove_meta_box('dashboard_recent_comments', 'dashboard', 'normal');
    // Enlaces entrantes
    remove_meta_box('dashboard_incoming_links', 'dashboard', 'normal');
    // Plugins
    remove_meta_box('dashboard_plugins', 'dashboard', 'normal');
    //Publicación rápida
    remove_meta_box('dashboard_quick_press', 'dashboard', 'side');
    // Borradores recientes
    remove_meta_box('dashboard_recent_drafts', 'dashboard', 'side');
    //Noticas del blog de WordPress
    remove_meta_box('dashboard_primary', 'dashboard', 'side');
    //Otras noticias de WordPress
    remove_meta_box('dashboard_secondary', 'dashboard', 'side');
  }
endif;

add_action( 'wp_dashboard_setup', 'mawt_wp_dashboard_setup' );

if ( !function_exists( 'mawt_admin_footer_text' ) ):
  function mawt_admin_footer_text () {
    return '<i>
      Sitio creado por
      <a href="https://jonmircha.com" target="_blank">@jonmircha</a>.
    </i>';
  }
endif;

add_filter( 'admin_footer_text', 'mawt_admin_footer_text' );

if ( !function_exists( 'mawt_user_contactmethods' ) ):
  function mawt_user_contactmethods ($data_user) {
    $data_user['facebook']=__('Facebook');
    $data_user['twitter']=__('Twitter');

    return $data_user;
  }
endif;

add_filter( 'user_contactmethods', 'mawt_user_contactmethods' );
?>
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
License:      GNU General Public License v2 or later
License URI:  http://www.gnu.org/licenses/gpl-2.0.html
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

if ( !function_exists( 'mawt_scripts' ) ):
  function mawt_scripts () {
    wp_register_style( 'google-fonts', 'https://fonts.googleapis.com/css?family=Raleway:400,700', array(), '1.0.0', 'all' );
    wp_register_style( 'parent-custom-properties', get_template_directory_uri() . '/css/custom_properties.css', array(), '1.0.0', 'all' );
    wp_register_style( 'parent-style', get_template_directory_uri() . '/style.css', array('google-fonts', 'parent-custom-properties'), '1.0.0', 'all' );
    wp_register_style( 'child-style', get_stylesheet_directory_uri() . '/style.css', array('google-fonts', 'parent-custom-properties', 'parent-style'), '1.0.0', 'all' );

    wp_enqueue_style( 'google-fonts' );
    wp_enqueue_style( 'parent-custom-properties' );
    wp_enqueue_style( 'parent-style' );
    wp_enqueue_style( 'child-style' );

    wp_register_script( 'parent-script', get_template_directory_uri() . '/script.js', array('jquery'), '1.0.0', true );
    wp_register_script( 'child-script', get_stylesheet_directory_uri() . '/script.js', array('jquery', 'parent-script'), '1.0.0', true );

    wp_enqueue_script( 'jquery' );
    wp_enqueue_script( 'parent-script' );
    wp_enqueue_script( 'child-script' );
  }
endif;

add_action('wp_enqueue_scripts', 'mawt_scripts');

if ( !function_exists( 'child_mawt_setup' ) ):
  function child_mawt_setup () {
    load_child_theme_textdomain( 'child_mawt', get_stylesheet_directory_uri() . '/languages' );
  }
endif;

add_action( 'after_setup_theme', 'child_mawt_setup' );
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
