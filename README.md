# React-Redus-ES6

Referencias sobre la tecnología React JS + Redux + ES6.

Versión inicial con base al curso *React JS + Redux + ES6 Completo ¡De cero a experto!* en Udemy.com

## Tabla de contenido

- [Node.js, Npm y Yarn](#Node.js,-Npm-y-Yarn).
- [Puntos fuertes de React](#Puntos-fuertes-de-React).
- [Hola mundo en React](#Hola-mundo-en-React).

## Node.js, Npm y Yarn

**Node.js y Npm**

Empezamos por descargar [Node.js](https://nodejs.org/es/), versión LTS (Servicio de término largo), el cual permitirá tener un entorno de ejecución para [JavaScript](https://es.wikipedia.org/wiki/JavaScript). 

Node.js fue construido con el motor de JavaScript V8 de Chrome y utiliza un modelo de entrada y salida sin bloqueo controlado por **eventos**, el cual lo hace un entorno ligero y eficiente. Node.js cambió la forma en que se programa en JavaScript, ya que ahora todo el código debe funcionar de manera **asíncrona** a partir de eventos.

En Windows, para instalar Node.js, simplemente se debe seguir el paso a paso de la instalación y dejar la configuración predeterminada. Para confirmar la instalación, se puede abrir la consola de comandos de Windows y verificar la versión instalada de Node.js y [Npm](https://es.wikipedia.org/wiki/Npm):

```
npm -v
node -v
```

**Yarn**

[Yarn](https://yarnpkg.com/en/docs/install#windows-stable) es un nuevo tipo de instalador de paquetes JavaScript y gestor de dependencias lanzado por Facebook en colaboración con otros jugadores como Google donde introduce cambios en esa gestión de dependencias, en la ejecución de tareas y algunas mejoras de rendimiento, también en el cambio de enfoque en la descarga e instalación de los paquetes y en su gestión de las dependencias, por ejemplo, con Yarn el programador podrá gestionar dependencias con mayor fiabilidad [Fuente](https://es.wikipedia.org/wiki/Yarn_(Facebook)).

En Windows, para instalar Yarn, simplemente se debe seguir el paso a paso de la instalación y dejar la configuración predeterminada. Para confirmar la instalación, se puede abrir la consola de comandos de Windows y verificar la versión instalada:

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

## Hola mundo en React

```js

ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);

```

Ver ejemplo práctico en [CodePen](https://es.reactjs.org/redirect-to-codepen/hello-world).

Para el ejemplo anterior, se utilizó un compilador llamado [Babel](https://babeljs.io/), que permite transformar el código JS de última generación (o con funcionalidades extras) a JS que cualquier navegador o versión de Node.js entienda. También, se utilizó [JSX](https://es.reactjs.org/docs/introducing-jsx.html), que es una extensión de la sintaxis de Javascript el cual produce **elementos** de React.