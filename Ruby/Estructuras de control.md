#### Condicionales

1. **`if`, `elsif`, `else`**
- Evalúa condiciones y ejecuta bloques de código en consecuencia.

```ruby
edad = 18

if edad < 18
  puts "Menor de edad"
elsif edad == 18
  puts "Exactamente 18 años"
else
  puts "Mayor de edad"
end
```

2. **unless**
- Ejecuta un bloque de código a menos que la condición sea verdadera.

```ruby
a = 5
unless a > 10
  puts "a no es mayor que 10"
end
```

3. **Operadores ternarios**
- Una forma abreviada de escribir un `if-else`.
```ruby
edad = 20
mensaje = edad >= 18 ? "Mayor de edad" : "Menor de edad"
puts mensaje  # => "Mayor de edad"
```

4. **case**
- Similar a `switch` en otros lenguajes, se usa para comparar un valor con múltiples condiciones.
```ruby
calificacion = 'B'

case calificacion
when 'A'
  puts "Excelente"
when 'B'
  puts "Bueno"
when 'C'
  puts "Suficiente"
else
  puts "Insuficiente"
end
```


#### Bucles

1. **`while`**
- Ejecuta un bloque de código mientras la condición sea verdadera.
```ruby

i = 0
while i < 5 do
  puts i
  i += 1
end
# Output:
# 0
# 1
# 2
# 3
# 4
```

2. **`until`**
- Ejecuta un bloque de código hasta que la condición se vuelva verdadera.
```ruby
i = 0
until i > 5 do
  puts i
  i += 1
end
# Output:
# 0
# 1
# 2
# 3
# 4
# 5
```

3. **`for`**
- Itera sobre un rango o una colección.
```ruby
for i in 1..5 do
  puts i
end
# Output:
# 1
# 2
# 3
# 4
# 5
```

**Métodos de iteración (`each`, `map`, etc.)**
- Itera sobre elementos de una colección usando bloques.
```ruby
[1, 2, 3, 4, 5].each do |i|
  puts i
end
# Output:
# 1
# 2
# 3
# 4
# 5

cuadrados = [1, 2, 3, 4, 5].map { |i| i * i }
puts cuadrados.inspect  # => [1, 4, 9, 16, 25]
```

#### Otras Estructuras de Control

1. **`break`**
    - Termina un bucle prematuramente.
```ruby
i = 0
while i < 10 do
  break if i == 5
  puts i
  i += 1
end
# Output:
# 0
# 1
# 2
# 3
# 4
```

2. **`next`**
- Salta a la siguiente iteración del bucle.
```ruby
for i in 0..5 do
  next if i % 2 == 0
  puts i
end
# Output:
# 1
# 3
# 5
```


3. **rendo**
- Repite una iteración actual de un bucle
```ruby

i = 0
while i < 5 do
  i += 1
  redo if i == 3
  puts i
end
# Este ejemplo causará un bucle infinito ya que `redo` reiniciará la iteración actual.
```
2