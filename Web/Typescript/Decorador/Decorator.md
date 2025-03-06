Los decoradores en TypeScript son una característica poderosa que te permite modificar o extender el comportamiento de clases, métodos, propiedades, parámetros y accesores de manera declarativa.

**¿Qué es?**
Un decorador es una función especial que se puede adjuntar a una clase, método, propiedad, parámetro o accesor para modificar su comportamiento.

**Su uso común**
- Añadir metadatos.
- Modificar o extender funcionalidades.
- Validar o transformar datos.
- Inyectar dependencias.

## Tipos de Decoradores
1. **Decoradores de Clase**: Aplicados a una clase.
2. **Decoradores de Método**: Aplicados a métodos de una clase.
3. **Decoradores de Propiedad**: Aplicados a propiedades de una clase.
4. **Decoradores de Parámetro**: Aplicados a parámetros de un método.
5. **Decoradores de Accesor**: Aplicados a los getters y setters de una propiedad.


### Sintaxis Básica
Un decorador es una función que recibe diferentes argumentos dependiendo de dónde se aplique. La sintaxis general es:

```ts
@decorador
class MiClase { ... }
```


## Decorador de clase
```ts
function MiDecorador(target: Function) {
    console.log("Decorador aplicado a la clase:", target.name);
}

@MiDecorador
class MiClase {
    constructor() {
        console.log("Instancia de MiClase creada");
    }
}

const instancia = new MiClase();
```

## Decoradores de Método
Los decoradores de método reciben tres parámetros:
1. `target`: El prototipo de la clase (o el constructor si el método es estático).
2. `propertyKey`: El nombre del método.
3. `descriptor`: Un objeto `PropertyDescriptor` que describe el método.

```ts
function LogMethod(target: any, propertyKey: string, descriptor: PropertyDescriptor) {
    const originalMethod = descriptor.value;

    descriptor.value = function (...args: any[]) {
        console.log(`Llamando al método ${propertyKey} con argumentos:`, args);
        const result = originalMethod.apply(this, args);
        console.log(`Método ${propertyKey} retornó:`, result);
        return result;
    };

    return descriptor;
}

class Calculadora {
    @LogMethod
    sumar(a: number, b: number): number {
        return a + b;
    }
}

const calc = new Calculadora();
calc.sumar(2, 3);
```

## Decoradores de Propiedad
Los decoradores de propiedad reciben dos parámetros:

1. `target`: El prototipo de la clase (o el constructor si la propiedad es estática).
2. `propertyKey`: El nombre de la propiedad.

```ts
function DefaultValue(value: any) {
    return function (target: any, propertyKey: string) {
        target[propertyKey] = value;
    };
}

class MiClase {
    @DefaultValue(42)
    miPropiedad: number;
}

const instancia = new MiClase();
console.log(instancia.miPropiedad); // 42
```

## Decoradores de Parámetro
Los decoradores de parámetro reciben tres parámetros:

1. `target`: El prototipo de la clase (o el constructor si el método es estático).
2. `propertyKey`: El nombre del método.
3. `parameterIndex`: La posición del parámetro en la lista de argumentos.

```ts
function LogParameter(target: any, propertyKey: string, parameterIndex: number) {
    console.log(`Parámetro ${parameterIndex} del método ${propertyKey} en la clase ${target.constructor.name}`);
}

class MiClase {
    miMetodo(@LogParameter valor: number) {
        console.log("Valor:", valor);
    }
}

const instancia = new MiClase();
instancia.miMetodo(10);
```

## Decorador de Accesor
Los decoradores de accesor (getters y setters) reciben los mismos parámetros que los decoradores de método.

```ts
function LogAccess(target: any, propertyKey: string, descriptor: PropertyDescriptor) {
    const originalGet = descriptor.get;
    const originalSet = descriptor.set;

    descriptor.get = function () {
        console.log(`Obteniendo valor de ${propertyKey}`);
        return originalGet?.call(this);
    };

    descriptor.set = function (value: any) {
        console.log(`Estableciendo valor de ${propertyKey} a ${value}`);
        originalSet?.call(this, value);
    };
}

class MiClase {
    private _miPropiedad: number = 0;

    @LogAccess
    get miPropiedad(): number {
        return this._miPropiedad;
    }

    set miPropiedad(value: number) {
        this._miPropiedad = value;
    }
}

const instancia = new MiClase();
instancia.miPropiedad = 10; // Estableciendo valor de miPropiedad a 10
console.log(instancia.miPropiedad); // Obteniendo valor de miPropiedad
```

## Decoradores de Fábrica
Puedes crear decoradores que acepten parámetros usando funciones de fábrica:

```ts
function DecoradorConParametros(mensaje: string) {
    return function (target: any) {
        console.log(`${mensaje} aplicado a la clase ${target.name}`);
    };
}

@DecoradorConParametros("¡Hola!")
class MiClase { ... }
```

## Uso de Múltiples Decoradores
Puedes aplicar múltiples decoradores a una misma entidad. Se ejecutarán en orden de arriba hacia abajo.

```ts
@Decorador1
@Decorador2
class MiClase { ... }
```

## Consideraciones
Los decoradores son una característica experimental en TypeScript, por lo que debes habilitar la opción `experimentalDecorators` en tu archivo `tsconfig.json`:

```json
{
  "compilerOptions": {
    "experimentalDecorators": true
  }
}
```  

## Ejemplo completo

```ts
function LogClass(target: Function) {
    console.log(`Clase ${target.name} creada`);
}

function LogMethod(target: any, propertyKey: string, descriptor: PropertyDescriptor) {
    console.log(`Método ${propertyKey} decorado`);
}

function LogProperty(target: any, propertyKey: string) {
    console.log(`Propiedad ${propertyKey} decorada`);
}

@LogClass
class MiClase {
    @LogProperty
    miPropiedad: string;

    constructor(miPropiedad: string) {
        this.miPropiedad = miPropiedad;
    }

    @LogMethod
    mostrarPropiedad() {
        console.log(this.miPropiedad);
    }
}

const instancia = new MiClase("Hola, TypeScript");
instancia.mostrarPropiedad();
```


A continuación sigue [[Kind of Utility Types]]
