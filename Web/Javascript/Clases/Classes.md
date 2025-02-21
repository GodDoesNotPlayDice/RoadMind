Las clases en JavaScript son una forma de crear objetos y encapsular datos junto con funciones que operan sobre esos datos. Aunque JavaScript está basado en prototipos, las clases proporcionan una sintaxis más clara y familiar para los desarrolladores que vienen de otros lenguajes de programación orientados a objetos.

```js
// Definición de una clase
class Persona {
    // Constructor para inicializar las propiedades de la clase
    constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    // Método para saludar
    saludar() {
        console.log(`Hola, mi nombre es ${this.nombre} y tengo ${this.edad} años.`);
    }
}

// Creación de una instancia de la clase Persona
const persona1 = new Persona("Juan", 30);

// Llamada al método saludar
persona1.saludar(); // Salida: Hola, mi nombre es Juan y tengo 30 años.
```

1. **Definición de la clase**: Usamos la palabra clave `class` seguida del nombre de la clase (`Persona`).
2. **Constructor**: El método `constructor` es un método especial que se llama cuando se crea una nueva instancia de la clase. Se utiliza para inicializar las propiedades del objeto.
3. **Métodos**: Dentro de la clase, podemos definir métodos como `saludar` que pueden ser llamados en las instancias de la clase.
4. **Creación de instancias**: Usamos la palabra clave `new` para crear una nueva instancia de la clase.
5. **Uso de métodos**: Una vez que tenemos una instancia, podemos llamar a sus métodos.


## Diferencias entre Objetos literales y Clases
Tanto las clases como los objetos literales son formas de crear y manejar datos, pero tienen diferencias clave en cuanto a su uso y estructura.

### Objetos literales
Un objeto literal es una colección de pares clave-valor, donde cada clave es una cadena (o un símbolo) y cada valor puede ser cualquier tipo de dato, incluyendo funciones (métodos). Los objetos literales son útiles para crear estructuras de datos simples y únicas.

```js
// Creación de un objeto literal
const persona = {
    nombre: "Juan",
    edad: 30,
    saludar: function() {
        console.log(`Hola, mi nombre es ${this.nombre} y tengo ${this.edad} años.`);
    }
};

// Llamada al método saludar
persona.saludar(); // Salida: Hola, mi nombre es Juan y tengo 30 años.
```

### Clases
Las clases, por otro lado, son plantillas para crear múltiples objetos con la misma estructura y comportamiento. Las clases permiten la **encapsulación**, **herencia** y **reutilización** de código.

1. **Reutilización**: Las clases permiten crear múltiples instancias con la misma estructura y comportamiento, mientras que los objetos literales son únicos y no están diseñados para ser reutilizados como plantillas.
2. **Herencia**: Las clases soportan herencia, lo que permite crear nuevas clases basadas en clases existentes. Los objetos literales no soportan herencia directamente.
3. **Encapsulación**: Las clases permiten encapsular datos y métodos relacionados, lo que facilita la organización y el mantenimiento del código. Los objetos literales también encapsulan datos, pero no proporcionan una estructura tan clara para la reutilización y la herencia.
4. **Sintaxis**: Las clases usan una sintaxis más estructurada y familiar para quienes vienen de otros lenguajes de programación orientados a objetos. Los objetos literales tienen una sintaxis más simple y directa.

```js
// Definición de una clase
class Persona {
    constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    saludar() {
        console.log(`Hola, mi nombre es ${this.nombre} y tengo ${this.edad} años.`);
    }
}

// Creación de una instancia de la clase Persona
const persona1 = new Persona("Juan", 30);

// Llamada al método saludar
persona1.saludar(); // Salida: Hola, mi nombre es Juan y tengo 30 años.
```

