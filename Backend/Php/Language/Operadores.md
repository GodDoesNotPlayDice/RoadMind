
# Aritméticos 
```php
$c = $a + $b;
$c = $a - $b;
$c = $a * $b;
$c = $a / $b;
$c = $a % $b;
$c = $a ** $b; // $a elevado a $b
```

# Asignación
```php
// Simple
$x = 5;
// Combinada
$x += 3;  // equivale a $x = $x + 3
$x -= 2;  // $x = $x - 2
$x *= 4;  // $x = $x * 4
$x /= 2;  // $x = $x / 2
$x %= 3;  // $x = $x % 3
$x **= 2; // $x = $x ** 2
$a = 1;
$b =& $a; // $b es alias de $a

```

Estos son de preferencia
```php
$a = 1;
$b =& $a; // $b es alias de $a

```

# Comparación
- Igualdad (con conversión de tipo): `==`
- Identidad (sin conversión, mismo tipo y valor): `===`
- Desigualdad: `!=` ó `<>`
- No idéntico: `!==`
- Menor que / Mayor que: `<` / `>`
- Menor o igual / Mayor o igual: `<=` / `>=`
- Nave espacial (retorna –1,0,1): `<=>`

```php
var_dump(2 <=> 3); // int(-1)
var_dump(3 <=> 3); // int(0)
var_dump(4 <=> 3); // int(1)
```

# Incremento y Decremento
- Pre-incremento: `++$i`
- Post-incremento: `$i++`
- Pre-decremento: `--$i`
- Post-decremento: `$i--`

```php
$i = 5;
echo $i++; // imprime 5, luego $i vale 6
echo ++$i; // primero incrementa a 7, luego imprime 7
```

# Lógicos
- AND: `&&` y `and`
- OR: `||` y `or`
- XOR: `xor`
- NOT: `!`

```php
if ($a && $b) { … }
if ($a or $b)  { … }
if ($a xor $b) { … }
if (! $a)      { … }
```

## Bits
- AND: `&`
- OR: `|`
- XOR: `^`
- NOT: `~`
- Desplazamiento a la izquierda: `<<`
- Desplazamiento a la derecha: `>>`
```php
$c = $a & $b;
$d = $a << 2; // desplaza bits de $a dos posiciones a la izquierda
```

# Concatenación
- Concatenación: `.`
- Concatenación asignativa: `.=`

```php
$s = "Hola";
$s .= " mundo"; // ahora "Hola mundo"
```

# Arreglo
- Acceso / asignación de elementos: `[]`
- Operador de fusión de arreglos (PHP 7.4+): `+`

```php
$a = ['x' => 1];
$b = ['y' => 2];
$c = $a + $b; // ['x'=>1, 'y'=>2]
```

```php
$sq = fn($n) => $n * $n;
```


# Condicionales
- Ternario: `condición ? expr1 : expr2`
- Ternario simplificado (PHP 5.3+): `expr1 ?: expr2`
- Null coalescing: `??`
- Asignación con null coalescing (PHP 7.4+): `??=`

```php
$x = $_GET['id'] ?? 'default';
$y ??= 10; // si $y no existe o es null, se le asigna 10
```

# Ejecución
Backticks (shell): `` `comando` ``
```php
$out = `ls -la`;
```

# Control de errores
Silenciar errores con : `@`
```php
$f = @file('no_existe.txt');
```

# Tipo e instancia
```php
if ($obj instanceof MiClase) { … }
```
Operador `new` para crear objetos

```php
$o = new MiClase();
```

