
## Creación y Acceso

1. **Crear Arrays**
```ruby
array = [1, 2, 3, 4, 5]
array_vacio = []
```

2. **Acceder a elementos**
```ruby
array = [1, 2, 3, 4, 5]
array[0]  # => 1
array[2]  # => 3
array[-1] # => 5 (último elemento)
```

3. **Asignar valores**
```ruby
array[2] = 10
puts array.inspect  # => [1, 2, 10, 4, 5]
```

4. **Slices (Subarrays)**
```ruby
array = [1, 2, 3, 4, 5]
array[1, 3]  # => [2, 3, 4] (desde el índice 1, toma 3 elementos)
array[1..3]  # => [2, 3, 4] (desde el índice 1 hasta el 3, inclusivo)
```

## Métodos de Modificación

1. **push y <<**

```ruby
array = [1, 2, 3]
array.push(4)  # => [1, 2, 3, 4]
array << 5    # => [1, 2, 3, 4, 5]
```

2. **pop**

```ruby
array = [1, 2, 3, 4, 5]
array.pop  # => 5
puts array.inspect  # => [1, 2, 3, 4]
```

3. **shift (Eliminar y retornar el primer elemento)**

```ruby
array = [1, 2, 3, 4, 5]
array.shift  # => 1
puts array.inspect  # => [2, 3, 4, 5]
```

4. **unshift (Añadir elementos al principio)**

```ruby
array = [2, 3, 4, 5]
array.unshift(1)  # => [1, 2, 3, 4, 5]
```

5. **Insert (Insertar elementos en una posición en especifico)**

```ruby
array = [1, 2, 4, 5]
array.insert(2, 3)  # => [1, 2, 3, 4, 5]
```

6. **delete (Eliminar elementos por valor)**

```ruby
array = [1, 2, 3, 4, 5, 3]
array.delete(3)  # => 3
puts array.inspect  # => [1, 2, 4, 5]
```
## Métodos de consulta

1. **length o size**

```ruby
array = [1, 2, 3, 4, 5]
array.length  # => 5
array.size    # => 5
```

2. **empty? (Verifica si esta vacio)**

```ruby
array = []
array.empty?  # => true
```

3. **Include (Verifica si un elemento esta presente)**

```ruby
array = [1, 2, 3, 4, 5]
array.include?(3)  # => true
```

## Métodos de transformación

1. **map (Transformar cada elemento a un bloque)**

```ruby
array = [1, 2, 3, 4, 5]
nuevo_array = array.map { |n| n * 2 }
puts nuevo_array.inspect  # => [2, 4, 6, 8, 10]
```

2. **select (Seleccionar elementos que cumplen una condición)**

```ruby
array = [1, 2, 3, 4, 5]
pares = array.select { |n| n.even? }
puts pares.inspect  # => [2, 4]
```

3. **reject (Eliminar elementos que cumplen una condición)**

```ruby
array = [1, 2, 3, 4, 5]
impares = array.reject { |n| n.even? }
puts impares.inspect  # => [1, 3, 5]
```

4. **uniq (Eliminar elementos duplicados)**

```ruby
array = [1, 2, 3, 3, 4, 5, 5]
unico = array.uniq
puts unico.inspect  # => [1, 2, 3, 4, 5]
```

5. **flatten (Aplanar un array de arrays)**. 

```ruby
array = [1, [2, 3], [4, [5, 6]]]
aplanado = array.flatten
puts aplanado.inspect  # => [1, 2, 3, 4, 5, 6]
```

## Extras

**join ( Convertir un array a string )**

```ruby
array = [1, 2, 3, 4, 5]
cadena = array.join(", ")
puts cadena  # => "1, 2, 3, 4, 5"
```

**reverse (Invertir el array)**

```ruby
array = [1, 2, 3, 4, 5]
invertido = array.reverse
puts invertido.inspect  # => [5, 4, 3, 2, 1]
```

**sort (Ordenar el array)**

```ruby
array = [5, 3, 1, 4, 2]
ordenado = array.sort
puts ordenado.inspect  # => [1, 2, 3, 4, 5]
```

**zip (Combinar elementos de multiples arrays)**

```ruby
array1 = [1, 2, 3]
array2 = [4, 5, 6]
combinados = array1.zip(array2)
puts combinados.inspect  # => [[1, 4], [2, 5], [3, 6]]
```


