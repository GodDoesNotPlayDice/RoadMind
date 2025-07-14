# Arquitectura del Plugin
```md
excel-to-wp-plugin/
├── composer.json                  ← (opcional) para PSR-4 y autoload
├── excel-to-wordpress.php         ← bootstrap principal
├── includes/                      ← “core” y loader
│   ├── class-activator.php        ← activation/deactivation
│   ├── class-deactivator.php
│   ├── class-plugin.php           ← clase principal que arranca el plugin
│   └── class-loader.php           ← registra todos los hooks
├── src/                           ← código organizado en namespaces
│   ├── Admin/                     ← todo lo que es back-office
│   │   ├── Menu.php               ← tu AdminMenu
│   │   ├── templates/             ← Carpeta templates
│   │   │   ├── admin-menu.php     ← Template
│   │   ├── SettingsPage.php       ← página de ajustes (si la hay)
│   │   └── Assets.php             ← registro de CSS/JS de admin
│   └── Public/                    ← funciones y assets para front
│       ├── Shortcodes.php
│       └── Assets.php
├── public/                        ← recursos públicos (imágenes, JS, CSS)
│   ├── css/
│   └── js/
└── languages/                     ← archivos .pot/.mo
```

# Estructura de un componente
`Admin/Menu.php`
```php
<?php
namespace ExcelToWP\Admin;

class Menu {
    private $plugin_path;

    public function __construct( string $plugin_path ) {
        $this->plugin_path = untrailingslashit( $plugin_path );
    }

    public function register() {
        add_menu_page(
            'Excel to WP',
            'Excel to WP',
            'manage_options',
            'excel-to-wordpress',
            [ $this, 'render' ],
            'dashicons-upload',
            1
        );
    }

    public function render() {
        include $this->plugin_path . '/src/Admin/templates/menu-page.php';
    }
}
?>
```

### `untrailingslashit()` 
Es una función auxiliar de WordPress que, como su nombre indica, **elimina la barra final** (“slash”) de una cadena. Se suele usar al trabajar con rutas o URLs para asegurarte de que terminen sin `/`, y luego poder concatenar segmentos de forma predecible.



## Import del componente
`/excel-to-wordpress.php`
```php
require_once plugin_dir_path(__FILE__) . 'src/Admin/Menu.php';
add_action('admin_menu', function() {
    $plugin_path = plugin_dir_path(__FILE__);
    $menu = new Menu($plugin_path);
    $menu->register();
});
```


