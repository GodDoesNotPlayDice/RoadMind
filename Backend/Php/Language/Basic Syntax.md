[[Backend/Php/Language/Variables|Variables]]
## Comentarios
Comentar código se hace con `//`

## Imprimir texto
Con el símbolo igual puedes hacer lo mismo que la otra syntax
```php
<?php echo 'Hello world usando Echo'; ?>
<?= "Hello World! sin Echo"; ?>
<?php print "XDDD siisi"; ?>
```

| Característica     | `echo`                                                                                | `print`                                                                                            |
| ------------------ | ------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Sintaxis           | Puede aceptar **varios** argumentos separados por comas:`echo "Hola ", $nombre, "!";` | Solo **un** argumento:`print "Hola Mundo";`                                                        |
| Valor de retorno   | **No** devuelve nada.                                                                 | Devuelve siempre `1`, por lo que puede usarse en expresiones:`$x = print "Hola";` asigna 1 a `$x`. |
| Velocidad          | Ligeramente más rápido.                                                               | Ligeramente más lento.                                                                             |
| Uso en estructuras | No puede usarse dentro de expresiones:`$x = (echo "Hola");` es inválido.              | Sí:`$x = print "Hola";` es válido.                                                                 |

### Tipo de variable
```php
$a = array(1, 2, array("a", "b", "c"));
var_dump($a);
?>
```

```out
array(3) { [0]=> int(1) [1]=> int(2) [2]=> array(3) { [0]=> string(1) "a" [1]=> string(1) "b" [2]=> string(1) "c" } }
```

```php
<?php  
$a = array ('a' => 'apple', 'b' => 'banana', 'c' => array ('x', 'y', 'z'));  
print_r($a);  
?>
```

```output
Array ( [a] => apple [b] => banana [c] => Array ( [0] => x [1] => y [2] => z ) )
```


|Característica|`print_r()`|`var_dump()`|
|---|---|---|
|Propósito|Mostrar una representación **legible** de arrays y objetos.|Mostrar **detalle completo**: tipo y longitud de cada valor.|
|Salida|Más limpia, sin indicar tipos ni longitudes:|Muy verbosa, incluye tipos, longitudes y estructuras:|
|Soporte de retorno|Devuelve la salida como string si le pasas segundo parámetro `true`:`$s = print_r($arr, true);`|No tiene parámetro de retorno.|
|Ideal para|Depurar estructuras de datos rápidas y sencillas.|Depuración profunda de variables y tipos.|
