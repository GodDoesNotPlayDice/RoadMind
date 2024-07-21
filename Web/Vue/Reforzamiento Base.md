## Reforzamiento de JavaScript / Typescript

### Variables
**`var`**: nunca mas usarla en la vida.
**`let`**: el amigo que se ven de vez en cuando
**`const`**: prácticamente tu mejor amigo en JavaScript

### Scope
El scope es algo muy importante en JS ya que delimita hasta donde tiene conocimiento tu variable en JS.
```ts
if ( true ) {
	const noctulo = "un noctulo el murcilago chico."
}

console.log(noctulo)
```

### Interpretación 
La interpretación es una manera de insertar variables en los strings.
```ts
const frase1 = "un noctulo"
const frase2 = "el murcielago chico."
const noctulo : string = `${frase1} ${frase2}`
```

### Objetos
Los objetos no es mas que una variable que tiene un JSON dentro.

**`as const`**: crea un objeto de solo lectura para la inmutabilidad en la clase.

```ts
const person = {
	name : 'Noctulo',
	age : 100,
	skills : {
		fire : true,
		water : false,
		whistle : true
	}
} as const;

person.age = 20 // Cannot assing to 'age'!!!
```

#### Paso por referencia
El paso por referencia es cuando el objeto es pasado a otra variable donde la variable con el objeto es **cambiada** por lo que ambas serán cambiadas, **todos los objetos en JavaScript se pasan por referencia.**

```ts
const person2 = person; // Modificacion por referencia name = Meruane
person2.name = "Meruane" // Modifico por referencia el name de objeto 2 y objeto 1
```

##### Como evitarla con Spread Operator y structuredClone
El operador **spread** cual sirve para dividir en partes los **atributos** de un objeto.
```ts
const person2 = {...person}; // Queda Noctulo
person2.name = "Meruane"  // Queda Meruane
```
Pero ojo, que si existe un atributo cual es otro **Objeto** dentro de, este cambiara si es modificado
```ts
person2.skills.fire = false; // Se cambia a false tanto en objeto 2 y en objeto 1
```
Que se hace.
```ts
const person2 = {...person, skills: {...person.skills} } // Solucion al sub objeto.
```

El método **`structuredClone`** es una función de JS 2022 cuya sirve para clonar objetos por completo.

```ts
const person2 = structuredClone(person);
```

### Listas / Arrays
Los arreglos es simplemente una colección de objetos.

```ts
const noctulo_array = [1,2,3,4,5] as const; // const fuerte solo lectura xd
noctulo_array.push(10) // meter 10 despues de 5 pero no es permitido porque esta congelada la constante.
```

Para copiar el array podemos copiarlos igual que un **objeto** ya que todo es un objeto en JS que son pasados por referencia por lo que el **StructuredClone** es lo mejor que paso en la vida.

```ts
const noctulo_array2  = structuredClone(noctulo_array) // copiao de forma segura.
```

Para recorrer las listas los **For** quedaron en el pasado hoy en día si no vives debajo de una piedra conocerías que existe **map** cual le pasamos una variable y hace lo mismo que un for pero con un método madre mía tío que espectacular.

```ts
noctulo_array2.map( value => {
	console.log(value) // contaria 1,2,3,4,5 xd
})
```



### Funciones / Functions
Las funciones simplemente son bloques de código que se suelen utilizar para reutilizar ciertas tareas.

Existen **tres** formas de declarar funciones.

```ts
function noctulo_viejo(name : string){
	return "nocutlo viejo con this " + name
}

const noctulo_moderno = (name : string) => {
	return "moderno sin this " + name
}

const noctulo_muymoderno = (name : string) => `hay que cerrar el estadio ${name}`


console.log(noctulo_moderno("JAJA MERUANE"));

```


