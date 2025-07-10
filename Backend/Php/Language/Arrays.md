
# Tipos de array
Como bien sabemos el array se crea de dos formas **Asociativa** o **Indexzativa**.

**Asociativa**
Es cuando el array tiene un indice declarado.
```php
<?php  
$array1 = array(  
"foo" => "bar",  
"bar" => "foo",  
);  
  
// Using the short array syntax  
$array2 = [  
"foo" => "bar",  
"bar" => "foo",  
];  
  
var_dump($array1, $array2);  
?>
```

Los indices se pueden asignar de cualquier tipo

```php
<?php  
$array = array(  
1 => "a",  
"1" => "b",  
1.5 => "c",  
true => "d",  
);  
var_dump($array);  
?>
```

También se pueden combinar tipos dentro de los arrays

```php
<?php  
$array = array(  
"foo" => "bar",  
"bar" => "foo",  
100 => -100,  
-100 => 100,  
);  
var_dump($array);  
?>
```

Pa volverse loco.

```php
<?php  
$array = array(  
1 => 'a',  
'1' => 'b', // the value "a" will be overwritten by "b"  
1.5 => 'c', // the value "b" will be overwritten by "c"  
-1 => 'd',  
'01' => 'e', // as this is not an integer string it will NOT override the key for 1  
'1.5' => 'f', // as this is not an integer string it will NOT override the key for 1  
true => 'g', // the value "c" will be overwritten by "g"  
false => 'h',  
'' => 'i',  
null => 'j', // the value "i" will be overwritten by "j"  
'k', // value "k" is assigned the key 2. This is because the largest integer key before that was 1  
2 => 'l', // the value "k" will be overwritten by "l"  
);  
  
?>
```

**Indexativa**
Acá php asigna automáticamente los indices.

```php
 <?php  
$array = array("foo", "bar", "hello", "world");  
var_dump($array);  
?>
```

**Negativo**
Ya pa esto es locura maxima XD, es porque asigna el valor a un indice que no existe pero como ya hay un -5 ademas de que empieza del -5 asigna n+1 por lo que el indice sera -4 = 2 XDDD, prácticamente es un "append".

```php
<?php  
$array = [];  
  
$array[-5] = 1;  
$array[] = 2;  
  
var_dump($array);  
?>
```

## Borrar elementos del array

 `unset`: sirve para borrar un elemento del array o todo el array dependiendo de su uso

```php
<?php  
$arr = array(5 => 1, 12 => 2);  
  
$arr[] = 56; // This is the same as $arr[13] = 56;  
// at this point of the script  
  
$arr["x"] = 42; // This adds a new element to  
// the array with key "x"  
  
unset($arr[5]); // This removes the element from the array  
  
var_dump($arr);  
  
unset($arr); // This deletes the whole array  
  
var_dump($arr);  
?>
```

## Destructuring

```php
<?php  
$source_array = ['foo', 'bar', 'baz'];  
  
[$foo, $bar, $baz] = $source_array;
  
echo $foo, PHP_EOL; // prints "foo"  
echo $bar, PHP_EOL; // prints "bar"  
echo $baz, PHP_EOL; // prints "baz"  
?>
```

Es posible ignorar ciertos elementos al momento de destructurar.
```php
<?php  
$source_array = ['foo', 'bar', 'baz'];  
  
// Assign the element at index 2 to the variable $baz  
[, , $baz] = $source_array;  
  
echo $baz; // prints "baz"  
?>
```

También es posible destructurar arrays asociativos
```php
<?php  
$source_array = ['foo' => 1, 'bar' => 2, 'baz' => 3];  
  
// Assign the element at index 'baz' to the variable $three  
['baz' => $three] = $source_array;  
  
echo $three, PHP_EOL; // prints 3  
  
$source_array = ['foo', 'bar', 'baz'];  
  
// Assign the element at index 2 to the variable $baz  
[2 => $baz] = $source_array;  
  
echo $baz, PHP_EOL; // prints "baz"  
?>
```

## Clonar arrays

```php
<?php  
$a = array(1 => 'one', 2 => 'two', 3 => 'three');  
  
/* will produce an array that would have been defined as  
$a = array(1 => 'one', 3 => 'three');  
and NOT  
$a = array(1 => 'one', 2 =>'three');  
*/  
unset($a[2]);  
var_dump($a);  
  
$b = array_values($a);  
// Now $b is array(0 => 'one', 1 =>'three')  
var_dump($b);  
?>
```

### Locuras

Intercambiar valores.
```php
<?php  
$a = 1;  
$b = 2;  
  
[$b, $a] = [$a, $b];  
  
echo $a, PHP_EOL; // prints 2  
echo $b, PHP_EOL; // prints 1  
?>
```

## Unpacking

Se puede hacer unpacking usando el **spread operator.**
```php
<?php  
// Using short array syntax.  
// Also, works with array() syntax.  
$arr1 = [1, 2, 3];  
$arr2 = [...$arr1]; // [1, 2, 3]  
$arr3 = [0, ...$arr1]; // [0, 1, 2, 3]  
$arr4 = [...$arr1, ...$arr2, 111]; // [1, 2, 3, 1, 2, 3, 111]  
$arr5 = [...$arr1, ...$arr1]; // [1, 2, 3, 1, 2, 3]  
  
function getArr() {  
return ['a', 'b'];  
}  
$arr6 = [...getArr(), 'c' => 'd']; // ['a', 'b', 'c' => 'd']  
  
var_dump($arr1, $arr2, $arr3, $arr4, $arr5, $arr6);  
?>
```


Se puede hacer unpacking con el indice duplicado y dejara el ultimo valor del unpacking.
```php
<?php

// string key
$arr1 = ["a" => 5];
$arr2 = ["a" => 10];
$arr4 = ["a" => 2];
$arr3 = ["a" => 0, ...$arr1, ...$arr2, ...$arr4];
var_dump($arr3); // ["a" => 2]

?>
```


## Leer directorios
Se pueden leer directorios y hacerles append a un array.

```php
<?php
// 1. Directorio actual
$dir = __DIR__;
// 2. Abrir el directorio
$handle = opendir($dir);
// 3. Inicializar array
$files = [];
// 4. Leer ficheros
while (false !== ($file = readdir($handle))) {
// Excluir referencias a directorio actual y padre
if ($file === '.' || $file === '..') { continue; } $files[] = $file; }
// 5. Cerrar manejador
closedir($handle);

?>

<!doctype html>

<html lang="es">
  <head>
    <meta charset="UTF-8" />

    <title>Listado de ficheros</title>
  </head>

  <body>
    <h1>Archivos en “<?php echo htmlspecialchars(basename($dir)); ?>”</h1>

    <?php if (empty($files)): ?>

    <p>No hay ficheros en este directorio.</p>

    <?php else: ?>

    <ul>
      <?php foreach ($files as $f): ?>

      <li>
        <!-- Creamos un enlace al propio fichero -->

        <a href="<?php echo urlencode($f); ?>">
          <?php echo htmlspecialchars($f); ?>
        </a>
      </li>

      <?php endforeach; ?>
    </ul>

    <?php endif; ?>
  </body>
</html>

```

## Multidimensional

Se pueden agregar arrays dentro arrays.
```php
$users = array(
       array("John", "john@example.com", "john123"),
       array("Jane", "jane@example.com", "jane123"),
       array("Doe", "doe@example.com", "doe123")
);
```

