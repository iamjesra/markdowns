# WordPress

* [Introducción](#introducción)
* [Instalación](#instalación)
* [Generando Contenido](#generando-contenido)
* [Plugins](#plugins)
* [Optimización](#optimización)
  * [SEO](#seo)
  * [WPO](#wpo)
  * [Seguridad](#seguridad)
* [Backup](#backup)

## Introducción

> Trusted by the Best
> 30% of the web uses WordPress, from hobby blogs to the biggest news sites online.

### Características

* Es un CMS (Content Management System).
* El CMS más utilizado en el mundo.
* Open Source / Licencia GPL.
* Extensible.
* Fuerte Comunidad multiidioma.
* Nacio en 2003 como plataforma de blogs.
* [Matt Mullenger](https://twitter.com/photomatt) creador y fundador de [Automattic](https://automattic.com/).
* A WordPress le gusta el jazz.
* WordPress tiene [apps nativas](https://wordpress.org/mobile/).

### ¿Quién usa WordPress?

* [WordPress.org](https://wordpress.org/)
* [WordPress.com](https://wordpress.com/)
* [La Casa Blanca](https://www.whitehouse.gov/)
* [jQuery](http://jquery.com/)
* [CSS-TRICKS](https://css-tricks.com/)
* [Tech Crunch](https://techcrunch.com/)
* [Variety](http://variety.com/)
* [AMC](http://www.amc.com/)
* [BBC America](http://www.bbcamerica.com/)
* [CNN en Español](http://cnnespanol.cnn.com/)
* [TIME](http://time.com/)
* [WIRED](https://www.wired.com/)
* [Sony Music](https://www.sonymusic.com/)
* [The Harvad Gazette](https://news.harvard.edu/gazette/)
* [The Mozilla Blog](https://blog.mozilla.org/)
* [Adobe Blogs](http://blogs.adobe.com/)
* [PlayStation Blog](https://blog.es.playstation.com/)
* [Spotify News](https://news.spotify.com/es/)
* [The New York Times](https://www.nytco.com/)
* [Mercedes-Benz](https://www.mercedes-benz.com/en/)
* [Silvester Stallone](https://sylvesterstallone.com/)
* [The Rolling Stones](http://www.rollingstones.com/)
* [Justin Bieber](http://www.justinbiebermusic.com/)
* y muchos más...

### Ambientes de desarrollo

* [Bitnami](https://bitnami.com/stacks)
* [AMPPS](https://www.ampps.com/)
* [MAMP](https://www.mamp.info/en/)
* [WAMP](http://www.wampserver.com/en/)
* [XAMPP](https://www.apachefriends.org/es/index.html)

**[🔙 Regresar](#wordpress)**

## Instalación

1. Descarga [WordPress](https://wordpress.org/).
1. Descomprime el **`.zip`** de  WordPress en la carpeta pública de tu servidor (local o remoto).
1. Renombra la carpeta wordpress por un nombre relacionado con el proyecto a desarrollar.
1. Crea una  base de datos en MySQL para el nuevo proyecto, lo puedes hacer desde la aplicación web **phpMyAdmin** que se incluye en la mayoría de ambientes de desarrollo para WordPress.
1. Busca el archivo **`wp-config-sample.php`** y renómbralo como **`wp-config.php`**.
1. Abre el archivo **`wp-config.php`** y editar los siguientes datos:
    ```php
      define('DB_NAME', 'database_name_here');
      define('DB_USER', 'username_here');
      define('DB_PASSWORD', 'password_here');
      define('DB_HOST', 'localhost');
      define('DB_CHARSET', 'utf8');
      define('DB_COLLATE', '');

      define('AUTH_KEY',         'put your unique phrase here');
      define('SECURE_AUTH_KEY',  'put your unique phrase here');
      define('LOGGED_IN_KEY',    'put your unique phrase here');
      define('NONCE_KEY',        'put your unique phrase here');
      define('AUTH_SALT',        'put your unique phrase here');
      define('SECURE_AUTH_SALT', 'put your unique phrase here');
      define('LOGGED_IN_SALT',   'put your unique phrase here');
      define('NONCE_SALT',       'put your unique phrase here');

      $table_prefix  = 'wp_';
    ```
1. Ejecuta la carpeta del sitio en el navegador.
1. Llena la información que se te pide:
    * Título del sitio.
    * Nombre del usuario **Administrador**.
    * Contraseña del **Administrador**.
    * Correo electrónico del **Administrador**.
    * Elegir la **Visibilidad para los buscadores**.
    * ¡Listo!
1. Una vez instalado:
    * Para ver WP como usuario administrador:
      * **http:// ruta-del-sitio/wp-login.php** o
      * **http:// ruta-del-sitio/wp-admin**
    * Para ver WP como usuario visitante:
      * **http:// ruta-del-sitio**

**Nota:** Si te quedan dudas puedes ver el siguiente **[video](https://www.youtube.com/watch?v=lE4wO3C4Eyg)**.

**[🔙 Regresar](#wordpress)**

##  Generando Contenido

### Taxonomía

Clasificación concreta de términos o conceptos, que pueden formar parte de una jerarquía o no.

En WordPress es la forma en como se organiza el contenido de nuestro sitio y lo hace a través de:

* Entradas **(Publicación dinámica)**.
* Páginas **(Publicación estática)**.
* Categorías **(Clasifican el contenido, son jerárquicas)**.
* Etiquetas **(Palabras clave, no son jerárquicas)**.

#### Entradas

Son las publicaciones dinámicas de nuestro sitio, pueden tener asociadas más de una categoría, si no le especificamos una, WP le asignará la categoría que trae por defecto: "Sin Categoría". Podemos agregarle (o no) tantas etiquetas como sean necesarias.

#### Páginas

Son las publicaciones estáticas de nuestro sitio, usadas para mostrar contenido que difícilmente cambiará, por ejemplo, la sección de contacto o acerca. No se les puede asignar categorías ni etiquetas.

#### Categorías

Son utilizadas para agrupar las entradas, mantienen un orden jerárquico por lo que podemos generar subcategorías. Se pueden ver como temas generales o tablas de contenido que clasifican las entradas del sitio.

#### Etiquetas

Son utilizadas para relacionar las entradas entre sí. Son microdatos que describen detalles específicos de las entradas. Sirven como palabras claves del contenido de las entradas.

#### ¿Cuál es la diferencia entre categorías y etiquetas?

En palabras de [Matt Mullenweg](https://en.blog.wordpress.com/2007/09/22/tags-and-categories/) creador de WordPress:

>  Lo intentaré explicar de la mejor forma que sé. Las categorías son cosas que creas con anterioridad y sólo tienes unas pocas. Imagínatelas como las secciones de tu web. Como si fueran los letreros en los pasillos de un supermercado. En cambio, las etiquetas son palabras clave que conectas una sola vez a una entrada. Puedes añadir una etiqueta a una entrada y nunca más volver a utilizar dicha etiqueta. Las categorías tienen el propósito de ser permanentes, mientras que las etiquetas son efímeras.

### Enlaces importantes de configuración

* [Embeds (Objetos Incrustados)](https://codex.wordpress.org/Embeds).
* [Servicios de Actualización](https://codex.wordpress.org/Update_Services).
* [Roles y Capacidades](https://codex.wordpress.org/Roles_and_Capabilities).
* [Gravatar](http://es.gravatar.com/).
* [Temas](https://wordpress.org/themes/).
* [Plugins](https://wordpress.org/plugins/).

**[🔙 Regresar](#wordpress)**

## Plugins

### Builders:

* [Elementor](https://wordpress.org/plugins/elementor/).
* [Divi](https://www.elegantthemes.com/gallery/divi/).
* [Page Builder](https://wordpress.org/plugins/siteorigin-panels/).

### Formularios

* [Contact Form 7](https://wordpress.org/plugins/contact-form-7/)
* [Rainmaker Form – Best Forms Plugin on WP](https://wordpress.org/plugins/icegram-rainmaker/)

### Optimización de Imágenes

* [EWWW Image Optimizer](https://wordpress.org/plugins/ewww-image-optimizer/)
* [Regenerate Thumbnails](https://wordpress.org/plugins/regenerate-thumbnails/)
* [Compress JPEG & PNG images](https://wordpress.org/plugins/tiny-compress-images/)
* [Manual Image Crop](https://wordpress.org/plugins/manual-image-crop/)

### Galerías y Sliders

* [HUGE-IT Gallery](https://huge-it.com/wordpress-gallery/)
* [WP Slick Slider and Image Carousel](https://wordpress.org/plugins/wp-slick-slider-and-image-carousel/)
* [Slider WD](https://wordpress.org/plugins/slider-wd/)
* [Post Slider](https://wordpress.org/plugins/post-slider-wd/)
* [Lightbox Pop](https://wordpress.org/plugins/lightbox-pop/)

### Theme Switchers

* [Any Mobile Theme Switcher](https://wordpress.org/plugins/any-mobile-theme-switcher/)
* [User Agent Themes Switcher](https://wordpress.org/plugins/useragent-themes-switcher/)

### Multimedia

* [Responsify WP](https://es-mx.wordpress.org/plugins/responsify-wp/)
* [RICG Responsive Images](https://wordpress.org/plugins/ricg-responsive-images/)
* [Advanced Responsive Video Embedder](https://wordpress.org/plugins/advanced-responsive-video-embedder/)

### Categorias y Entradas

* [No Category Base (WPML)](https://wordpress.org/plugins/no-category-base-wpml/)
* [WP No Base Permalink](https://wordpress.org/plugins/wp-no-base-permalink/)
* [WP Most Popular](https://wordpress.org/plugins/wp-most-popular/)
* [Multiple Featured Images](https://wordpress.org/plugins/multiple-featured-images/)

### Social Media Share

* [Simple Share Buttons Adder](https://wordpress.org/plugins/simple-share-buttons-adder/)
* [Social Share Buttons - Social Pug](https://wordpress.org/plugins/social-pug/)
* [Social Count Plus](https://wordpress.org/plugins/social-count-plus/)
* [Share Buttons by Add This](https://wordpress.org/plugins/addthis/)
* [Social Counter for WordPress - AccessPress Social Counter](https://wordpress.org/plugins/accesspress-social-counter/)

### Social Media Tags

* [Social Meta by Brozzme](https://wordpress.org/plugins/wp-social-meta-by-brozzme/)
* [Meta Tags by DivPusher](https://wordpress.org/plugins/meta-tags/)
* [Keyword Meta by Appleuser](https://wordpress.org/plugins/keyword-meta/)
* [Open Graph](https://wordpress.org/plugins/opengraph/)
* [Content Cards](https://wordpress.org/plugins/content-cards/)

### Comentarios

* [Akismet](https://wordpress.org/plugins/akismet/)
* [Disqus Conditional Load](https://wordpress.org/plugins/disqus-conditional-load/)
* [Disqus Comment System](https://wordpress.org/plugins/disqus-comment-system/)
* [WordPress Social Comments Plugin for Facebook Comments, Google+ Comments, Disqus Comments](https://wordpress.org/plugins/heateor-social-comments/)
* [WordPress Social Share, Social Login and Social Comments Plugin – Super Socializer](https://wordpress.org/plugins/super-socializer/)

### Campos adicionales

* [Advanced Custom Fields](https://wordpress.org/plugins/advanced-custom-fields/)
* [Meta Box](https://metabox.io/)

### Personalización de la página de Login

* [Custom Login Page Customizer](https://wordpress.org/plugins/login-customizer/)
* [WP Customize Login Page](https://wordpress.org/plugins/wp-customize-login-page/)
* [Customize WordPress Login Page](https://wordpress.org/plugins/admin-custom-login/)
* [Custom Login Page by SeedProd](https://wordpress.org/plugins/custom-login-page-wp/)

### Paginación

* [WP-PageNavi](https://wordpress.org/plugins/wp-pagenavi/)
* [Infinite Scroll](http://www.infinite-scroll.com/)
* [Infinite Scroll and Load More Ajax Pagination](https://wordpress.org/plugins/infinite-scroll-and-load-more-ajax-pagination/)

### Traducciones

* [Loco Translate](https://wordpress.org/plugins/loco-translate/)
* [WP Translate – Translate WordPress](https://wordpress.org/plugins/wp-translate/)
* [TranslatePress – Translate Multilingual sites](https://wordpress.org/plugins/translatepress-multilingual/)

### Menús

* [Max Mega Menu](https://wordpress.org/plugins/megamenu/)
* [WP Mobile Menu](https://wordpress.org/plugins/mobile-menu/)
* [Responsive Menu](https://wordpress.org/plugins/responsive-menu/)

### Cookies

* [Cookie Consent](https://wordpress.org/plugins/uk-cookie-consent/)
* [Cookie Bar](https://wordpress.org/plugins/cookie-bar/)

### Gestores de archivos

* [WP File Manager](https://wordpress.org/plugins/wp-file-manager/)
* [File Manager](https://wordpress.org/plugins/file-manager/)

### Servicios de Google

* [Google Analytics for WordPress](https://es.wordpress.org/plugins/analytics-for-wp/)
* [Google Analytics](https://wordpress.org/plugins/googleanalytics/)
* [Google Analytics by MonsterInsights](https://wordpress.org/plugins/google-analytics-for-wordpress/)
* [Google Analytics Dashboard for WP (GADWP)](https://wordpress.org/plugins/google-analytics-dashboard-for-wp/)
* [WP Google Fonts](https://wordpress.org/plugins/wp-google-fonts/)
* [Google Map](https://wordpress.org/plugins/gmap-embed/)
* [Google Map](https://wordpress.org/plugins/wd-google-maps/)
* [YouTube Embed, Playlist and Popup](https://wordpress.org/plugins/youtube-video-player/)
* [YouTube EmbedPlus](https://wordpress.org/plugins/youtube-embed-plus/)
* [Translate WordPress with GTranslate](https://wordpress.org/plugins/gtranslate/)

### Listas de correo

* [Email Subscribers & Newsletters](https://wordpress.org/plugins/email-subscribers/)
* [MailChimp for WP](https://wordpress.org/plugins/mailchimp-for-wp/)
* [MailPoet Newsletters](https://wordpress.org/plugins/wysija-newsletters/)

### Inserción de código

* [Insert PHP](https://wordpress.org/plugins/insert-php/)
* [Easy Custom Css/Js](https://wordpress.org/plugins/easy-custom-cssjs/)
* [Simple Custom CSS](https://wordpress.org/plugins/simple-custom-css/)
* [Simple Custom CSS and JS](https://wordpress.org/plugins/custom-css-js/)
* [Sublime Custom CSS Editor](https://wordpress.org/plugins/sublime-custom-css-editor/)
* [Sublime Custom JS Editor](https://wordpress.org/plugins/sublime-custom-js-editor/)
* [Ajax Custom CSS/JS](https://wordpress.org/plugins/ajax-awesome-css/)
* [WP-SCSS](https://wordpress.org/plugins/wp-scss/)

### Roles y usuarios

* [Paid Memberships Pro](https://wordpress.org/plugins/paid-memberships-pro/)
* [User Roles and Capabilities](https://wordpress.org/plugins/user-roles-and-capabilities/)
* [User Groups](https://wordpress.org/plugins/user-groups/)

### Foros y comunidades

* [BuddyPress](https://wordpress.org/plugins/buddypress/)
* [bbPress](https://wordpress.org/plugins/bbpress/)

### Comercio electrónico

* [WooCommerce](https://wordpress.org/plugins/woocommerce/)

**[🔙 Regresar](#wordpress)**

##  Optimización

### SEO

**Search Engine Optimization**  (Optimización en Motores de Búsqueda): Como los motores de busqueda indexan los sitios y sus urls.

Implica:

* Indexación
* SERP (**Search Engine Results Page**)
* URL
* Keywords

Adicionalmente en WordPress implica, uso correcto de:
  * Paginación
  * Taxonomía
  * Entradas
  * Páginas
  * Categorías
  * Etiquetas
  * Páginas de Autor

**El problemas por excelencia: CONTENIDO DUPLICADO.**

URLs diferentes para un mismo recurso. Páginas que suelen compartir el mismo contenido en WordPress:

* Categorías y etiquetas.
* Categorías y author.
* Categorías y paginación.
* Home y archivos del mes.
* Entradas con comentarios paginados.

**Soluciones:**

* Una categoría por entrada.
* Usar etiquetas con cautela, que existan claras diferencias entre éstas y las categorías.
* Si varias personas colaboran en el sitio ten una guía de contenido para la correcta asignación de etiquetas y categorías. Así evitaras el sobreuso.
* Indexa al autor cuando existan más de uno generando contenido.
* Usa urls canónicas.

#### Plugins SEO

* [All in One SEO Pack](https://es.wordpress.org/plugins/all-in-one-seo-pack/)
* [Jetpack by WordPress.com](https://wordpress.org/plugins/jetpack/)
* [Yoast SEO](https://wordpress.org/plugins/wordpress-seo/)
* [WP Meta SEO](https://es.wordpress.org/plugins/wp-meta-seo/)
* [Redirection](https://es.wordpress.org/plugins/redirection/)
* [Broken Link Checker](https://es.wordpress.org/plugins/broken-link-checker/)
* [itemprop WP for SERP/SEO Rich snippets](https://wordpress.org/plugins/itempropwp/)

**[🔙 Regresar](#wordpress)**

### WPO

**Web Performance Optimization** u optimización del rendimiento web son técnicas que se encargan de optimizar el tiempo de carga de una web.

El término **WPO** se dio a conocer de forma masiva a raíz de la incorporación del "***landing page load time***" al algoritmo de Google en 2008, en el que se afirmaba que la velocidad de carga de un sitio era uno de los factores que el buscador tomaba en cuenta a la hora de posicionar las páginas en sus **SERP's**.

Todos los CMS suelen estar **poco optimizados** en este aspecto por lo que debes cuidar los siguientes aspectos:

* Tu sitio debe cargar en menos de 3 segundos.
* Control del ***Time To First Byte - TTFB***, que es el tiempo que tarda el servidor en comenzar a enviar contenido. Se puede afectar por rendimiento de **hosting** o **programación**.
* Testea las velocidades de toda la web: home, páginas, entradas, búsquedas, productos, perfiles, etc.
* Cachea el contenido, todo irá mucho más rápido y los recursos del servidor disminuirán.
* Habilita el GZip (con esto se mejora entre un 30% y un 70%).
* Optimizar las imágenes antes de subirlas a la web.
* Minificar código (CSS, JS y HTML).
* Utilizar recursos asíncronos.
* Usa **CDN's**, si paralelizas la carga y repartes la información puedes agilizar la velocidad de la web.
* Eliminar los errores del cliente 4XX y del servidor 5XX.

#### Plugins WPO

* [WP Super Cache](https://wordpress.org/plugins/wp-super-cache/)
* [W3 Total Cache](https://wordpress.org/plugins/w3-total-cache/)
* [Autoptimize](https://wordpress.org/plugins/autoptimize/)
* [P3 (Plugin Performance Profiler)](https://es.wordpress.org/plugins/p3-profiler/)

**[🔙 Regresar](#wordpress)**

### Seguridad

* Mantén actualizado el core, los plugins y los themes  de WordPress.
* Elimina los plugins y themes innecesarios.
* Haz un BackUp de tu base de datos y de tus archivos periódicamente.
* Utiliza una contraseña difícil.
* Cambia el prefijo de la Base de Datos.
* Asígnale los permisos correctos a las carpetas de tu servidor.
* Evita la exploración de las carpetas.
* Protege el archivo wp-config.php.
* No muestres la versión de tu WordPress.

#### Plugins Seguridad

* [All In One WP Security & Firewall](https://wordpress.org/plugins/all-in-one-wp-security-and-firewall/)
* [iThemes Security (anteriormente Better WP Security)](https://es.wordpress.org/plugins/better-wp-security/)
* [Sucuri Security](https://es.wordpress.org/plugins/sucuri-scanner/)
* [Simple Optimizer](https://wordpress.org/plugins/simple-optimizer/)
* [Brozzme DB Prefix](https://es.wordpress.org/plugins/brozzme-db-prefix-change/)
* [WP Limit Login Attempts](https://es.wordpress.org/plugins/wp-limit-login-attempts/)

**[🔙 Regresar](#wordpress)**

## Backup

### Backup Manual

1. Respalda toda la carpeta WordPress ( wp-admin, wp-includes, wp-content, archivos sueltos ).
1. Carga o Descarga el respaldo vía FTP, SSH, Git, etc.
1. Exportar en formato **`.sql`** la BD desde **phpMyAdmin**.
1. Abre el archivo **.sql** y con ayuda del comando buscar y reemplazar de tu editor de código favorito, reemplaza todas las coincidencias de la ruta actual del sitio por la nueva.
1. Modifica las rutas de las siguientes lineas del archivo **.htaccess**:
    * **RewriteBase**
    * **RewriteRule**
    ```htaccess
      # BEGIN WordPress
      <IfModule mod_rewrite.c>
        RewriteEngine On
        RewriteBase /carpeta-sitio-wp/
        RewriteRule ^index\.php$ - [L]
        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteCond %{REQUEST_FILENAME} !-d
        RewriteRule ./carpeta-sitio-wp/index.php [L]
      </IfModule>
      # END WordPress
    ```
1. Modifica los nuevos datos de la base de datos en el archivo **wp-config.php**
    ```php
      define('DB_NAME', 'database_name_here');
      define('DB_USER', 'username_here');
      define('DB_PASSWORD', 'password_here');
      define('DB_HOST', 'localhost');
    ```

1. Importa el archivo **`.sql`** modificado de la BD, en el nuevo servidor.
1. Copia el respaldo de la carpeta WordPress en la nueva ubicación del nuevo servidor.
1. ¡Listo!, cruza los dedos para que nada estalle.

**Nota:** Si te quedan dudas puedes ver el siguiente **[video](https://www.youtube.com/watch?v=4IRnuFqinlI)**.

### Backup con Plugins:

* [Duplicator](https://wordpress.org/plugins/duplicator/)
* [All-in-One WP Migration](https://wordpress.org/plugins/all-in-one-wp-migration/)
* [BackWPup - WordPress Backup Plugin](https://wordpress.org/plugins/backwpup/)
* [Backup & Restore Dropbox](https://es.wordpress.org/plugins/dropbox-backup/)

**[🔙 Regresar](#wordpress)**
