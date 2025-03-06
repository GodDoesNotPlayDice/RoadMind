En TypeScript, una clase es una plantilla para crear objetos. 

Define propiedades y métodos que los objetos creados a partir de la clase tendrán.

```ts
class Animal {
  nombre: string;
  constructor(nombre: string) {
    this.nombre = nombre;
  }
  hacerSonido() {
    console.log("Sonido genérico");
  }
}
```

## Parámetros del constructor
El constructor es un método especial que se llama cuando se crea una instancia de una clase. Los parámetros del constructor se utilizan para inicializar las propiedades del objeto.

```ts
class Animal {
  constructor(public nombre: string) {}
}
```

## Modificadores de acceso
- TypeScript soporta modificadores de acceso como `public`, `private`, y `protected` para controlar la visibilidad de las propiedades y métodos.
- `public`: Accesible desde cualquier lugar.
- `private`: Accesible solo dentro de la clase.
- `protected`: Accesible dentro de la clase y sus subclases.

```ts
class Animal {
  private nombre: string;
  constructor(nombre: string) {
    this.nombre = nombre;
  }
}
```

## Clases abstractas
Una clase abstracta no puede ser instanciada directamente y está diseñada para ser heredada. Puede contener métodos abstractos que deben ser implementados por las subclases.

```ts
abstract class Animal {
  abstract hacerSonido(): void;
}
```

## Herencia vs Polimorfismo

**Herencia**: Permite a una clase heredar propiedades y métodos de otra clase. Esto promueve la reutilización de código.

**Polimorfismo**: Permite a las clases derivadas ser tratadas como instancias de su clase base, pero con comportamientos específicos.

```ts
class Perro extends Animal {
  hacerSonido() {
    console.log("Guau");
  }
}
```


## Method Overriding (Sobreescritura de Métodos)
La sobreescritura de métodos permite a una subclase proporcionar una implementación específica de un método que ya está definido en su clase base.

```ts
class Gato extends Animal {
  hacerSonido() {
    console.log("Miau");
  }
}
```

## Constructor Overloading (Sobrecarga de constructores)
TypeScript no soporta sobrecarga de constructores directamente como otros lenguajes, pero puedes lograr un comportamiento similar usando parámetros opcionales o uniones de tipos.

```ts
class Animal {
  constructor(nombre: string, edad?: number) {
    // ...
  }
}
```

Continuación con [[Generic Types and Constraints]]