#### Métodos
Los métodos son funciones de librerías o del propio lenguaje.
```ts
const noctulos = [
	{
		id: 1,
		name: "noctulo espectacular"
	},
	{
		id: 2,
		name: "noctulo feo"
	}
];

const noctulo = noctulos.find(n ⇒ n.id === 1);
console.log(noctulo.?.name); // esto es porque no sabe que es el noctulo.
console.log(noctulo.?.po)
```


### Desestructuración

#### Objetos
Es cuando tenemos un objeto con varios atributos y lo queremos separar en variables para su uso, lo único malo de esto es que se pierde el **trackeo** del objeto ósea que pasan a ser **undefined**.

Se presenta el problema del **no poderoso** cual es donde hay un atributo que no todos tienen en la destructuracion ejemplo: el noctulo no tienen poder pero puede que otro si.

```ts
const noctulo = {
	name : "Meruane",
	age: 100,
}
const {name, age, power = "la mea caga"} = noctulo; // problema del no poderoso.

console.log({age, name, power})

```
Se soluciona de la siguiente manera, **TS** tiene una palabra reservada llamada **`interface`** esto es muy weno ya que nos deja solucionar varios problemas de **js**

```ts
interface Noctulo {
	name: string;
	age: number;	
	power?: string; // opcional ?
}

const noctulo : Noctulo = {
	name : "Meruane",
	age: 100,
}
const {name, age, power = "la mea caga"} = noctulo; // ahora funciona.

console.log({age, name, power})

```


#### Arrays
La destructuracion de arrays es lo mismo pero con **variables posicionales**.
```ts
const noctulo = ['Meruane', 'Ayuda', 'AAAAA']
const [a, b, c, x = "Desvan!" ] = noctulo; // podemos agregar otro que no este en la lista pero es opcional por lo que si se ve agregado otro elemento el de la lista lo suplantara y el opcional no funcionara mas.
console.log(a)
```

Tambien podemos desestructurar **Arrays** resultado de funciones, la cosa esque tenemos el inconveniente que puede que nos de dualidad de valores **`const numbers : string | number`** este problema no es grave pero puede escalara a cosas mas graves, ya que TS no sabe que tipo definir para los metodos.
```ts
const returnNoctulo = () => {
	return [123, "ABC"] as const; // lo podemos tratar como const para que siempre lo trate igual y asi que retorne siempre un valor.
}

const [numbers, letters] = returnNoctulo();
```


### Importaciones y exportaciones

#### Exportaciones
Las exportaciones es bien sencillo de explicar al igual que la importaciones, las exportaciones son **objetos** cuyo colocamos la palabra **`export`** con anterioridad.

```ts
export const Noctulo = {
	name : "Noctule",
	age : 1000
}
```

Tenemos el export **default**.
```ts
const noctulos = [
	{
		name : "Noctulo rojo",
		age : 1000
	},
	{
		name : "Noctulo azul",
		age : 1000
	},
	{
		name : "Noctulo amarillo",
		age : 1000
	},
	{
		name : "Noctulo verde",
		age : 1000
	}
]

export default noctulos;
```

#### Importaciones
Las importaciones nos sirven para **importar** valga redundancia **librerías, exportaciones y CSS**
```ts
import './styles.css';
import 'noctuloLogo' from './NoctuloLogo.svg'
import noctulos from '/noctulos.ts'
import noctulos { noctuloslocos } from '/noctulos.ts' // mas de uno
```


### Tipado de datos
El tipado de datos es para asignarle un cierto tipo de objeto o como debe ser la variable.

```ts
const noctulos = [{}, {}, {}...] // array con objetos

export const noctulo = (loco : 'loco' | 'normal') => { // esto es funcional cuando sabemos que no va a cambiar el criterio pero no es lo mas correcto.
  return noctulos.filter( n => n.tipo == loco)
}
```

