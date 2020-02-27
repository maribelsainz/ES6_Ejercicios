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
## Instalación de Babel.

Para instalar babel en nuestro proyecto, se debe ejecutar los siguientes comando por el terminal (recuerda que debes disponer anteriormente de NodeJS y NPM).

```
npm install --save-dev @babel/core @babel/cli @babel/preset-env
npm install --save @babel/polyfill
```

Posteriormente, se debe crear un archivo de configuración llamado “babel.config.json” en la raíz de su proyecto con este contenido:
```json
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
