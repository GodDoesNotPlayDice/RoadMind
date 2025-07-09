# Scalar Types
## Integers
Números enteros, positivos o negativos.
```php
$a = 42;
$b = -7;
$hex = 0xFF;    // 255 en hexadecimal
$bin = 0b1010;  // 10 en binario
```
## Floats
Números con parte decimal o notación científica.
```php
$precio     = 19.99;
$cientifico = 1.2e3;  // 1200
```

## Strings
- **Simples**: no interpretan variables ni escapes (salvo \’ y \\).
- **Dobles**: interpolan variables y secuencias de escape (`\n`, `\t`, etc.).
```php
$nombre      = 'Pragmir';
$saludo      = "Hola, $nombre\n";  // interpola $nombre
$rutaWindows = "C:\\xampp\\htdocs";
```

## Bool
Sólo dos valores: `true` o `false`. Muy usado en condicionales.

```php
$activo = true;
if ($activo) {
    echo "Está activo\n";
}
```


# Compound Types (compuestos)
## Array
Colección ordenada (indexada) o asociativa de valores.
### Indexado
```php
$colores = ['rojo', 'verde', 'azul'];
echo $colores[1]; // verde
```

### Asociativo
```php
$persona = [
    'nombre' => 'xaxa',
    'edad'   => 32
];
echo $persona['nombre']; // Pragmir
```


## Object
Instancias de clases, con propiedades y métodos.

```php
class Usuario {
    public $nombre;
    public function __construct($n) {
        $this->nombre = $n;
    }
    public function saludar() {
        return "¡Hola, {$this->nombre}!";
    }
}

$u = new Usuario('Pragmir');
echo $u->saludar(); // ¡Hola, Pragmir!
```