Podemos crear nuestros propios tipos para manejar el tipado y lo que puede insertarse y devolver.
```ts

interface Noctulo {
	id: number;
	name: string;
	age: number;
	type : Specie
}

type Specie = "loco" | "normal" // No deja poner otro tipo de dato.

const noctulos : Noctulo[] = [
  { name: 'noctulo normal', type: 'normal' },
  { name: 'noctulo loco', type: 'loco' },
  { name: 'noctulo normal', type: 'normal' },
  { name: 'noctulo loco', type: 'loco' },
  { name: 'noctulo normal', type: 'normal' },
  { name: 'noctulo loco', type: 'loco' },
  { name: 'noctulo normal', type: 'normal' },
  { name: 'noctulo loco', type: 'loco' },
  { name: 'noctulo normal', type: 'normal' },
  { name: 'noctulo loco', type: 'loco' },
  { name: 'noctulo normal', type: 'normal' },
  { name: 'noctulo loco', type: 'loco' },
  { name: 'noctulo normal', type: 'normal' },
  { name: 'noctulo loco', type: 'loco' },
  { name: 'noctulo normal', type: 'normal' },
  { name: 'noctulo loco', type: 'loco' },
  { name: 'noctulo normal', type: 'normal' },
  { name: 'noctulo loco', type: 'loco' },
  { name: 'noctulo normal', type: 'normal' },
  { name: 'noctulo loco', type: 'loco' }
]

export const noctulo = (tipo : Specie) => {
  return noctulos.filter( n => n.type == tipo)
}
```


### Promesas
Las promesas no es mas que un **callback** moderno cual suele ser **async**. funciona de la siguiente manera en este orden:
1. Se resuelve el **Thread** cual es el hilo de JS
2. Se resuelven los **Callbacks, Intervals, Promises, etc.**

Por lo que primero se ejecutaría el **Hilo principal** y cuando haya acabado se ejecutara lo demás.

```output
> Inicio (Hilo)
> Fin (Hilo)
> Mi amigo cumplio. (callback)
```

**Historia del amigo**
La historia del amigo consiste en

> El amigo dice préstame **dinero**, entonces como somos muy buenos amigos le presto el **dinero** que pueden ser 1000 o 2000 pesos y el amigo dice yo te **prometo** que te lo voy a pagar.

Pueden pasar 2 cosas.
1. El amigo **devuelve** el dinero
2. El amigo **no devuelve** el dinero.

En la promesa tenemos un parámetro llamado **resolve o res** que le pasamos un parámetro que **resuelve el valor** que nosotros queremos.
Entonces ponemos en duda la **promesa** usando **`then()`** o **`catch()`**,
- **then**: lo ocuparemos para cuando la respuesta fue la que esperábamos.
- **catch**: lo ocuparemos cuando no es la respuesta que esperábamos.

```ts
new Promise( ( res ) => {
	res('Mi amigo cumplio')
}).then( ( message ) => console.log(message) ).catch( (message ) => console.log(message) )
```

El **resolve** solo es posible llamar una vez, no obstante todo lo demás es posible llamar mas de 1 vez.

```ts
new Promise( (res, rej ) => {
	setTimeout(() => {
		reject("Mi amigo no cumplio")
	}, 1000)
}).then( ( message ) => console.log(message) ).catch( (message ) => console.log(message) )
```

#### Argumentos en promesas
Esto sirve para poder trabajar de forma **asíncrona** y usar **endpoints**

