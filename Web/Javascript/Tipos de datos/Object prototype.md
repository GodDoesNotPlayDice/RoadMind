JavaScript es un lenguaje orientado a objetos construido alrededor de un modelo prototipo. En JavaScript, cada objeto hereda las propiedades de su prototipo, si las hay. Un prototipo es simplemente un objeto del que otro objeto hereda las propiedades. Para crear programas complejos que usan JavaScript, uno debe ser competente para trabajar con prototipos: forman el núcleo mismo de OOP en el lenguaje.

En JavaScript, cada objeto tiene una propiedad interna llamada `[[Prototype]]` (a la que puedes acceder mediante `__proto__` en algunos entornos, aunque no es recomendable usarla directamente). Este `[[Prototype]]` es una referencia a otro objeto, y es a través de este mecanismo que se logra la herencia en JavaScript.

Cuando intentas acceder a una propiedad o método en un objeto, JavaScript primero busca esa propiedad en el objeto mismo. Si no la encuentra, busca en su prototipo, y así sucesivamente hasta llegar al objeto `Object.prototype`, que es el prototipo base de todos los objetos en JavaScript.

## Creación de objetos y prototipos

### Objetos literales
Cuando creas un objeto literal en JavaScript, automáticamente su prototipo es `Object.prototype`.

```js
let animal = {
    tipo: 'Desconocido',
    hacerSonido: function() {
        console.log('Sonido desconocido');
    }
};

console.log(animal.__proto__ === Object.prototype); // true
```

### Constructor de objetos
Puedes crear objetos usando una función constructora. En este caso, el prototipo del objeto creado será el objeto `prototype` de la función constructora.

```js
function Animal(tipo) {
    this.tipo = tipo;
}

Animal.prototype.hacerSonido = function() {
    console.log('Sonido desconocido');
};

let perro = new Animal('Perro');
console.log(perro.__proto__ === Animal.prototype); // true
```

### Herencia mediante prototipos
Para implementar herencia, puedes establecer el prototipo de un objeto como otro objeto. Esto se puede hacer usando `Object.create()`

```js
let animal = {
    tipo: 'Desconocido',
    hacerSonido: function() {
        console.log('Sonido desconocido');
    }
};

let perro = Object.create(animal);
perro.tipo = 'Perro';
perro.hacerSonido = function() {
    console.log('Guau guau');
};

perro.hacerSonido(); // Guau guau
console.log(perro.__proto__ === animal); // true
```

### Métodos y propiedades en el prototipo
Es común agregar métodos y propiedades compartidas al prototipo de una función constructora para que todas las instancias compartan esos métodos y propiedades, en lugar de tener una copia en cada instancia.

```js
function Animal(tipo) {
    this.tipo = tipo;
}

Animal.prototype.hacerSonido = function() {
    console.log('Sonido desconocido');
};

let perro = new Animal('Perro');
let gato = new Animal('Gato');

perro.hacerSonido(); // Sonido desconocido
gato.hacerSonido(); // Sonido desconocido

console.log(perro.hacerSonido === gato.hacerSonido); // true (ambos comparten el mismo método)
```

