![fixtergeek logo](https://fixter.camp/static/media/geek_completo.7e1e87a7.png)

## Normalización de base de datos

#### ¿Qué vamos a aprender?

- Qué es normalización de base de datos y porqué es importante
- Cuales son los niveles de normalización
- Cómo se usa la normalización en bases de datos como SQL o No-SQL
- Cómo implementar normalización en Firebase
- Crear una funcion para hacer un populate de modelos

## ¿Qué es normalización?

La normalización de bases de datos es propuesta para evitar la redundancia de la información y favorecer su integridad, ya que sin ella es muy probable que los datos tiendan a repetirce, fué propuesta por Edgar F. Codd cómo parte integral de su "relational model".
En palabras humanas, la normalización tiene que ver con relacionar diferentes modelos en una base de datos con respecto únicamente a una llave única, mejor conocida cómo "foreign key" o llave foranea, el nombre precisamente porque se refiere a un documento que vive en otra colección fuerá de la actual.
por ejemplo; si tenemos un modelo Postre y un modelo Ingrediente, el modelo postre puede tener una lista de ingredientes pero estos ingredientes ya existen en nuestra base de datos en la forma de otro modelo, entonces, para evitar la redundancia o la repetición de estos datos, acudimos a las llaves foraneas de cada ingrediente para no repetir toda la información del ingrediente, y solo referenciarlo por medio de una llave única que lo representa. Nuestro modelo Postre quedaría algo así: {ingredientes: [id1,id2,id150,id24,id100]}.
Pero eso puede abrir otra puerta a la duda; ¿Qué es un modelo?

### Modelo de datos

Cuando trabajamos con bases de datos en una aplicación web, es importante definir muy bien nuestros modelos, un modelo de datos describiendolo de la forma estricta es: Las estructuras de datos de la base: El tipo de los datos que hay en la base y la forma en que se relacionan.
Pero una vez más intentando humanizar esta definición, un modelo de datos es el molde con el que vamos a representar cómo guardaremos la información de nuestra app en la base de datos, esto es que cada que guardemos un Postre en nuestra base de datos, estamos esperando que tenga una forma determinada.
Cuando seguimos este patron terminamos construyendo un modelo, que representa la forma del documento que vamos a almacenar en nuestra base de datos. En bases de datos no-SQL como lo es Firebase Firestore o MongoDB, hablamos de documentos en collecciones, las cuales representan una collección de estos documentos que tienen la forma de nuestro modelo, mientras que en SQL, hablamos de "records" o filas en una tabla, las cuales tienen diferentes columnas, un modelo también puede definir la forma de estos "records" mismos que viven en vez de en colecciones, en tablas.
Cualquiera que sea la tecnología que elijamos, un modelo de datos nos ayudará a darle forma a nuestra base de datos.

### Bases de datos no-SQL

Es importante no confundir "no-SQL" con "no-Relacional", las bases de datos no relacionales son ya muy escasas, pero aún se les llama de esta manera a las bases de datos no-SQL solo por mala costumbre, el decir no-relacional se intuye que la base de datos no soporta normalización, y que no se pueden relacionar datos de diferentes modelos o colecciones, pero esto no es así en la mayoría de las bases de datos, incluso en bases de datos no-relacionales se pueden crear normalizaciones lo que automáticamente las convierte en SI-relacionales.
Es por ello que nosotros las llamaremos "noSQL" qué es un nombre más apropiado, pues no usaremos este micro lenguaje para utilizarlas, si no solo JavaScript o las API de las mismas bases de datos, como MongoDB o Firestore.

### Niveles de normalización

Codd creo el concepto de normalización y lo que ahora se conoce como primera forma de normalización "first normal form" (1NF) en 1970 Codd definió posteriormente la segunda forma de normalizacion "second normal form" (2NF) y la tercera form de normalización "third normal form" (3NF) en 1971. Codd y Raymond F. Boyce definieron "the Boyce-Codd normal form" (BCNF) en 1974.
¿En qué consiste cáda una?, estamos hablando de muchos años de trabajo, para cada uno de los niveles se invirtieron sudor y mucho tiempo, para llegar a la fabulosa conclusion de que lo que hacia falta y resuelve casi todos los niveles de normalización es una "llave primaria".

![normalization](https://imgur.com/UyTLkyp)

### ¿Cómo usamos la normalización con llave foranea?

Entonces, cada que nostros necesitamos separar modelos y al mismo tiempo relacionarlos, vamos a utilizar normalización.

Ejemplo:

![ejemplo de normalización](https://imgur.com/Ay3mdLf)

¿Qué te parece si hacemos un ejercicio con Uber Eats?

Uber Eats

* Restaurants
* Dishes
* Promos
* Users
* Deliverers

### Diseñando una base de datos normalizada en Firebase

Vamos a crear una normalización simple en Firebase Firestore, creando un modelo en texto y basandonos en él para diseñar nuestra colección y primer documento. 

```javascript

let userModel = {
  name: "BlisS",
  age: 31,
  adressess:[
    {
      name: "home",
      street: "cordoba",
      number: 51
    },
    {
      name: "work",
      street: "Jalapa",
      number: 100
    }
  ]
}

```

Tenemos entonces la forma de nuestro objetos, los cuales a simple vista ya podemos ver que address se puede convertir en un modelo, de igual forma que user, y relacionarlos por medio de una llave primaria.



### Another example

Finally we will write another example but this time we will use a map to show every element in an array that comes as a prop argument.

```javascript
let ListOfFoods = function({ foods }) {
  return (
    <ul>
      {foods.map((food, index) => {
        return <li key={index}>{food}</li>;
      })}
    </ul>
  );
};

let App = function() {
  let foods = ["eggs", "fruits", "candy"];
  return (
    <div>
      <ListOfFoods foods={foods} />
    </div>
  );
};

ReactDOM.render(<App />, root);
```

We have to observe that when we use a map inside of a component it have to be with an array ofcourse but also whe need to return JSX, we can observe too that we use the index provided for the map to use it in a prop called "key" this is mandatory when using map, in order to ReactJS work propertly.

We can write this example with even one component more inside the map, and with this we are using the components development style as it were conceived.

```javascript
let DisplayFood = function({ food }) {
  return <li> {food} </li>;
};

let ListOfFoods = function({ foods }) {
  return (
    <ul>
      {foods.map((food, index) => {
        return <DisplayFood key={index} food={food} />;
      })}
    </ul>
  );
};

let App = function() {
  let foods = ["eggs", "fruits", "candy"];
  return (
    <div>
      <ListOfFoods foods={foods} />
    </div>
  );
};

ReactDOM.render(<App />, root);
```

And with this example we have covered the several ways of working with props and the creation of multiple components always observing that we only render the `<App/>` component with `ReactDOM.render()` using all the other components within App component.

## Recap:

We have learned what ReactJS is, and how the component style development is acomplished, we have writen our first component and some more, we understand now what a prop is and how we can use them, and used the destructuring ES6 tool in order to write more readable components and we have set some defaults in props.

## Resources:

- [React official docs](https://reactjs.org/)
- [Destructuring](http://exploringjs.com/es6/ch_destructuring.html)
- [Tutorial: intro to React](https://reactjs.org/tutorial/tutorial.html)

> Author: @hectorbliss
