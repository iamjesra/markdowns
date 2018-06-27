# Webpack

* [Introducción](#introducción)
* [Sin archivo de configuración](#sin-archivo-de-configuración)
* [Modo de producción y desarrollo](#modo-de-producción-y-desarrollo)
* [Transpilando Javascript ES6 con Babel](#transpilando-javascript-es6-con-babel)
* [Inyección de JS en HTML](#inyección-de-js-en-html)
* [Extracción de CSS](#extracción-de-css)
* [Servidor Web de Desarrollo](#servidor-web-de-desarrollo)
* [Configuración completa](#configuración-completa)

## Introducción

Es un empaquetador de archivos para aplicaciones JavaScript modernas, totalmente configurable y a diferencia de los Task Runners (como Grunt y Gulp) donde los procesos se gestionan de forma separada, en webpack, se conoce el origen y todo se compila en un único archivo.

Crea una gráfica de todas las dependencias de la aplicación. Tiene un archivo de configuración, denominado ***webpack.config.js***, donde se define todo el proceso de construcción en un objeto JS.

Webpack tiene 4 conceptos clave:

* ***Entry***: Indica cuál es el punto(s) de entrada.
* ***Output***: Indica cuál es el punto(s) de salida.
* ***Loaders***: Realizan transformaciones en los archivos.
* ***Plugins***: Realizan acciones en los archivos.

Aprende más sobre webpack:

* [Sitio Oficial](https://webpack.js.org/)
* [Conceptos básicos](https://webpack.js.org/concepts/)
* [Configuración básica](https://webpack.js.org/configuration/)
* [Loaders](https://webpack.js.org/loaders/)
* [Plugins](https://webpack.js.org/plugins/)
* [Dev Server](https://webpack.js.org/configuration/dev-server/)

[🔙 Regresar](#webpack)

## Sin archivo de configuración

Crea un nuevo directorio y colócate en el:

```
mkdir webpack-starter-kit && cd webpack-starter-kit
```

Inicia un proyecto Node:

```
npm init
```

Instala webpack y su cli:

```
npm i -D webpack webpack-cli
```

En el ***package.json*** agrega el siguiente comando:

```json
"scripts" : {
  "build" : "webpack"
}
```

Ejecuta el comando:

```
npm run build
```

El comando arrojará un error:

```js
ERROR in Entry module not found: Error: Can't resolve './src' in '~/webpack-starter-kit'
```

Webpack está buscando un punto de entrada en ./src 😱😱😱¡¡¡ Sin Archivo de configuración !!!

A partir de la versión 4 no es necesario definir el punto de entrada, tomará ***./src/index.js***  como valor predeterminado 🤓.

En versiones anteriores, el punto de entrada debe definirse dentro del archivo de configuración denominado ***webpack.config.js***.

Crea el archivo ***./src/index.js***  y escribe:

```js
console.log('Hola mundo sin configuración con Webpack')
```

Ejecuta nuevamente el comando ***build*** y webpack en automático nos habrá generado el archivo de salida ***./dist/main,js*** 😱😱😱

[🔙 Regresar](#webpack)

## Modo de producción y desarrollo

En webpack un patrón común es tener 2 archivos de configuración uno para las tareas de desarrollo y otro para las de producción.

Mientras que para proyectos grandes aún se pueden necesitar 2 archivos, en proyectos pequeños , es posible especificar el tipo de configuración en una sola línea de configuración.

Webpack 4 introduce el modo de producción  y el modo de desarrollo.

De hecho cuando corrimos el comando ***build*** la terminal nos mando un mensaje de advertencia:

```js
WARNING in configuration
The 'mode' option has not been set, webpack will fallback to 'production' for this value. Set 'mode' option to 'development' or 'production' to enable defaults for each environment.
You can also set it to 'none' to disable any default behavior. Learn more: https://webpack.js.org/concepts/mode/
```

La opción 'modo' no se ha configurado. Establezca la opción 'modo' en 'desarrollo' o 'producción' para habilitar los valores predeterminados para este entorno.

Vamos a crear un comando para cada ambiente:

```json
"scripts" : {
  "dev" : "webpack --mode development" ,
  "build" : "webpack --mode production"
}
```

Ejecutemos ambos comandos y miremos el archivo ***./dist/main.js*** después de ejecutarlos:

* ***`npm run dev`*** generará un archivo indentado y con comentarios.
* ***`npm run build`*** generará un archivo minificado y sin comentarios.

Modificando puntos de entrada y salida predeterminados:

```json
"scripts": {
  "dev": "webpack --mode development ./foo/src/index.js --output ./foo/main.js",
  "build": "webpack --mode production ./foo/src/index.js --output ./foo/main.js"
}
```

[🔙 Regresar](#webpack)

## Transpilando Javascript ES6 con Babel

Webpack por sí sólo no sabe como transpilar código ES6, pero tiene un loader que lo hace.

Instala ***babel-loader*** y sus dependencias:

```
npm i -D babel-loader babel-core babel-preset-env
```

Ahora crea el archivo ***.babelrc***  con el siguiente código:

```json
{
  "presets": [
    "env"
  ]
}
```

En este punto tenemos 2 opciones para configurar babel-loader:

1. Sin archivo de configuración.
1. Con archivo de configuración.

Escribe el siguiente código en tu archivo ***./src/index.js***

```js
const arr = [1, 2, 3],
  codeES6 = () => console.log(...arr)

window.codeES6 = codeES6

window.codeES6()
```

### Sin archivo de configuración.

Se agrega la opción ***--module-bind*** con el valor ***js=babel.loader***:

```json
"scripts": {
    "dev-babel": "webpack --mode development --module-bind js=babel-loader",
    "build-babel": "webpack --mode production --module-bind js=babel-loader"
  }
```

Ejecutemos ambos comandos y miremos el archivo ***./dist/main.js*** después de ejecutarlos:

* ***`npm run dev-babel`*** transpiló el archivo con sintaxis ES6 a ES5 indentado y con comentarios.
* ***`npm run build-babel`*** transpiló el archivo con sintaxis ES6 a ES5 minificado y sin comentarios.

### Con archivo de configuración.

Crea el archivo ***webpack.config.js*** y escribe el siguiente código:

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader'
        }
      }
    ]
  }
};
```

Ejecutemos los comandos ***dev*** y ***build*** y miremos el archivo ***./dist/main.js*** después de ejecutarlos:

* ***`npm run dev`*** transpiló el archivo con sintaxis ES6 a ES5 indentado y con comentarios, gracias a la configuración del archivo ***webpack.config.js***.
* ***`npm run build`*** transpiló el archivo con sintaxis ES6 a ES5 minificado y sin comentarios, gracias a la configuración del archivo ***webpack.config.js***.

[🔙 Regresar](#webpack)

## Inyección de JS en HTML

Para inyectar el código dinámico que genera webpack en los archivos HTML, necesita 2 dependencias : ***html-webpack-plugin*** y ***html-loader***.

Instala las dependencias:

```
npm i -D html-webpack-plugin html-loader
```

Agrega la siguiente regla al archivo ***webpack.config.js***:

```js
const HtmlWebPackPlugin = require("html-webpack-plugin");

module.exports = {
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader'
        }
      },
      {
        test: /\.html$/,
        use: [
          {
            loader: 'html-loader',
            options: { minimize: true }
          }
        ]
      }
    ]
  },
  plugins: [
    new HtmlWebPackPlugin({
      template: './src/index.html',
      filename: './index.html'
    })
  ]
};
```

Ahora crea el archivo ***./src/index.html***:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Webpack</title>
</head>
<body>
  <div id="app"></div>
</body>
</html>
```

Ejecutemos los comandos ***dev*** o ***build*** y miremos el archivo ***./dist/index.html*** después de ejecutarlos.

No es necesario incluir el JavaScript dentro del archivo HTML, webpack lo ha inyectado automáticamente y ha minificado el código 😎.

[🔙 Regresar](#webpack)

## Extracción de CSS

Webpack por sí sólo no sabe como extraer código CSS en un archivo externp, pero tiene un loader y un plugin que lo hace.

Instala las dependencias:

```
npm i -D mini-css-extract-plugin css-loader
```

Agrega la siguiente regla al archivo ***webpack.config.js***:

```js
const HtmlWebPackPlugin = require('html-webpack-plugin'),
  MiniCssExtractPlugin = require('mini-css-extract-plugin');

module.exports = {
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader'
        }
      },
      {
        test: /\.html$/,
        use: [
          {
            loader: 'html-loader',
            options: { minimize: true }
          }
        ]
      },
      {
        test: /\.css$/,
        use: [MiniCssExtractPlugin.loader, 'css-loader']
      }
    ]
  },
  plugins: [
    new HtmlWebPackPlugin({
      template: './src/index.html',
      filename: './index.html'
    }),
    new MiniCssExtractPlugin({
      filename: '[name].css',
      chunkFilename: '[id].css'
    })
  ]
};
```

Ahora crea el archivo ***./src/style.css*** con algo de código:

```css
html {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: sans-serif;
  font-size: 16px;
  color: #8DD6F9;
  background-color: #2B3A42;
}
```

Ahora importamos los estilos desde el punto de entrada, el archivo ***./src/index.js***:

```js
import style from './style.css'
```

Ejecutemos los comandos ***dev*** o ***build*** y miremos el archivo ***./dist/index.html*** después de ejecutarlos.

No es necesario incluir el CSS dentro del archivo HTML, webpack lo ha inyectado automáticamente y ha creado el archivo de estilos ***main.css*** 😎.

[🔙 Regresar](#webpack)

## Servidor Web de Desarrollo

No es muy óptimo estar ejecutando el comando ***dev*** cada vez que hacemos un cambio en nuestra aplicación lo ideal es configurar un servidor web de prueba que en automático recompile nuestro código y recargue el navegador.

Webpack, cuenta con su propio servido de desarrollo.

Instala la dependencia:

```
npm i -D webpack-dev-server
```

Agregamos el comando ***start*** a nuestro ***package.json***:

```json
"scripts": {
  "start": "webpack-dev-server --mode development --open"
}
```

Al ejecutarlo, webpack abrirá la aplicación en una ventana del navegador.

```
npm start
```

[🔙 Regresar](#webpack)

## Configuración completa

```javascript
const HtmlWebPackPlugin = require('html-webpack-plugin'),
  MiniCssExtractPlugin = require('mini-css-extract-plugin'),
  CleanWebpackPlugin = require('clean-webpack-plugin'),
  { VueLoaderPlugin } = require('vue-loader')

module.exports = {
  entry: {
    js: './src/index.js',
    vanilla: './src/hello_vanilla.js',
    react: './src/hello_react.js',
    vue: './src/hello_vue.js',
    ts: './src/hello_ts.js'
  },
  output: {
    filename: '[name].[chunkhash].js',
  },
  devtool: 'inline-source-map',
  module: {
    rules: [
      {
        test: /\.(js|jsx)$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader'
        }
      },
      {
        test: /\.html$/,
        use: [
          {
            loader: 'html-loader',
            options: { minimize: true }
          }
        ]
      },
      {
        test: /\.(css|scss)$/,
        use: [
          'style-loader', // creates style nodes from JS strings
          MiniCssExtractPlugin.loader,
          'css-loader?minimize&sourceMap', // translates CSS into CommonJS
          'postcss-loader?sourceMap',
          'resolve-url-loader',
          'sass-loader?outputStyle=compressed&sourceMap' // compiles Sass to CSS
        ],
      },
      {
        test: /\.(jpe?g|png|gif|svg|webp)$/i,
        use: [
          'file-loader?name=assets/[name].[ext]',
          'image-webpack-loader?bypassOnDebug'
        ]
      },
      {
        test: /\.(ttf|eot|woff2?|mp4|txt|xml)$/,
        use: 'file-loader?name=assets/[name].[ext]'
      },
      {
        test: /\.vue$/,
        exclude: /node_modules/,
        use: {
          loader: 'vue-loader'
        }
      },
      {
        test: /\.tsx?$/,
        exclude: /node_modules/,
        use: {
          loader: 'ts-loader'
        }
      }
    ]
  },
  plugins: [
    new CleanWebpackPlugin(['dist/*.*']),
    new MiniCssExtractPlugin({
      filename: '[name].[chunkhash].css',
      chunkFilename: '[id].css'
    }),
    new HtmlWebPackPlugin({
      template: './src/index.html',
      filename: 'index.html',
      favicon: './src/img/favicon.ico',
      hash: true,
      chunks: ['js']
    }),
    new HtmlWebPackPlugin({
      template: './src/index.html',
      filename: 'hello-vanilla.html',
      favicon: './src/img/favicon.ico',
      hash: true,
      chunks: ['vanilla']
    }),
    new HtmlWebPackPlugin({
      template: './src/index.html',
      filename: 'hello-react.html',
      favicon: './src/img/favicon.ico',
      hash: true,
      chunks: ['react']
    }),
    new HtmlWebPackPlugin({
      template: './src/index.html',
      filename: 'hello-vue.html',
      favicon: './src/img/favicon.ico',
      hash: true,
      chunks: ['vue']
    }),
    new HtmlWebPackPlugin({
      template: './src/index.html',
      filename: 'hello-ts.html',
      favicon: './src/img/favicon.ico',
      hash: true,
      chunks: ['ts']
    }),
    new VueLoaderPlugin()
  ]
}
```

[🔙 Regresar](#webpack)
