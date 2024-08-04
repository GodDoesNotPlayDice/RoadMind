Testing usado con **vitest.**

## Unitarias
Las pruebas unitarias son cuando se hace **test** a un elemento independiente.

## Integración
Es cuando pasan todas las pruebas **unitarias** y luego se juntan.

## Características
1) Fáciles de escribir (que no sea complicado)
2) Fáciles de leer (que se entienda)
3) Confiables (que sea lo que se espera)
4) Principalmente unitarias (porque es más fácil de testear)
5) Rápidas (porque se ejecutan muchas veces)

### Concepto AAA
`Arrange, Act, Assert`
1) **Arrange**: Preparar el entorno de la prueba
	- Es el sujeto de prueba que se va a testear y aca preparamos el ambiente para hacer pruebas
2) **Act**: Ejecutar la prueba
	- Es lo que queremos simular o probar.
1) **Assert**: Verificar que el resultado es el esperado
	- Es la verificación de que el resultado es el esperado.



## Estructura del testing
En la carpeta raíz de la App se crea una carpeta llamada **tests** y dentro de ella se crean los archivos de test.
Los archivos que lo siguen son dentro del carpeta del componente que se va a testear.
### Ejemplo
**src**: `helpers/sum.ts`
**test**: `tests/helpers/sum.test.ts`

```typescript
import { expect, test } from 'vitest'
import { addArray, sum } from '../../src/helpers/sum'
import { describe } from 'node:test'

  

test('adds 1 + 2 to equal 3', () => {
	const a = 1
	const b = 2
	const result = sum(a, b)
	expect(result).toBe(3)
})

describe('addArray', () => {
	test('should return 0 if the array is empty', () => {
	const result = addArray([])
	expect(result).toBe(0)
})
test('should return the sum of the array', () => {
	const result = addArray([1, 2, 3, 4])
	expect(result).toBe(10)
})

})
```

**`test`:** Es una función que recibe dos parámetros, el primero es el nombre de la prueba y el segundo es una función que ejecuta la prueba.

**`describe`**: Es una función que recibe dos parámetros, el primero es el nombre de la prueba y el segundo es una función que ejecuta la prueba.

**`expect`**: Es una función que recibe un valor y retorna un objeto con el método `toBe` que recibe un valor y compara si es igual al valor que se le pasa.

> Al momento de testear se recomienda buscar las partes mas atómicas de los componentes para testearlas y luego ir testeando los composables.


### Configuración

#### Vitest
Para configurar las pruebas se debe instalar las siguientes dependencias:
```bash
npm install --save-dev vitest
```

Luego se debe agregar el siguiente script en el `package.json`:
```json
"scripts": {
  "test": "vitest"
}
```

Finalmente se debe ejecutar el siguiente comando:
```bash
npm run test
```

#### Configuración de files.

`vitest.config.ts`
```ts
import { fileURLToPath } from 'node:url'
import { mergeConfig, defineConfig, configDefaults } from 'vitest/config'
import viteConfig from './vite.config'
export default mergeConfig(
	viteConfig,
	defineConfig({
		test: {
		environment: 'jsdom',
		exclude: [...configDefaults.exclude, 'e2e/**'],
		root: fileURLToPath(new URL('./', import.meta.url)),
		globals : true
		};
	});
);
```
Ya la mayoría de este código viene por defecto en la configuración de `vitest`, pero se puede modificar según las necesidades del proyecto.

Ejemplo agregar `globals : true` para que se puedan usar en todas las pruebas.

luego en `tsconfig.vitest.json` agregamos lo siguiente.

```json
"types": ["node", "jsdom", "vitest/globals"],
```

y por ultimo en `tsconfig.app.json`  agregamos `tests`.

```json
"include": ["env.d.ts", "src/**/*", "src/**/*.vue","tests"],
```

### Pruébas de componentes
Podemos agregarle una `data` como atributo al elemento que queremos testear y luego buscarlo por el `data-testid`.

  ```html
  <h3 data-testid="counter-label">Counter: {{ counter }}</h3>
  <h3 data-testid="square-label">Square: {{ counter * counter }}</h3>
  ```

```ts
expect(wrapper.find('h3').text()).toContain(`Counter: ${value}`)

expect(wrapper.find('[data-testid="square-label"]').text()).toContain(`Square: ${(value * value)}`)  

const [ counterLabel, squareLabel ] = wrapper.findAll('h3')

expect(counterLabel.text()).toContain(`Counter: ${value}`)
expect(squareLabel.text()).toContain(`Square: ${(value * value)}`)
```

