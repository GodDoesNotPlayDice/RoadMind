La propuesta para cambiar el comportamiento de `typeof null` en ECMAScript (JavaScript) es un tema recurrente en la comunidad de desarrollo debido a la peculiaridad de que, en la versión actual del lenguaje, `typeof null` devuelve `"object"` en lugar de `"null"`.

### Contexto y Problema Actual

En JavaScript, el operador `typeof` devuelve una cadena que indica el tipo del operando. Sin embargo, hay una excepción notable: cuando se aplica a `null`, el operador devuelve `"object"`:

```js
console.log(typeof null); // "object"
```

Este comportamiento es considerado un error en el diseño original de **JavaScript**. En versiones anteriores del lenguaje, se asignaban bits específicos para indicar el tipo de un valor en su representación interna. El valor `null` se representaba con un puntero nulo (o un valor similar), y la verificación de tipo para un objeto también se basaba en la verificación de un bit específico. Como resultado, `null` accidentalmente se identificó como un objeto.

### Propuesta de Solución

La propuesta que mencionas sugirió cambiar este comportamiento para que `typeof null` devuelva `"null"`, lo que sería más intuitivo y lógico para los desarrolladores. Sin embargo, dado que cambiar esto directamente en el lenguaje rompería la retrocompatibilidad con muchísimo código existente, la propuesta se presentó como un "opt-in". Es decir, los desarrolladores tendrían que optar por esta nueva semántica de manera explícita.

### Rechazo de la Propuesta

La razón principal por la cual la propuesta fue rechazada es el gran riesgo que supone para la compatibilidad hacia atrás. Muchas aplicaciones y bibliotecas de JavaScript dependen del comportamiento actual (aunque erróneo) y un cambio como este podría romper una cantidad significativa de código. Además, el lenguaje JavaScript valora mucho la estabilidad y la retrocompatibilidad, lo que hace que los cambios de este tipo sean particularmente difíciles de implementar.

Al final, se decidió mantener el comportamiento actual, en lugar de introducir una nueva opción que podría complicar aún más la semántica del lenguaje. Por ello, `typeof null === "object"` sigue siendo la norma, a pesar de que muchos desarrolladores encuentran este comportamiento confuso y desearían que fuera diferente.

Este es un ejemplo de cómo, en el diseño de lenguajes de programación, las decisiones técnicas tienen que equilibrarse con la necesidad de mantener la estabilidad y la compatibilidad con el código existente.