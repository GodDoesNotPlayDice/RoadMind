Los **conditional statements** (declaraciones condicionales) en JavaScript te permiten ejecutar diferentes bloques de código dependiendo de si una condición es verdadera (`true`) o falsa (`false`). Los más comunes son:

1. **`if`**: Ejecuta un bloque de código si la condición es verdadera.
2. **`else`**: Ejecuta un bloque de código si la condición del `if` es falsa.
3. **`else if`**: Permite verificar múltiples condiciones.
4. **`switch`**: Útil cuando tienes muchas condiciones para evaluar.

## Sentencias

### if
El bloque de código dentro del `if` se ejecuta solo si la condición es verdadera

```js
let edad = 18;

if (edad >= 18) {
    console.log("Eres mayor de edad.");
}
```

### else
El bloque de código dentro del `else` se ejecuta si la condición del `if` es falsa.

```js
let edad = 15;

if (edad >= 18) {
    console.log("Eres mayor de edad.");
} else {
    console.log("Eres menor de edad.");
}
```

### else if
Permite verificar múltiples condiciones. Si la primera condición es falsa, se verifica la siguiente, y así sucesivamente

```js
let hora = 14;

if (hora < 12) {
    console.log("Buenos días.");
} else if (hora < 18) {
    console.log("Buenas tardes.");
} else {
    console.log("Buenas noches.");
}
```


### switch
Es útil cuando tienes muchas condiciones para evaluar. Compara una expresión con múltiples casos (`case`) y ejecuta el bloque de código correspondiente.

```js
let dia = 3;
let nombreDia;

switch (dia) {
    case 1:
        nombreDia = "Lunes";
        break;
    case 2:
        nombreDia = "Martes";
        break;
    case 3:
        nombreDia = "Miércoles";
        break;
    case 4:
        nombreDia = "Jueves";
        break;
    case 5:
        nombreDia = "Viernes";
        break;
    case 6:
        nombreDia = "Sábado";
        break;
    case 7:
        nombreDia = "Domingo";
        break;
    default:
        nombreDia = "Día no válido";
}

console.log("Hoy es " + nombreDia);
```


## Operadores de comparación
Al igual que en el bloque anterior [[Equality Comparisons]] cuales son para comparar también existen otros operadores como:

- `!=` : No igual a (compara valor, no tipo).
- `!==` : No igual a (compara valor y tipo).
- `>` : Mayor que.
- `<` : Menor que.
- `>=` : Mayor o igual que.
- `<=` : Menor o igual que.

```js
let numero = 10;

if (numero === 10) {
    console.log("El número es exactamente 10.");
} else if (numero > 10) {
    console.log("El número es mayor que 10.");
} else {
    console.log("El número es menor que 10.");
}
```

## Operadores lógicos
También puedes combinar condiciones con operadores lógicos:

- `&&` : AND (y).
- `||` : OR (o).
- `!` : NOT (no).

```js
let edad = 20;
let tieneLicencia = true;

if (edad >= 18 && tieneLicencia) {
    console.log("Puedes conducir.");
} else {
    console.log("No puedes conducir.");
}
```
