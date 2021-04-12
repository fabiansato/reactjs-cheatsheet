# reactjs-cheatsheet

# Instalación react globalmente

Hay que tener instalado Nodejs en nustra maquina.

y en nuestro terminal:
```
npm install -g create-react-app
```

# Inicializar proyecyo react
```
create-react-app <nombre de la aplicación>
```

ejemplo:
```
create-react-app mi-primer-proyecto
```

ejecutar proyecto (dentro de la carpeta del proyecto):
```
npm start
```

#directorio ReactJS
●	public: en la cual se encuentran los archivos que no son de programación (html, imágenes)
●	src: en la cual se encuentra todo nuestro proyecto. Todo aquello que programaremos en nuestro proyecto (archivos JS con los componentes, archivos de estilos)

index.html
solo contiene:
npm start
```html
<div id="root"></div>
npm start
```
index.js
Es el punto de entrada de JavaScript para el proyecto React. Este archivo se encarga de mostrar el componente App.js en el <div id=”root”></div> del archivo HTML principal
```javascript
import App from './App';
ReactDOM.render(<App />, document.getElementById('root'));
```

archivo app.js:

import './App.css';
```javascript
function App() { return (
<div className="App">
<h1>Mi primer aplicación React</h1>
</div>
);
}

export default App;
```
El “return” de la función es el encargado de generar la Interfaz del componente.


# JSX
Es una extensión de la sintaxis de JavaScript con la cual se generan las interfaces gráficas en React.
JSX permite “mezclar” código HTML con código JavaScript. Por ejemplo, permite asignar un fragmento HTML a una variable JavaScript y luego mostrar dicha variable.

ejemplo:
```javascript
const variableAMostrar = <h1>Título de la página</h1>;
```

ejemplo:
```javascript
function Prueba() {
const curso = 'React inicial - Fabian Gonzalez';
const variableAMostrar = <h1>Bienvenido al curso {curso}</h1>; return variableAMostrar;
}



ejemplo en el componente:
```javascript
import React from 'react';

export default function PrimerComponente() { const curso = 'React inicial - Fabian Sato';
const variableAMostrar = <h1>Bienvenido al curso {curso}</h1> return variableAMostrar;
}

}
```

Todo el código JSX debe estar contenido dentro de una etiqueta
Este código esta mal❌:
```html
<div>
<p>Uno</p>
</div>
<div>
<p>Dos</p>
</div>
```

para ponerlo en JSD tenemos que tener 2 elementos div dentro de 1 solo div padre asi
Este códdigo está bien🆗:
```html
<div>
<div>
<p>Uno</p>
</div>
<div>
<p>Dos</p>
</div>
</div>

```

Aquí sí tenemos un único elemento padre, un único <div>