```ts
export interface Noctulo {
	id?: number;
	name: string;
	age?: number;
	type : Specie
}

type Specie = "loco" | "normal"

const noctulos : Noctulo[] = [
  { id: 1 ,name: 'noctulo normal', type: 'normal' },
  { id: 2 ,name: 'noctulo loco', type: 'loco' },
  { id: 3 ,name: 'noctulo normal', type: 'normal' },
  { id: 4 ,name: 'noctulo loco', type: 'loco' },
  { id: 5 ,name: 'noctulo normal', type: 'normal' },
  { id: 6 ,name: 'noctulo loco', type: 'loco' },
  { id: 7 ,name: 'noctulo normal', type: 'normal' },
  { id: 8 ,name: 'noctulo loco', type: 'loco' },
  { id: 9 ,name: 'noctulo normal', type: 'normal' },
  { id: 10 ,name: 'noctulo loco', type: 'loco' },
  { id: 11 ,name: 'noctulo normal', type: 'normal' },
  { id: 12 ,name: 'noctulo loco', type: 'loco' },
  { id: 13 ,name: 'noctulo normal', type: 'normal' },
  { id: 14 ,name: 'noctulo loco', type: 'loco' },
  { id: 15 ,name: 'noctulo normal', type: 'normal' },
  { id: 16 ,name: 'noctulo loco', type: 'loco' },
  { id: 17 ,name: 'noctulo normal', type: 'normal' },
  { id: 18 ,name: 'noctulo loco', type: 'loco' },
  { id: 19 ,name: 'noctulo normal', type: 'normal' },
  { id: 20 ,name: 'noctulo loco', type: 'loco' }
]

export const getNocutuloById = (id : number) => {
  return noctulos.find( n => n.id == id)
}

```

Podemos **tipar la salida** para no perder las propiedades del tipo de dato que queremos obtener.
En el ejemplo filtramos por **id** los noctulos si son econtrados la promesa devolvera los **resuelto** y si no la promesa devolverá lo **rechazado.**

```ts
import getNoctuloById, { Noctulo } from '/noctulo.ts'

const getNoctuloIDAsync = (id : number) : Promise<Noctulo> => {
  return new Promise( (res, rej) => {
    setTimeout(() => {
      const noctulo = getNocutloById(id)
      if (noctulo) {
        res(noctulo)
      } else {
        rej(`No se encontraron noctulos ${id}`)
      }
    }, 1500)
  })
}

getNoctuloIDAsync(10).then( noctulos => { console.log(noctulos) }).catch( err => { console.log(err) }) 

```

Observaciones y limpieza del codigo.

```ts
if (noctulo) {
	res(noctulo)
} else {
	rej(`No se encontraron noctulos ${id}`)
}
```

Podemos evitar el anidamiento de la estructura para hacerlo mas limpio.

```ts
if (noctulo) {
	res(noctulo)
	return;
}
rej(`No se encontraron noctulos ${id}`)

```

Mas resumido aun, un **ternario**.

```ts
noctulo ? res(noctulo) : rej(`No se encontraron noctulos ${id}`)
```


### Fetch
Hacer fetch es literalmente para consumir la API de nosotros o de un tercero utilizando **`fetch`** que es literalmente un **callback** que devuelve una **promesa.**

```ts
const api = 'https://pokeapi.co/api/v2/pokemon/' as const;

const getPokemon = (id: number) => {
  return fetch(`${api}${id}`).then((res) => res.json()).catch((err) => console.error(err))
}

const pokemon = await getPokemon(33)
console.log(pokemon)
```

### Axios
Axios es lo mismo pero un poco mas simplificado

```ts
import axios from 'axios'

import type { PokemonResponse } from './pokemon.response.ts'

const pokemonApi = axios.create({
  baseURL: 'https://pokeapi.co/api/v2',
})

pokemonApi.get<PokemonResponse>('/pokemon')
.then(response => {
  const { count, results } = response.data
  console.log(`There are ${count} pokemons`)
  results.forEach(({ name }) => console.log(name))
}).catch(error => {
  console.error(error)
})
```

### Async y Await
Mas de lo mismo con los fetch y axios solo que aquí ocupamos promese con async y await para poder hacer tomar una petición get.

```ts
import axios from 'axios'
import type { PokemonResponse } from './pokemon.response.ts'


const pokemonApi = axios.create({
  baseURL: 'https://pokeapi.co/api/v2',
})


const getPokemons = async () => {
  try {
    const { data } = await pokemonApi.get<PokemonResponse>('/pokemon')
    console.log(data)
  }
  catch (error) {
    console.error("No se pudo obtener la lista de pokemones")
  }
}

getPokemons()
```

