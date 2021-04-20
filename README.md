Un framework tenes que adaptarte a sus reglas, react es una librería donde somos libres de usar lo que queremos.
reactjs es creado por Facebook.
anular atrás está google
vue atrás es opensource.

# reactjs-cheatsheet
----------------------------------------

# Instalación react globalmente
----------------------------------------

Hay que tener instalado Nodejs en nustra maquina.

y en nuestro terminal:
```
npm install -g create-react-app
```
----------------------------------------
# Inicializar proyecto react
```----------------------------------------
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

# directorio ReactJS

●	public: en la cual se encuentran los archivos que no son de programación (html, imágenes)

●	src: en la cual se encuentra todo nuestro proyecto. Todo aquello que programaremos en nuestro proyecto (archivos JS con los componentes, archivos de estilos)


index.html
solo contiene:


```html
<div id="root"></div>
```

Inicializamos el proyecto con ```npm start```

## index.js

Es el punto de entrada de JavaScript para el proyecto React. Este archivo se encarga de mostrar el componente App.js en el <div id=”root”></div> del archivo HTML principal

```javascript
import App from './App';
ReactDOM.render(<App />, document.getElementById('root'));
```

archivo app.js:
```javascript
import './App.css';

function App() { return (
<div className="App">
<h1>Mi primer aplicación React</h1>
</div>
);
}

export default App;
```
El “return” de la función es el encargado de generar la Interfaz del componente.



-------------------------------
# JSX
-------------------------------
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

para ponerlo en JSX tenemos que tener 2 elementos div dentro de 1 solo div padre asi
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
  
 --------------------------
 # Componentes
 --------------------------
 
 Son fragmentos visuales de la página web

 # Creación de componentes
 
 ## Paso 1 : Creamos un archivo con el nombre del componente con extensión jsx
 
 ejemplo: primerComponente.jsx
 
 ## Paso 2 : Escrubunis el codigo del componente. (componentes basados en funciones o clases)
 ejemplo:
 
```javascript
import './App.css'; import React from 'react';

export default function PrimerComponente() { const name = 'Fabian Gonzalez';
const element = <h1>Hola {name}</h1>; return element;
}

Obligatoriamente tiene que tener un return


```

En este otro ejemplo utilizaremos una función que incluye el componente que acabamos de crear.
```javascript
import PrimerComponente from './primerComponente'; export default function App() {
return (
<div className="App">
<PrimerComponente />
</div>
)
}

```

Se considera que el archivo “primerComponente.jsx” se encuentra en la misma carpeta que App.js

----------------------------
## Return de la función
----------------------------
### SIN ELEMENTO CONTENEDOR

ejemplo:

```javascript

return (
<React.Fragment>
<td>Hello</td>
<td>World</td>
</React.Fragment>
);
```

otra forma sin elemento:
```javascript
return (
<>
<td>Hello</td>
<td>World</td>
</>
);

```

-------------------------------------------
# Comunicación en entre componentes
-------------------------------------------

Componentes que podamos cambiar su comportamiento

Comencemos con la llamada a un componente llamado PrimerComponente cuya función es mostrar el nombre que le pasamos como parámetro.

Llamada al componente HTML:
```html
    <PrimerComponente name="Fabian" />
```

```javascript
import React from 'react';

export default function PrimerComponente(props) { return (
<h1>Hola {props.name}</h1>
)
}

```

El parámetro (atributo) es name, por lo que para poder acceder a dicho parámetro hacemos uso de props.name.

Nada nos impide de llamar al componente varias veces en nuestra aplicación, por ejemplo de la siguiente forma:


```javascript
return (
<div className="App">
<PrimerComponente name="Juan Carlos" />
<PrimerComponente name="Maria" />
<PrimerComponente name="Victoria" />
</div>
)
```
De esta forma, se llamará al componente 3 veces, la primera vez el parámetro name
tendrá como valor Juan Carlos, la segunda vez Maria, y por último el valor Victoria. Esto provocará que el componente se muestre 3 veces en la aplicación.


## Uso de vectores

```javascript
const vectorNombres = [ 'Juan Carlos', 'Maria',
'Gerardo'
];
```

El método map, permite convertir los elementos de un vector, a otro formato, para el ejemplo que estamos realizando convertiremos los elementos del vector en componentes React, más precisamente en componentes PrimerComponente, y cada uno de estos componentes recibirán como parámetro el nombre de la persona que debe mostrar.

```javascript
const vectorNombres = [ 'Juan Carlos', 'Maria',
'Gerardo'
];

const respuesta = vectorNombres.map(unItem => { return <PrimerComponente name={unItem} />
})

return (
<div className="App">
{respuesta}
</div>
)
```

●	Recorreremos vectorNombres y por cada elemento

○	Convertiremos el nombre al componente PrimerComponente pasándole como parámetro el nombre de la persona (elemento del vector)

○	Cada	elemento	del	vector	nuevo	(vector	de PrimerComponente) se almacena en la variable respuesta

●	Mostramos la variable respuesta (el vector de componentes)





