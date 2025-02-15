La herencia prototípica es una característica en JavaScript utilizada para agregar métodos y propiedades en los objetos. Es un método por el cual un objeto puede heredar las propiedades y métodos de otro objeto.

Tradicionalmente, para obtener y establecer el prototipo de un objeto, usamos `Object.getPrototypeOf` y `Object.SetPrototypeOF`.

Es bien util para cambiar el comportamiento de objetos en **runtime.**
## getPrototypeOf
Este lo usaremos para obtener el prototipo de un objeto, por ejemplo.
Es como preguntarle a una fruta: "¿De quién **heredaste** tus propiedades y métodos?"

## setPrototypeOf
Establece o cambia el prototipo de un objeto, por ejemplo. 
Es como decirle a una fruta: "Ahora **hereda** de este otro objeto."

## Ejemplo clave

Creamos un objeto base `frutaGenerica` que será nuestro prototipo base:

```js
const frutaGenerica = {
  tipo: "Fruta",
  color: "desconocido",
  describir() {
    return `Soy una ${this.tipo} de color ${this.color}.`;
  }
};
```

Luego crearemos una `manzana`, cual heredara de `frutaGenerica`:

**¿Que es lo que ocurrirá?**
- Usaremos@ `Object.setPrototypeOf` para decirle a `manzana` que herede de `frutaGenerica`.
- Ahora `manzana` puede acceder a los métodos y propiedades de `frutaGenerica`.

```js
const manzana = {
  tipo: "manzana",
  color: "rojo"
};

// Establecemos el prototipo de manzana como frutaGenerica
Object.setPrototypeOf(manzana, frutaGenerica);

console.log(manzana.describir()); // "Soy una manzana de color rojo."
```


Podemos usar `Object.getPrototypeOf` para verificar de quién hereda `manzana`, el resultado es `prototipoDeManzana` es igual a `frutaGenerica`, lo que confirma que `manzana` hereda de `frutaGenerica`.

```js
const prototipoDeManzana = Object.getPrototypeOf(manzana);
console.log(prototipoDeManzana === frutaGenerica); // true
```

Ahora creamos una `pera` y le asignamos un prototipo diferente:

**¿Que es lo que ocurrirá?**
- `pera` heredara de `frutaGenerica`, pero también tiene su propia propiedad `maduracion`.

```js
const pera = {
  tipo: "pera",
  color: "verde",
  maduracion: "2 días"
};

// Establecemos el prototipo de pera como frutaGenerica
Object.setPrototypeOf(pera, frutaGenerica);

console.log(pera.describir()); // "Soy una pera de color verde."
```


Usamos `Object.getPrototypeOf` para confirmar de quién hereda `pera`:

`prototipoDePera` es igual a `frutaGenerica`, lo que confirma que `pera` también hereda de `frutaGenerica`.

```js
const prototipoDePera = Object.getPrototypeOf(pera);
console.log(prototipoDePera === frutaGenerica); // true
```


También podemos hacer que Podemos cambiar el prototipo de un objeto en tiempo de ejecución. Por ejemplo, hagamos que `manzana` herede de un nuevo prototipo:

**¿Que es lo que ocurrirá?**
- `manzana` ahora hereda de `frutaExotica` en lugar de `frutaGenerica`.
- El método `describir` de `frutaExotica` se usa en lugar del de `frutaGenerica`.

```js
const frutaExotica = {
  tipo: "Fruta Exótica",
  sabor: "tropical",
  describir() {
    return `Soy una ${this.tipo} de sabor ${this.sabor}.`;
  }
};

// Cambiamos el prototipo de manzana a frutaExotica
Object.setPrototypeOf(manzana, frutaExotica);

console.log(manzana.describir()); // "Soy una manzana de sabor tropical."
```

Usamos `Object.getPrototypeOf` para confirmar el cambio:

```js
const nuevoPrototipoDeManzana = Object.getPrototypeOf(manzana);
console.log(nuevoPrototipoDeManzana === frutaExotica); // true
```

