Una estructura de datos es un formato organizado, maneja y guarda la data de una manera eficiente y accesible a la información.

Javascript tiene un primitivo **built-in** y uno no primitivo **non-primitive** sobre estructura de data.

## Primitivos
Estos primitivos vienen por default con el lenguaje y esta en todo el entorno de JavaScript y puedes usarlo inmediatamente sin configuraciones previas, **un ejemplo son los objetos y los arrays**.

### Ejemplos de datos primitivos
```js
// Usando un array (estructura primitiva)
const frutas = ["manzana", "banana", "naranja"]
frustas.push("uva")
console.log(frutas[1]) // Accedemos mediante el indice

// Usando un objeto (estructura primitiva)
const usuario = {
	nombre: "Ana",
	edad: 30,
	esAdmin: true,
}

console.log(usuario.edad) // Accedemos por medio de la propiedad.
```

La utilidad que tiene estos **Built-in** es que las tenemos disponibles desde ya y no debemos programar para usarlas.

## No Primitivos
No vienen con el lenguaje y tu debes codificarlas para si quieres usarlas, un ejemplo de "out of the box" seria
- Imaginemos que queremos una estructura de datos tipo **pila** de apilar, _cual el ultimo que entra y el primero en salir_

Como esta función no existe debemos programarla.

En este caso codeamos una data estructura cual lo que hace es apilar, esto es usado en
- Gestión de historial (ej: "undo" en editores de texto).
- Evaluación de expresiones matemáticas.
- Navegación entre rutas (ej: el botón "atrás" en un navegador).

Al implementarla manualmente, controlamos su comportamiento específico.

```js
class Stack {
	constructor() {
		this.items = [] // usamos un array interno
	}
	
	push(element){
		this.items.push(element)
	}
	
	pop(){
		if (this.isEmpty()) return "Pila vacia"
		return this.items.pop() // elimina el ultimo elemento
	}
	isEmpty() {
		return this.items.lenght === 0
	}

	count(){
		return this.items
	}
}

const pila = new Stack();
pila.push("libro1")
pila.push("libro2")
console.log(pila.pop())
pila.push("libro3")
console.log(pila.count())
console.log(pila.pop())
console.log(pila.count())

```


Otro ejemplo son las **listas enlazadas**, las listas enlazadas no están built-in en JavaScript, pero son útiles para inserciones/eliminaciones rápidas.

Las listas **enlazadas** son eficientes para:
- **Inserción/eliminación** de elementos en tiempo constante (`O(1)`) en ciertos casos.


```js
class Nodo {
  constructor(valor) {
    this.valor = valor;
    this.siguiente = null;
  }
}

class LinkedList {
  constructor() {
    this.cabeza = null;
  }

  agregar(valor) {
    const nuevoNodo = new Nodo(valor);
    if (!this.cabeza) {
      this.cabeza = nuevoNodo;
    } else {
      let actual = this.cabeza;
      while (actual.siguiente) {
        actual = actual.siguiente;
      }
      actual.siguiente = nuevoNodo;
    }
  }
}

// Uso de la lista enlazada
const lista = new LinkedList();
lista.agregar(10);
lista.agregar(20);
console.log(lista.cabeza.siguiente.valor); // 20
```


## ¿Por qué es útil esta diferenciación?
- **Estructuras built-in (arrays, objetos):**
    - Son rápidas y optimizadas por el motor de JavaScript **(V8, SpiderMonkey, etc.)**.
    - Ideales para la mayoría de casos cotidianos.
- **Estructuras custom (pilas, listas enlazadas, árboles):**
    - Permiten resolver problemas específicos donde las estructuras nativas no son suficientes.
    - Ejemplos: algoritmos de búsqueda avanzada (árboles binarios), gestión de memoria, etc.


Luego continua con [[Keyed Collections]], [[Structure data]] y [[Index Collection]].
