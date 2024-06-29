## Conceptos claves
**Nil**: Nulo

## Variables y Sintaxis

```ruby
# Variables

variable_string = "Hola"
variable_numero = 20
CONSTANTE = 15
$variable_global = 20
array = [1, 2, 3, 4, 5]

  

## Interpolacion de variables

puts "Variable normal: #{variable_string}"
puts "Constante: #{CONSTANTE}"

  

## Clase del objeto

puts "Variable normal: #{variable_string.class}"

## Depurar variables

puts "Variable array: #{array.inspect}"

## Verificacion de nulos

puts "Variable normal: #{variable_string.nil?}" # verifica si la variable es nula
puts "Variable normal: #{variable_numero.zero?}" # verifica si la variable es cero


## Verificar si esta definida

puts "Variable normal: #{defined?(variable_string)}"

  
## Congela el objeto

variable_string.freeze
puts "Variable normal: #{variable_string.frozen?}" # verifica si el objeto esta congelado
variable_string << 5 # No se puede modificar el objeto congelado

## Duplicar variable

variable_normal_dup = variable_string.dup
variable_normal_dup << 5
puts "Variable normal: #{variable_normal_dup}"

```

## Strings

### Methods

```ruby
string = "Hola como estas?"

# Metodos
string.length # Cantidad de caracteres
string.upcase # Mayusculas
string.downcase # Minusculas
string.capitalize # Primera letra en mayuscula
string.reverse # Invierte el string
string.swapcase # Invierte mayusculas y minusculas
string.start_with?("Hola") # Comienza con
string.end_with?("estas?") # Termina con
string.include?("como") # Incluye la palabra
string.gsub("Hola", "Chau") # Reemplaza
string.split # Separa por palabras
string.lstrip # Elimina espacios a la izquierda
string.rstrip # Elimina espacios a la derecha
string.split(/(\s+)/) #divide la cadena en palabras y espacios, manteniendo los espacios como elementos en el array.
string.concat(" Bien y vos?") # Concatena strings
string.tr("a", "o") # Reemplaza caracteres
string.empty? # Esta vacio?
string.index("como") # Posicion de la palabra
string.rindex("como") # Posicion de la palabra desde la derecha
string.insert(4, "estas ") # Inserta en la posicion
string.casecmp("hola como estas?") # Compara sin importar mayusculas o minusculas
string.casecmp?("hola como estas?") # Compara sin importar mayusculas o minusculas (booleano)
string.delete("a") # Elimina caracteres
string.delete_prefix("Hola") # Elimina prefijo
string.delete_suffix("estas?") # Elimina sufijo
string.chomp # Elimina el ultimo caracter
string.chomp("as?") # Elimina el ultimo caracter si es igual al parametro
string.chomp! # Elimina el ultimo caracter
string.chomp!("as?") # Elimina el ultimo caracter si es igual al parametro
"123".to_i # Transforma strings a numeros
"123.4".to_f # Transforma de strings a floats.

```
#### gsub
`gsub` es un método en Ruby que se usa para buscar y reemplazar todas las ocurrencias de una expresión regular en una cadena.
`str.gsub(/\S+/, &:reverse)` = `str.gsub(/\S+/) { |match| match.reverse }`

**usando &**: `&` antes de un símbolo convierte ese símbolo en un bloque de código que envía el mensaje correspondiente a cada elemento.


## Números 

```ruby
a = 10
## Metodos enteros

-a.abs # Valor absoluto
a.even? # Es par?
a.odd? # Es impar?
a.next # Siguiente
a.pred # Anterior
a.to_f # Transforma a float
a.to_s # Transforma a string
a.to_i # Transforma a entero
a.round # Redondea
a.ceil # Redondea hacia arriba
a.floor # Redondea hacia abajo
a.to_r # Transforma a racional
a.to_c # Transforma a complejo
a.times { |i| puts i } # Itera la cantidad de veces
a.upto(20) { |i| puts i } # Itera desde el numero hasta el parametro
a.downto(0) { |i| puts i } # Itera desde el numero hasta el parametro
a.step(20, 2) { |i| puts i } # Itera desde el numero hasta el parametro con saltos
a.infinite? # Es infinito?
a.zero? # Es cero?
a.nonzero? # No es cero?
a.positive? # Es positivo?
a.negative? # Es negativo?
a.finite? # Es finito?
```

## Operadores aritméticos

```ruby
a = 5
b = 3

a - b # resta
a + b # suma
a * b # multiplicación
a / b # división
a % b # módulo
a ** b # potencia
a += b # a = a + b
a -= b # a = a - b
a *= b # a = a * b
a /= b # a = a / b
a %= b # a = a % b
a **= b # a = a ** b
a.div(b) # división entera
a.divmod(b) # división entera y módulo
a.modulo(b) # módulo
a.gcd(b) # máximo común divisor
a.lcm(b) # mínimo común múltiplo
3.75.rationalize # racional
```


## Operadores lógicos

```ruby
a = true
b = false
  
a && b # Hace un AND
a and b # Hace un AND
a || b # Hace un OR
a or b # Hace un OR
!a # Hace un NOT
!b # Hace un NOT
a && !b # Hace un AND y un NOT
a || !b # Hace un OR y un NOT
a && b || a # Hace un AND, un OR y un OR
a && (b || a) # Hace un AND y un OR
a || (b && a) # Hace un OR y un AND
```


