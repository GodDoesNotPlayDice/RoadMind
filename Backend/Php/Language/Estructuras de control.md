
# If / else
Esta es una condicional simple, sin llaves "{}", por lo que solo se puede aplicar un "return".
```php
<?php   if ($a > $b)   echo "a is bigger than b";   ?>
```

En cambio esta condicional si es posible asignar llaves para aplicar mas declaraciones.
```php
<?php   if ($a > $b) {   echo "a is bigger than b";   $b = $a;   }   ?>
```

Esto no se sigue usándose hoy en día, pero es una manera de mostrar contenido dependiendo de la condición y mostrara el html.
```php
<?php if (condition): ?>      
// html code to run if condition is true     
<?php else: ?>      
// html code to run if condition is false      
<?php endif ?>
```

Condicional multiple.
```php
if( ($a==1 || $a==2) && ($b==3 || $b==4) && ($c==5 || $c==6) ) {   
	//do that something here.
}
```

Así se aplica el `else`.
```php
<?php
	if ($a > $b) {   
		echo "a is greater than b";   
	} else {   
		echo "a is NOT greater than b";   }   
?>
```

Condicional anidado.
```php
<?php
	$a = false;
	$b = true;   
	if ($a)
		if ($b)   
			echo "b";   
		else   
			echo "c";   
			
?>
```

Y por ultimo se puede aplicar **else if**
```php
<?php   if ($a > $b) {   
	echo "a is bigger than b";   
	} elseif ($a == $b) {   
		echo "a is equal to b";   }
	else {   
		echo "a is smaller than b";   }   
?>
```

## Es posible hacer la estructura de control sin las llaves

```php
<?php   /* Correct Method: */
if ($a > $b):
	echo $a." is greater than ".$b;
elseif ($a == $b):
// Note the combination of the words.   
	echo $a." equals ".$b;
else:   
	echo $a." is neither greater than or equal to ".$b;   
endif;      
?>
```


```php
<?php   
	if ($a == 5):
	   echo "a equals 5";
	   echo "...";
	elseif ($a == 6):
	   echo "a equals 6";
	   echo "!!!";
	else:   
		echo "a is neither 5 nor 6";
	endif;   
?>
```

# Switch y Match

```php
switch ($fruit) {
  case "apple":
    echo "You chose apple.";
    break;
  case "banana":
    echo "You chose banana.";
    break;
  default:
    echo "Invalid choice.";
}
```

Match es una feature introducida en php 8.0 y es el killer de **switch** ya que es mas simple y no necesitas **break** para poder funcionar.
```php
$message = match ($statusCode) {
  200, 300 => 'OK',
  400 => 'error',
  default => 'unknown status code',
};


```


# Null Coalescing
Este operador es literalmente como el operador ternario de javascript, y ademas se puede asignar más condiciones **if / else** a través de **??**.

```php
$username = isset($_GET['user']) ? $_GET['user'] : 'nobody'; // isset es mas verboso
```

Esta es una version mas corta de su uso.
```php
$_GET = ['user' => null];

$username = $_GET['user'] ?? 'nobody';

$username = $_GET['user'] ?? $_POST['user'] ?? 'nobody';
echo "Hello, $username!";

?>
```


# Null Safe Operator
Antes se anidaban los nulls así.
```php
$country =  null;
 
if ($session !== null) {
    $user = $session->user;
 
    if ($user !== null) {
        $address = $user->getAddress();
 
        if ($address !== null) {
            $country = $address->country;
        }
    }
}
```

Pero hoy en día hacer esta solución es penca, por lo que es mejor usar **?** para indicar la existencia de nulls.

```php
$country = $session?->user?->getAddress()?->country;
```


# Loops

## Bucle While
```php
$i = 1;
while ($i <= 10){
	echo $i++; 
	}
```

Con endwhile
```php
$i = 1;
while ($i <= 10):
	echo $i;
	$i++;
endwhile;
?>
```

## Do While
```php
<?php   
$i = 0;
do {
	echo $i;
} while ($i > 0);   
?>
```

## For

```php
for ($i = 1; $i <= 10; $i++) {
	echo $i;
}
```

```php
for ($i = 1; ; $i++) {
	if ($i > 10) {   
		break;
	}   
	echo $i;
} 
```

```php
for (; ;) {
	if ($i > 10) {   
		break;
	}   
	echo $i;
} 
```
- **Inicialización:** nada (vacío)
- **Condición:** nada (vacío → se asume `true`)
- **Paso:** nada (vacío)


Este ultimo bucle es para flexear.
```php
for ($i = 1, $j = 0; $i <= 10; $j += $i, print $i, $i++);   ?>
```

## For Each

```php
$array = [1, 2, 3, 17];
foreach ($array as $value) {
	echo "Current element of \$array: $value.\n";
}
```

For each con key osea el indice.
```php
$array = [
"one" => 1,
"two" => 2,
"three" => 3,
"seventeen" => 17
];
foreach ($array as $key => $value) {
	echo "Key: $key => Value: $value\n";
}
```

For each con multi-array.
```php
$grid = [];
$grid[0][0] = "a";
$grid[0][1] = "b";
$grid[1][0] = "y";
$grid[1][1] = "z";

foreach ($grid as $y => $row) {
    foreach ($row as $x => $value) {
        echo "Value at position x=$x and y=$y: $value\n";
    }
}
```

For each con **range**.
```php
/* Example: dynamic arrays */
foreach (range(1, 5) as $value) {
echo "$value\n";
}
```

