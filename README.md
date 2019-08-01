# React-Redus-ES6

Referencias sobre la tecnología React JS + Redux + ES6.

Versión inicial con base al curso *React JS + Redux + ES6 Completo ¡De cero a experto!* en Udemy.com

## Tabla de contenido

- [NodeJs, Npm y Yarn](#NodeJs,-Npm-y-Yarn).
- [Puntos fuertes de React](#Puntos-fuertes-de-React).
- [Hola mundo en React](#Hola-mundo-en-React).
- [Creación de app react](#Creación-de-app-react).
- [Creación de functional component](#Creación-de-functional-component).
- [ES6 Arrow Functions](#ES6-Arrow-Functions).
- [JavaScript Debugging](#JavaScript-Debugging).
- [Object Destructuring](#Object-Destructuring).

## NodeJs, Npm y Yarn

**Node.js y Npm**

Empezamos por descargar [Node.js](https://nodejs.org/es/), versión LTS (Servicio de término largo), para el sistema operativo Windows, el cual permitirá tener un entorno de ejecución para [JavaScript](https://es.wikipedia.org/wiki/JavaScript). En la instalación, seguir el paso a paso y dejar la configuración predeterminada. Para confirmar la instalación, se puede abrir la consola de comandos de Windows y verificar la versión instalada de Node.js y [Npm](https://es.wikipedia.org/wiki/Npm):

```
node -v
```

```
npm -v
```

Node.js fue construido con el motor de JavaScript V8 de Chrome y utiliza un modelo de entrada y salida sin bloqueo controlado por **eventos**, el cual lo hace un entorno ligero y eficiente. Node.js cambió la forma en que se programa en JavaScript, ya que ahora todo el código debe funcionar de manera **asíncrona** a partir de eventos.

**Yarn**

[Yarn](https://yarnpkg.com/en/docs/install#windows-stable) nace como una alternativa a npm mucho más rápida. Yarn primero verifica todas las dependencias que se necesitan, arma el árbol de dependencias y luego los descarga en paralelo. Por último, guarda en cache todas y cada una de las dependencias descargadas, así si volvemos a descargar la misma dependencia simplemente la trae de la cache. [Fuente](https://platzi.com/blog/manejo-de-dependencias-javascript-con-yarn/)

Para instalar Yarn en Windows, descargar el instalador de la [página oficial](https://yarnpkg.com/en/docs/install#windows-stable) y seguir el paso a paso con la configuración predeterminada. Para confirmar la instalación, se puede abrir la consola de comandos de Windows y verificar la versión instalada:

```
yarn -v
```

## Puntos fuertes de React

Reac.js es una de las librerias basadas en Javascript, que permite manejar de forma eficiente la interfaz de usuarios de las aplicaciones o páginas web.

Principales puntos fuertes:

- Ecosistema: Con una gran cantidad de librerias disponibles que extiende sus características.
- Estabilidad y alta retrocompatibilidad: Permite una evolución de versiones en la libreria sin quiebres de compatibilidad.
- Perfomance: Libreria liviana lo que genera tiempos de cargas muy buenos. Rápida actualización de pantalla.

A nivel de arquitectura, React representa la **Vista** en el patrón de diseño [MVC](https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93controlador) y también, suele ser utilizado sobre Single Page Application.

Recomendación: [Ver video explicativo sobre como funciona React](https://youtu.be/lWQ69WX7-hA).

## Hola mundo en React

```js

ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);

```

Ver ejemplo práctico en [CodePen](https://es.reactjs.org/redirect-to-codepen/hello-world).

Para el ejemplo anterior, se utilizó un compilador llamado [Babel](https://babeljs.io/), que permite transformar el código JS de última generación (o con funcionalidades extras) a JS que cualquier navegador o versión de Node.js entienda. También, se utilizó [JSX](https://es.reactjs.org/docs/introducing-jsx.html), que es una extensión de la sintaxis de Javascript el cual produce **elementos** de React.

## Creación de app react

Para el ejemplo práctico, seguir los siguientes pasos:

1. Se crea una carpeta llamada *WeatherApp*.
2. En el editor de texto, en este caso vcode, ir a la opción File > Open Folder > Seleccionar la carpeta creada.
3. Presionar Control + ñ para abrir la consola de comandos en vcode.
4. Para crear un nuevo proyecto React con una Single Page Application de ejemplo, ejecutar el comando: 
```
npx create-react-app weather-app
```
Si el comando anterior falla, ejecutar los siguientes comandos uno seguido del otro:

```
npm -g create-react-app
```
```
create-react-app weather-app
```
5. Terminada la generación del nuevo proyecto, se puede ejecutar el proyecto con el siguiente comando:
```
yarn start
```
Lo anterior, tambien se puede con el siguiente comando:
```
npm start
```

*Nota: La ejecución de los comandos anteriores, ya deja configurado Babel y Yarn para ser utilizados en el proyecto.*

## Creación de functional component

En el proyecto *weather-app* creado anteriormente, seguir los siguientes pasos:

1. Se crea una nueva carpeta llamada *components* dentro de la carpeta *src* del proyecto.
2. En la carpeta *components*, crear un archivo llamado *WeatherLocation.js*.
3. En el archivo *WeatherLocation.js*, colocar el siguiente código:

```js
// Se importa el modulo react:
import React from 'react';

// Componente funcional en una constante, implementando un arrow function:
const WeatherLocation = () => (
    <div>Weather Location</div>
);

// Hacer público el componente anterior para que pueda llamarse en otra parte del proyecto:
export default WeatherLocation;
```
4. En el archivo App.js, se importa el componente funcional, para luego retornar en la función principal *App* y así mostrar el resultado en pantalla al usuario:

```js
import React from 'react';
// Se importa el componente creado anteriormente:
import WeatherLocation from './components/WeatherLocation';
import './App.css';

function App() {
  return (    
    // Se llama el componente <WeatherLocation />. 
    // Esta respuesta se retorna al index.html y se muestra en pantalla al usuario:
    <div className="App">
      Weather App (aplicación del clima)
      <WeatherLocation />  
    </div>
  );
}

export default App;

```

## ES6 Arrow Functions

La expresión de función flecha o arrow functions tiene una sintaxis más corta que una expresión de función convencional y no vincula sus propios this, arguments, super, o new.target. Las funciones flecha siempre son anónimas. Estas funciones son funciones no relacionadas con métodos y no pueden ser usadas como constructores ([fuente](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Funciones/Arrow_functions)). 

**Ejemplo función convencional**

```js

// Se define una lista de marca de carros:
var cars = {
  'Ford',
  'Toyota',
  'Mazda',
  'BMW'
}

// Función convencional que retorna la cantidad de carros almacenados en la lista cars.
// La función no es anónima, ya que posee un nombre de función.
// Para este ejemplo, no tiene parámetros de entrada.
function mi_funcion_conv(){
  return cars.length;
}

// Imprime en consola el valor que retorna la función convencional:
// > 4
console.log(mi_funcion_conv());

```

**Ejemplo de Arrow Functions**

```js

// Se define una lista de marca de carros:
var cars = {
  'Ford',
  'Toyota',
  'Mazda',
  'BMW'
}

// La función se define en una constante, por lo tanto es anónima, ya que la función no está definida.
// Para este ejemplo, no tiene parámetros de entrada.
// Si se trabaja en una única linea, no se requiere poner la palabra clave return.
// Si se requiere poner más de una linea en la función, se debe usar las llaves {}.
const mi_funcion = () => (cars.length);

// Imprime en consola el valor que retorna la función:
// > 4
console.log(mi_funcion());

```

## JavaScript Debugging

**console.log()**

Si su navegador admite la depuración, puede usar el método console.log() para mostrar los valores de JavaScript en la ventana del depurador:

```js

import React from 'react';

const Location = (props) => {
  // Imprime en la consola el valor del parámetro de entrada props:
  console.log(props);

  return <div><h1>{props.city}</h1></div>
}
```

**Configurando Breakpoints**

En la ventana del depurador, puede establecer puntos de interrupción en el código JavaScript. En cada punto de interrupción, JavaScript dejará de ejecutarse y le permitirá examinar los valores de JavaScript. Después de examinar los valores, puede reanudar la ejecución del código (normalmente con un botón de reproducción).

**Palabra clave debugger**

La palabra clave `debugger` detiene la ejecución de JavaScript y llama (si está disponible) a la función de depuración. Esto tiene la misma función que establecer un punto de interrupción en el depurador. Si no hay depuración disponible, la declaración del depurador no tiene efecto. Con el depurador encendido, este código dejará de ejecutarse antes de ejecutar la tercera línea:

```js

import React from 'react';

const Location = (props) => {
  // Imprime en la consola el valor del parámetro de entrada props:
  console.log(props);
  // Establece un punto de parada:
  debugger;

  return <div><h1>{props.city}</h1></div>
}

export default Location;

```

## Object Destructuring

El destructuring es una técnica que nos permite asignar valores a variables desde un objeto más complejo o desde arreglos con varios elementos:

Ejemplos:

```js

// Un objeto con dos propiedades
const obj = {name: 'Emiliano', nick: 'Oke'}

// Destructuring:
const {name: myName, nick: myNick} = obj

// myName = 'Emiliano'
// myNick = 'Oke'

```

```js

// Un objeto con dos propiedades
const obj = {name: 'Emiliano', nick: 'Oke'};

// Destructuring:
const {name, nick} = obj;

// name => 'Emiliano'
// nick => 'Oke'

```

```js

const myArray = ['a', 'b'];

// Destructuring
const [x, y] = myArray

// x => a
// y => b

```
Cuando se hace destructuring sobre un objeto, no es necesario tomar todas las propiedades de dicho objeto, sino que puede ser solo las que se requieran:

```js

const source = {x: 7, y: 3};

// Destructuring:
const {x} = source;

// x => 7
// y => Error de referencia.

```

Se puede establecer valores por defecto:

```js

// Destructuring el cual se está asignando un objeto vacío, pero una de las propiedades tiene un valor por defecto:
const {x, y = 1} = obj

// x => undefined
// y => 1

```

El destructuring de arrays se puede utilizar "elision". De esa forma se puede omitir uno o más elementos de determinada posición del array:

```js

// los valores 'a' y 'b' quedan sin asignación:
const [, , x, y] = ['a', 'b', 'c', 'd'];

// x => 'c'
// y => 'd'

```

También se puede utilizar el "rest operator" en conjunción con destructuring para extraer los elementos remanentes,los elementos que queden, después de tomar los primeros identificados:

```js

// el rest operator son los tres puntos ...
const [x, ...y] = ['a', 'b', 'c'];

// x => 'a'
// y => ['b', 'c']

```

Además:

- El destructuring puede utilizarse para asignaciones con `const`, `let` y `var`.
- El destructuring se puede anidar, de manera que se pueda hacer destructuring de objetos con estructuras anidadas o de arrays que tienen arrays como elementos.


