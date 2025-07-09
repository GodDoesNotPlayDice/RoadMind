Las variables en **PHP** tienen alcance de **función** o **global**.
# Declaración de variables y constantes
## Variables
Las variables se declaran con **$**.
```php
$variable = 123
```

|Variable|Válida / Inválida|Por qué|
|---|---|---|
|`$nombre`|Válida|Empieza con letra, solo ASCII|
|`$_apellido`|Válida|Empieza con guion bajo|
|`$usuario1`|Válida|Dígito permitido tras la primera letra|
|`$1usuario`|Inválida|No puede empezar con dígito|
|`$mi-variable`|Inválida|El guion medio no está permitido|
|`$mi variable`|Inválida|El espacio no está permitido|
|`$ñandú`|**Técnicamente válida** en PHP 7+ UTF-8, pero **no recomendada**|Unicode, puede dar problemas|

## Constantes

### define
Son globales: accesibles desde cualquier función o ámbito sin necesidad de `global`.
```php
<?php
define('PI', 3.14159265);
define('RUTA_PROYECTO', __DIR__ . '/mi_app');
define('VERSION', '1.2.0');

echo PI;             // 3.14159265
echo RUTA_PROYECTO;  // /ruta/al/directorio/mi_app
echo VERSION;        // 1.2.0
```
### const 
Para constantes simples y estáticas, especialmente dentro de clases o namespaces, usa `const`.
```php
<?php
const MAX_USUARIOS = 100;
const MIN_IVA      = 0.19;

class Config {
    const ENTORNO = 'producción';
}

echo MAX_USUARIOS;       // 100
echo Config::ENTORNO;    // producción

```

[[Backend/Php/Language/Tipos de datos|Tipos de datos]]