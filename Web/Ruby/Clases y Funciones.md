En Ruby, las clases y los métodos (funciones) son fundamentales para la programación orientada a objetos.
## Clases
#### Definiendo una Clase

Una clase en Ruby se define usando la palabra clave `class`, seguida del nombre de la clase. Por convención, los nombres de las clases utilizan la notación Camel-Case.

```ruby
class Persona
  # código de la clase
end
```

#### Atributos de Clase

Puedes definir atributos de clase utilizando `attr_accessor`, `attr_reader` y `attr_writer`.

- `attr_accessor` define tanto los métodos de lectura como de escritura para los atributos.
- `attr_reader` define solo los métodos de lectura.
- `attr_writer` define solo los métodos de escritura.

```ruby
class Persona
  attr_accessor :nombre, :edad
  attr_reader :dni
  attr_writer :direccion
end
```

#### Inicializador (`initialize`)

El método `initialize` se llama automáticamente cuando se crea una nueva instancia de la clase. Se utiliza para inicializar los atributos de la clase.

```ruby
class Persona
  attr_accessor :nombre, :edad
  
  def initialize(nombre, edad)
    @nombre = nombre
    @edad = edad
  end
end
```


#### Métodos de Instancia

Los métodos de instancia se definen usando la palabra clave `def` dentro de la clase. Estos métodos se pueden llamar en objetos de la clase.

```ruby
class Persona
  attr_accessor :nombre, :edad

  def initialize(nombre, edad)
    @nombre = nombre
    @edad = edad
  end

  def presentarse
    "Hola, me llamo #{@nombre} y tengo #{@edad} años."
  end
end

persona = Persona.new("Juan", 30)
puts persona.presentarse  # => "Hola, me llamo Juan y tengo 30 años."
```



#### Métodos de Clase

Los métodos de clase se definen utilizando `self.` antes del nombre del método. Estos métodos se llaman en la propia clase y no en instancias de la clase.

```ruby

class Persona
  attr_accessor :nombre, :edad

  def initialize(nombre, edad)
    @nombre = nombre
    @edad = edad
  end

  def self.saludar
    "Hola a todos!"
  end
end

puts Persona.saludar  # => "Hola a todos!"


```

#### Herencia

Ruby soporta la herencia, lo que permite que una clase herede los atributos y métodos de otra clase.

```ruby

class Persona
  attr_accessor :nombre, :edad

  def initialize(nombre, edad)
    @nombre = nombre
    @edad = edad
  end

  def presentarse
    "Hola, me llamo #{@nombre} y tengo #{@edad} años."
  end
end

class Estudiante < Persona
  attr_accessor :grado

  def initialize(nombre, edad, grado)
    super(nombre, edad)
    @grado = grado
  end

  def presentarse
    super + " Estoy en el grado #{@grado}."
  end
end

estudiante = Estudiante.new("Ana", 20, "Ingeniería")
puts estudiante.presentarse  # => "Hola, me llamo Ana y tengo 20 años. Estoy en el grado Ingeniería."

```


#### Ejemplo completo

```ruby
class Persona
  attr_accessor :nombre, :edad

  def initialize(nombre, edad)
    @nombre = nombre
    @edad = edad
  end

  def presentarse
    "Hola, me llamo #{@nombre} y tengo #{@edad} años."
  end
end

class Estudiante < Persona
  attr_accessor :grado

  def initialize(nombre, edad, grado)
    super(nombre, edad)
    @grado = grado
  end

  def presentarse
    super + " Estoy en el grado #{@grado}."
  end
end

# Crear instancias y llamar métodos
persona = Persona.new("Juan", 30)
puts persona.presentarse  # => "Hola, me llamo Juan y tengo 30 años."

estudiante = Estudiante.new("Ana", 20, "Ingeniería")
puts estudiante.presentarse  # => "Hola, me llamo Ana y tengo 20 años. Estoy en el grado Ingeniería."

```


