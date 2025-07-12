```php
function foo($arg_1, $arg_2, /* ..., */ $arg_n)
{
    echo "Example function.\n";
    return $retval;
}
```

## Recursión
```php
function recursion($a)
{
    if ($a < 20) {
        echo "$a\n";
        recursion($a + 1);
    }
}
```

## Parámetros opcionales y named
```php
function greet($name = "guest"): string {
  return "Hello! " . $name;
}

echo greet("Jhon")
```

```php
$a = array_fill(start_index: 0, count: 100, value: 50);
```

## Función anónima
```php
$greet = function($name)
{
    printf("Hello %s\r\n", $name);
};

$greet('World');
$greet('PHP');
```

## Función Flecha

```php
$y = 1;      
$fn1 = fn($x) => $x + $y;
```

Es equivalente a esto.
```php
$fn2 = function ($x) use ($y) {
    return $x + $y;
};
```

