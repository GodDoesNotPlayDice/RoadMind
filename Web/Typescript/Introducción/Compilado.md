El compilado de un archivo typescript es usando `tsc`

```bash
tsc index.ts
```

## Opciones de compilado `--help`
Son **opciones de compilación** que puedes pasarle al compilador de TypeScript (comando `tsc`) para indicarle cómo quieres que convierta tu código. 

Cada opción se especifica con el prefijo `--`. Por ejemplo:

```bash
tsc --target ES5 --module commonjs
```

- `--target ES5` indica que el código TypeScript se convertirá en JavaScript compatible con la versión ECMAScript 5.

- `--module commonjs` especifica el tipo de sistema de módulos que se usará en el JavaScript resultante (en este caso, CommonJS, típico de Node.js).