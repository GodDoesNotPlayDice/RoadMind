Explicación de bucles con peras y manzanas, los bucles te permiten repetir una acción para cada fruta sin tener que escribir el código una y otra vez.

Los bucles disponibles en Javascript son:
-  `for`
-  `do...while`
-  `while`
-  `for...in loop`
-  `for...of loop`

## Ejemplo de los Bucles

### for
Este bucle es como si tuvieras una lista de frutas y quisieras contar cuántas manzanas hay.

```js
let frutas = ['manzana', 'pera', 'manzana', 'pera', 'manzana'];
let contadorManzanas = 0;

for (let i = 0; i < frutas.length; i++) {
    if (frutas[i] === 'manzana') {
        contadorManzanas++;
    }
}

console.log('Hay ' + contadorManzanas + ' manzanas.');
```

### while
Este bucle es como si estuvieras comiendo frutas hasta que ya no queden más.

```js
let frutas = ['manzana', 'pera', 'manzana'];
let indice = 0;

while (indice < frutas.length) {
    console.log('Me comí una ' + frutas[indice]);
    indice++;
}
```

### do...while
Similar al `while`, pero asegura que al menos una fruta se coma, incluso si la condición no se cumple inicialmente.

```js
let frutas = ["pera", "manzana", "naranja"];
let indice = 0;

do {
    console.log('Me comí una ' + frutas[indice]);
    indice++;
} while (indice < frutas.length);
```

### for...of
Este bucle es como si estuvieras mirando cada fruta en la canasta una por una.

```js
let frutas = ['manzana', 'pera', 'manzana'];

for (let fruta of frutas) {
    console.log('Hay una ' + fruta + ' en la canasta.');
}
```

### for...in
Este bucle es útil si quieres ver las propiedades de un objeto, como si tuvieras una bolsa con diferentes tipos de frutas y quisieras saber cuántas hay de cada una.

```js
let bolsaDeFrutas = {
    manzana: 3,
    pera: 2,
    banana: 1
};

for (let fruta in bolsaDeFrutas) {
    console.log('Hay ' + bolsaDeFrutas[fruta] + ' ' + fruta + '(s).');
}
```

## Continue y Break
Estos son como si decidieras dejar de comer frutas si encuentras una podrida (`break`) o saltarte una fruta específica (`continue`).

```js
let frutas = ['manzana', 'pera', 'manzana podrida', 'pera'];

for (let fruta of frutas) {
    if (fruta === 'manzana podrida') {
        console.log('Encontré una manzana podrida, dejé de comer.');
        break;
    }
    console.log('Me comí una ' + fruta);
}

for (let fruta of frutas) {
    if (fruta === 'pera') {
        continue;
    }
    console.log('Me comí una ' + fruta);
}
```

