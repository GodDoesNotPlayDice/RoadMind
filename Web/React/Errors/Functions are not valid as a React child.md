El error **"Functions are not valid as a React child"** usualmente ocurre cuando intentas renderizar una función directamente en tu componente en lugar de llamarla o renderizar su resultado.

```jsx
export const Input = ({setCategories}) => {
    const onAddCategory = (e) => { 
        if (e.key === "Enter") {
            setCategories([categories => [...categories, e.target.value]]);
            e.target.value = '';
        }
    };

    return (
        <>
            <input 
                className="shadow appearance-none border rounded w-3/5 py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" 
                id="search" 
                type="text" 
                placeholder="Capitan america!" 
                onKeyDown={onAddCategory}
            />
        </>
    );
};
```

### Error
Aquí, `setCategories` estaba siendo llamado con un nuevo array que contiene una función como único elemento `[categories => [...categories, e.target.value]]`. Esto sucede cuando `setCategories` se llama incorrectamente con una función en lugar de un nuevo estado.

```jsx
setCategories([categories => [...categories, e.target.value]]);
```

Aquí, `setCategories` estaba siendo llamado con un nuevo array que contiene una función como único elemento `[categories => [...categories, e.target.value]]`. Esto sucede cuando `setCategories` se llama incorrectamente con una función en lugar de un nuevo estado.

La corrección implica llamar a `setCategories` con un nuevo estado que incluya el valor anterior y el nuevo valor ingresado por el usuario, lo cual se logra correctamente en el código corregido

```jsx
setCategories(prevCategories => [...prevCategories, e.target.value]);
```

Esta corrección asegura que `setCategories` reciba el nuevo estado de forma adecuada, evitando así el error mencionado.