# Node.js

## [¿Qué es Node.js?](https://nodejs.org/)

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

## Ciclo de vida de un proceso

1. Pila de Procesos (Requests & Response)
1. Pila de Subprocesos (Async Requests)
1. Cola de Callbacks (Async Responses)

![Event Loop](https://raw.githubusercontent.com/jonmircha/markdowns/master/assets/event-loop.png)

## Blocking vs Non Blocking I/O

Comensales VS Meseros

![Comensales VS Meseros](https://raw.githubusercontent.com/jonmircha/markdowns/master/assets/comensales.jpg)

## Asincronía

Establece la capacidad que tienen las operaciones del flujo de un programa para devolver el control de la ejecución al mismo (programa) antes de que hayan terminado sus procesos, mientras siguen operando en segundo plano (procesos u operaciones no bloqueantes).

Esto agiliza el proceso de ejecución y permite aumentar la escalabilidad, pero complica el razonamiento sobre el programa.

![Asincronía](https://raw.githubusercontent.com/jonmircha/markdowns/master/assets/asincronia.png)

Mecanismos asíncronos en JavaScript:

* [Callbacks](http://callbackhell.com/)
* [Promises](https://www.promisejs.org/)
* [Async Functions](https://tc39.github.io/ecmascript-asyncawait/)

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

## Paquetes y Módulos

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

## Scripts NPM

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
