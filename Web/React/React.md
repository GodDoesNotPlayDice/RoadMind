## Estructura base de React

esta es la base de cualquier componente de React usando TS.

```tsx
import React from "react";

interface TitleProps{
	name : string;
}

export const Title: React.FC<TitleProps> = ({name}) => {
	return (
		<h1>Hola bienvenido {name}</h1>
	
	)
}

```


## Vite + Tailwind + React
```sh
npm create vite@latest
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

```sh
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},2
  },
  plugins: [],
}
```

index.css
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## Manejo de los elementos en React

### Sin uso del estado

Sin uso del estado estamos haciendo es limitar la capacidad de renderizado y reactividad al elemento afectado, sin embargo, esto nos puede servir en algunos casos donde no necesitemos una reactividad con algún o mismo elemento.

Ejemplo: un nav que tenga los elementos ocultos y haya un botón que solo haga show y hidde de los elementos.

- Ventajas: Simplifica la lógica del componente y mejora el rendimiento al no tener que rastrear y actualizar el estado.
- Desventajas: Limita la capacidad de crear interfaces de usuario dinámicas y reactivas.


### Con uso del estado

 Con el uso del estado los componentes pueden mantener y actualizar datos de forma dinámica. Esto permite que los elementos de la interfaz de usuario respondan a eventos y cambios de datos en la aplicación.

Ejemplo: Un contador que incrementa su valor cada vez que se hace clic en un botón. El estado del contador se actualiza cada vez que se hace clic, y React se encarga de volver a renderizar el componente con el nuevo valor.

- Ventajas: Permite una gestión dinámica de datos y una interfaz de usuario interactiva.
- Desventajas: Puede aumentar la complejidad del código y el rendimiento si no se utiliza correctamente.
#### Hooks
En React, los "hooks" son funciones especiales que te permiten utilizar el estado y otras características de React sin tener que escribir una clase.

Los hooks proporcionan una forma más simple y efectiva de compartir lógica entre componentes, reutilizar código y manejar el ciclo de vida del componente.
##### useState 
Sirve para re renderizar un componente, o del atributo que quiero guardar. Es la función que react me da para interactuar con el.
- Uso del booleano (Re render)
- Uso de cambio de lista de productos (Re render)
- Uso de cambio de texto (Re render)
```tsx
const [inputValue, setInputValue] = useState<string>("");  
const [searchResults, setSearchResults] = useState<Product[]>([]);  
const [isFocused, setIsFocused] = useState<boolean>(false);
```

Se da una destructuracion del array porque react es flojo, y es simple uno es el valor inicial y el otro es el método para re renderizar.


##### useEffect
Tiene que pasar algo para que ejecute, en este caso si las deps cambian se ejecutara el useEffect.

```tsx
useEffect(() => {  
  if (isFocused) {  
    fetchData(inputValue);  
  } else {  
    setSearchResults([]);  
  }  
}, [inputValue, isFocused]); // deps
```

### Fetch 
No es buena practica usar fetch, porque la función ocupa valor en memoria y no se limpia y se va ir cacheando por 1 segundo por lo menos hasta que el garbage collector.
 ```tsx
 const fetchData = (value: string) => {  
  fetch(`https://test-products-json-default-rtdb.firebaseio.com/.json`)  
    .then((response) => response.json())  
    .then((data) => {  
      const filteredData: Product[] = data.filter((item: Product) => {  
        return item?.nombre?.toLowerCase().includes(value.toLowerCase());  
      });  
      setSearchResults(filteredData);  
    });  
};
```


### useCallback
Hace que no cache una función normal y no le afecte el re render.

### Events
Los da React por que la arquitectura 
```tsx
onChange={(e) => handleChange(e.target.value)}  // Devuelve un evento
onFocus={handleFocus}  // es void
onBlur={handleBlur} // es void
```

### Teoria
**Componentes Sencillos**: Cuando los componentes son sencillos se usan estados simples.
**UseState de objeto**: Se usa el estado y manejo del estado, el manejo del estado es usar el state de una manera compleja.


