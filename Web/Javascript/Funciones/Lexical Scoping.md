El **alcance léxico** se refiere a cómo JavaScript determina el alcance de las variables en función de su posición en el código. Las funciones pueden acceder a variables definidas en su ámbito exterior

```js
let x = 10;

function exterior() {
    let y = 20;

    function interior() {
        console.log(x + y); // Accede a x (global) y y (de exterior)
    }

    interior();
}

exterior(); // 30
```

a función `interior` puede acceder a `x` (variable global) y `y` (variable de la función `exterior`) debido al alcance léxico.