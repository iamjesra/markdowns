# Node.js

1. [Fundamentos](#fundamentos)
1. [NPM](#npm)
1. [Express.js](#expressjs)
1. [Socket.IO](#socketio)
1. [Mongo DB](#mongo-db)
1. [](#)

## Fundamentos

### [¿Qué es Node.js?](https://nodejs.org/)

> Node.js® es un entorno de ejecución para JavaScript construido con el motor de JavaScript V8 de Chrome. Node.js usa un modelo de operaciones E/S sin bloqueo y orientado a eventos, que lo hace liviano y eficiente. El ecosistema de paquetes de Node.js, npm, es el ecosistema mas grande de librerías de código abierto en el mundo.

* [Node.js en español](https://nodejs.org/es/)
* Instalación
  * Tipos de Versiones
    * **LTS** - *Long Term Support*
    * **Current**
  * Tipos de Instalación
    * [Stand Alone](https://nodejs.org/en/download/)
    * Node Version Manager
      * [NVM para Linux / Mac](https://github.com/creationix/nvm)
      * [NVM para Windows](https://github.com/coreybutler/nvm-windows)

### Ciclo de vida de un proceso

1. Pila de Procesos (Requests & Response)
1. Pila de Subprocesos (Async Requests)
1. Cola de Callbacks (Async Responses)

![Event Loop](https://raw.githubusercontent.com/jonmircha/markdowns/master/assets/event-loop.png)

### Blocking vs Non Blocking I/O

Comensales VS Meseros

![Comensales VS Meseros](https://raw.githubusercontent.com/jonmircha/markdowns/master/assets/comensales.jpg)

### Asincronía

Establece la capacidad que tienen las operaciones del flujo de un programa para devolver el control de la ejecución al mismo (programa) antes de que hayan terminado sus procesos, mientras siguen operando en segundo plano (procesos u operaciones no bloqueantes).

Esto agiliza el proceso de ejecución y permite aumentar la escalabilidad, pero complica el razonamiento sobre el programa.

![Asincronía](https://raw.githubusercontent.com/jonmircha/markdowns/master/assets/asincronia.png)

Mecanismos asíncronos en JavaScript:

* [Callbacks](http://callbackhell.com/)
* [Promises](https://www.promisejs.org/)
* [Async Functions](https://tc39.github.io/ecmascript-asyncawait/)

[🔙 Regresar](#nodejs)

## NPM

***[Node Package Manager](https://www.npmjs.com/)***

Es el gestor de paquetes de Node.js... y de todo JavaScript.

### Paquetes en Node:

* Nativos ( _[API Core](https://nodejs.org/api/)_  )
* Externos ( _[NPM Docs](https://docs.npmjs.com/)_ )

### Proyectos en Node:

```
$ > npm init //Con asistente

$ > npm init -y //Sin asistente
```

### _**[package.json](https://docs.npmjs.com/files/package.json)**_

Es el archivo de configuración de un proyecto de node.js.

### Tipos de instalación

* Dependencia de proyecto
* Dependencia de desarrollo
* Dependencia global

Instalando un paquete:

```
$ > npm install [package]

$ > npm install [package]@3.4.12 // Versión específica

$ > npm i [package] //shortcut
```

Como dependencia de proyecto:

```
$ > npm install [package] //sin flag

$ > npm install [package] --save //con flag

$ > npm install [package] -S //shortcut
```

Como dependencia de desarrollo:

```
$ > npm install [package] --save-dev //con flag

$ > npm install [package] -D //shortcut
```

Como dependencia global:

```
$ > npm install [package] --global //con flag

$ > npm install [package] -g //shortcut
```

Instalando múltiples paquetes de forma simultanea:

```
$ > npm install [package1] [package2] [package3] --flag
```

Desinstalando paquetes:

```
$ > npm uninstall [package]

$ > npm uninstall [package]@3.4.12 // Versión específica

$ > npm un [package] //shortcut

$ > npm un [package] --save

$ > npm un [package] --save-dev

$ > npm un [package] --global
```

Cuando un proyecto tiene registradas sus dependencias en el _**package.json**_ se pueden instalar simplemente con el comando:

```
$ > npm install
```

### Paquetes y Módulos

Podemos importar y exportar módulos en Node de 2 formas:

1. CommonJS ( estándar y nativa )
1. Módulos +ES6 ( se requiere usar Babel )

CommonJS:

```javascript
//exportar
module.exports = myModule

//importar
const myModule = require('./myModule')
```

Módulos +ES6:

```javascript
//exportar
export const myModule

//importar
import myModule from './myModule'
```

### Scripts NPM

Podemos ejecutar comandos desde la cli mediante la definición de scripts en el archivo _package.json_.

```
"scripts": {
  "sass": "node-sass -o ./dist/ ./src/",
  "dev-server": "browser-sync start --server --files public",
  "start": "nodemon app.js"
 }

$ > npm run sass
$ > npm run dev-server
$ > npm start
```

_**npm start**_ no necesita especificar la palabra '_run_' para ejecutarse. Generalmente es el script estandar para iniciar un proyecto.

[🔙 Regresar](#nodejs)

## [Express.js](http://expressjs.com/)

### ¿Qué es?

> Express es una infraestructura de aplicaciones web Node.js mínima y flexible que proporciona un conjunto sólido de características para las aplicaciones web y móviles.<br><br>
> Con miles de métodos de programa de utilidad HTTP y middleware a su disposición, la creación de una API sólida es rápida y sencilla.<br><br>
>Express proporciona una delgada capa de características de aplicación web básicas, que no ocultan las características de Node.js que tanto ama y conoce.

* [Express.js en español](http://expressjs.com/es)
* [Documentación](http://expressjs.com/en/4x/api.html)
* Express API:
  * [Express](http://expressjs.com/4x/api.html#express)
  * [Application](http://expressjs.com/4x/api.html#app)
  * [Require](http://expressjs.com/4x/api.html#req)
  * [Response](http://expressjs.com/4x/api.html#res)
  * [Router](http://expressjs.com/4x/api.html#router)
* [Generador de Express](http://expressjs.com/en/starter/generator.html)

#### Características

* Estrictamente web (microframework).
* Sencillo, flexible y minimalista.
* Muy popular.
* Se adapta muy bien a la filosofía de Node.
* Similar a Sinatra, Sylex, Flask, Spark, etc.

#### Útil para:

* Rutas.
* Parámetros.
* Formularios.
* Subida de ficheros.
* Cookies.
* Sesiones.
* Templates.

#### NO es útil para:

* Base de datos / ORM.
* Autenticación de usuarios.
* Seguridad.
* Migraciones.
* Deployment.
* Testing.
* Organización del código.

#### CONCRETAMENTE:

* Construye sobre `http`.
* Procesa la petición a través middlewares.
* Asocia rutas a manejadores.
* Procesa los objetos de petición y respuesta.
* Visualiza templates.
* Nosotros escogemos qué middlewares queremos usar, y en qué orden.

#### Frameworks inspirados o basados en Express:

* [Koa](https://koajs.com/)
* [Hapi](https://hapijs.com/)
* [Kraken](http://krakenjs.com/)
* [Sails](https://sailsjs.com/)
* [Adonis](https://adonisjs.com/)
* [Total](https://www.totaljs.com/)
* [Locomotive](http://www.locomotivejs.org/)
* [Geddy](http://geddyjs.org/)

### Middlewares

Express.js se ayuda de paquetes adicionales, para mantener su core simple y minimalista: los _[Middlewares](http://expressjs.com/en/guide/using-middleware.html)_.

Son módulos _**plug and play**_ que se pueden apilar arbitrariamente en cualquier orden y proveen cierta funcionalidad.

Hay de dos tipos:

1. **Filtros**: procesan tráfico entrante/saliente, pero no responden a ninguna petición. Por ejemplo `bodyParser`.
1. **Proveedores**: ofrecen respuestas automáticas a algún tipo de petición. Por ejemplo `static`.

Escribir middlewares para express es muy sencillo:

* Una función que recibe 3 parámetros: `req`, `res`, `next`.
* Al terminar su tarea, tiene que invocar a `next()`:
  * **Sin parámetro**: se invoca al siguiente middleware del stack.
  * **Con parámetro**: se cambia la ruta a lo que se pase como parámetro.
* Dos maneras de activar middlewares:
  1. **Globalmente**, activos para toda la app.
  1. **Locales**. para ciertas rutas.

### Templates Engines

Express tiene un mecanismo para renderizar plantillas que es:

* Agnóstico
* Modular
* Simple

Templates compatibles con Express:

* [Jade](http://jade-lang.com/)
* [Pug](https://pugjs.org/)
* [EJS](http://ejs.co/)
* [Handlebars](http://handlebarsjs.com/)
* [Hogan.js](http://twitter.github.io/hogan.js/)
* [Dust](http://www.dustjs.com/)
* [Twig.js](https://github.com/twigjs/twig.js)
* [Vash](https://github.com/kirbysayshi/vash)

[🔙 Regresar](#nodejs)

## [Socket.IO](https://socket.io/)

### ¿Qué es?

* Una librería para manipular websockets.
* Muy popular.
* Fallback para navegadores obsoletos.
* Muy fácil de usar.
* Servidor / Cliente.
* [API Docs](https://socket.io/docs/).

### ¿Qué son los [WebSockets](https://www.websocket.org/)?

* Protocolo de comunicación.
* Full-duplex.
* Una sola conexión permanente.
* Stream de mensajes.
* Contenido en tiempo real.
* El cliente puede enviar y recibir datos en tiempo real.
* Orientado a eventos (mensajes).
* Siempre conectado.
* Baja latencia.
* Son fundamentales, para:
  * Aplicaciones colaborativas.
  * Juegos multijugador.
  * Envío de datos.
  * Cargar recursos.
* En resumen: "tiempo real" en vez de "a petición".

[🔙 Regresar](#nodejs)

## Mongo DB

[🔙 Regresar](#nodejs)

[🔙 Regresar](#nodejs)
