Cuando trabaja con API remotas, necesita una forma de interactuar con esas API. Modern JavaScript proporciona dos formas nativas de enviar solicitudes HTTP a servidores remotos, **xmlhttprequest** y buscar.

## Usando XMLHttpRequest
`XMLHttpRequest` es una forma más antigua de hacer solicitudes HTTP en JavaScript.

```js
// Crear una nueva instancia de XMLHttpRequest
var xhr = new XMLHttpRequest();

// Configurar la solicitud
xhr.open("GET", "https://api.ejemplo.com/datos", true);

// Definir lo que sucede cuando la solicitud se completa
xhr.onload = function () {
    if (xhr.status >= 200 && xhr.status < 300) {
        // La solicitud fue exitosa
        console.log(JSON.parse(xhr.responseText));
    } else {
        // Hubo un error
        console.error("Error al realizar la solicitud");
    }
};

// Definir lo que sucede en caso de error
xhr.onerror = function () {
    console.error("Error de red");
};

// Enviar la solicitud
xhr.send();
```

## Usando Fetch
`Fetch` es una API más moderna y poderosa para hacer solicitudes HTTP. Es más fácil de usar y devuelve promesas, lo que facilita el manejo de respuestas asíncronas.

```js
// Hacer una solicitud GET
fetch("https://api.ejemplo.com/datos")
    .then(response => {
        if (!response.ok) {
            throw new Error("Error en la solicitud");
        }
        return response.json();
    })
    .then(data => {
        console.log(data);
    })
    .catch(error => {
        console.error("Hubo un problema con la solicitud Fetch:", error);
    });
```

## Comparación
- **`XMLHttpRequest`** es más verboso y requiere más código para manejar errores y respuestas. 
- **`Fetch`** es más moderno, utiliza promesas y es más fácil de usar, pero no es compatible con navegadores muy antiguos.


Si estás trabajando en un entorno moderno, `Fetch` es generalmente la mejor opción.

