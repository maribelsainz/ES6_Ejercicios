## ¿Que es ECMAScript 6 o ES6?

Asociación Europea de fabricantes de computadoras o  European Computer Manufacturers Association (ECMA ).

ECMAScript es estándar para la implementación de JavaScript que se creó para hacer que el código sea más uniforme entre los navegadores. Por lo tanto, es una especificación de lenguaje de programación publicada por ECMA International. ECMAScript 6 también se conoce como ES6 y ECMAScript 2015.

## ¿Qué es babel?

Básicamente, Babel es un compilador de JavaScript. En otras palabras más técnicas, Babel es una cadena de herramientas que se utiliza principalmente para convertir el código ECMAScript 2015+ (ES6) en una versión de JavaScript compatible con versiones anteriores en navegadores o entornos actuales y anteriores, es decir, transformar la sintaxis actual de ES6 en versiones anteriores. Ejemplo:

```JS
// Entrada en Babel: ES6 -> función de flecha
[1, 2, 3].map((n) => n + 1);

// Salida con Babel: ES5 -> equivalente
[1, 2, 3].map(function(n) {
  return n + 1;
});
```

## Instalación de Babel

Para instalar babel en nuestro proyecto, se debe ejecutar los siguientes comando por el terminal (recuerda que debes disponer anteriormente de NodeJS y NPM).

```bash
npm install --save-dev @babel/core @babel/cli @babel/preset-env
npm install --save @babel/polyfill
```

Posteriormente, se debe crear un archivo de configuración llamado “babel.config.json” en la raíz de su proyecto con este contenido:

```JS
{
  "presets": [
    [
      "@babel/env",
      {
        "targets": {
          "edge": "17",
          "firefox": "60",
          "chrome": "67",
          "safari": "11.1",
        },
        "useBuiltIns": "usage",
      }
    ]
  ]
}
```

*Nota*: La lista de navegadores anterior es solo un ejemplo arbitrario. Tendrá que adaptarlo para los navegadores que desea admitir.

Por último, ejecutando este comando para compilar todo su código del directorio src a lib:

```bash
./node_modules/.bin/babel src --out-dir lib
```

## ¿Que es WebPack?

Webpack es un paquete de módulos estáticos para aplicaciones JavaScript modernas. Cuando webpack procesa su aplicación, internamente crea un gráfico de dependencia que asigna cada módulo que su proyecto necesita y genera uno o más paquetes.

## Instalación de ambas herramientas:

Para instalar ambas herramientas en un solo comando en la terminal, se debe ejecutar las siguientes instrucciones:

```bash
npm i webpack webpack-cli @babel/core @babel/plugin-proposal-object-rest-spread @babel/preset-env babel-loader -D
```

# Instalando Webpack y Babel, pasos:

1. Verificar si posee NodeJS y NPM con:

```bash
node -v
npm -v
```

2. Crear la carpeta del proyecto. Sin espacios entre caracteres.
3. Entrar a la carpeta mediante la terminal.
4. Inicar el instalador de NodeJS

```bash
npm init -y
```

5. Se instala el WebPack con:

```bash
npm install webpack --save-dev
```

*Nota:* si esta paso u otro de install con npm genera vulnerabilidades, se debe ejecutar el `npm audit --force` para solicionar los detalles.

6. Instalar el Webpack Cli con:

```bash
npm install webpack-cli --save-dev
```

7. Crear una carpeta de src y dentro de ella el index.js y en la carpeta raiz el index.html

8. Ejecutar en el terminal los comandos de:

```bash
npx webpack
```

Nota: se genera un WARNING debido a que estamos trabajando en modo de producción. (normal)

9. Crear el archivo en la carpeta raiz de webpack.config.js.

10. Se mueve el archivo index.html a la carpeta dist creada en pasos anteriores.

11. Crear el enlace en el archivo index.html al archivo main.js

12. En el archivo de configuración de WebPack se copia el codigo:

```JS
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js'
  }
};
```

13. Se ejecuta el comando a continuación para compilar segun la configuracion del archivo webpack.config.js:

```bash
npx webpack --config webpack.config.js
```

14. Agregar el archivo compilado al index.html en el script.

15. Agregar al archivo de packge.json el siguiente script:

```JS
"build": "webpack --mode development",
```

16. Ejecutar el comando `npm run build`

17. Agregar al archivo de packge.json el siguiente script:

```JS
 "produccion": "webpack -p",
```

18. Ejecutar el comando `npm run produccion`

19. Agregar al archivo de packge.json el siguiente script:

```JS
 "watch": "webpack --w --mode development"
```

20. Ejecutar el comando `npm run watch`

21. Instalar Babel utilizando la pagina de [Babel Setup](https://babeljs.io/setup#installation). Ejecutando el comando:

```bash
 npm install @babel/preset-env --save-dev
```

22. Crear en la raiz del repositorio el archivo .babelrc y agregar las siguientes lineas:

```JS
module: {
  rules: [
    { test: /\.js$/, exclude: /node_modules/, loader: "babel-loader" }
  ]
}
```

23. Pegar el json en el archivo .babelrc:

```JS
{
  "presets": ["@babel/preset-env"]
}
```

Primera actividad para hoy:

2. Ejemplos utilizando ES6 Modular con import y export. (parecido al desafío de hoy)

3. Investigar y socializar: Paradigma Funcional, Recursividad, Programacion orientada a Eventos, Concurrencia y procesos paralelos, callbacks.
