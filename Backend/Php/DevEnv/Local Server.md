| Acrónimo  | Plataforma     | Qué incluye                                         | Pros / Contras                                                                                            |
| :-------- | :------------- | :-------------------------------------------------- | :-------------------------------------------------------------------------------------------------------- |
| **LAMP**  | Linux          | Linux, Apache, MariaDB/MySQL, PHP                   | Control total (instalación manual vía pacman), siempre actual; pero un poco más de configuración inicial. |
| **WAMP**  | Windows        | Apache, MySQL, PHP en Windows                       | Instalador gráfico, muy fácil para novatos; sólo para Windows.                                            |
| **MAMP**  | macOS (y Win)  | Apache, MySQL, PHP (+ Python opcional) en macOS/Win | Muy popular en Mac; GUI sencilla; permisos “propios” (no usa tu gestor de paquetes).                      |
| **XAMPP** | Cross-platform | Apache, MariaDB, PHP, Perl                          | Disponible para Linux/Win/Mac; incluye extras (OpenSSL, FTP, etc.); paquete autónomo (no usa pacman/apt). |

## Imagenes de docker
**Mysql**
```docker-compose.yml
version: '3.8'
services:
  db:
    image: mysql:8.0
    container_name: wpdb
    restart: unless-stopped
    volumes:
      - db_data:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: root_passwd
      MYSQL_DATABASE: wp_dev
      MYSQL_USER: wp_user
      MYSQL_PASSWORD: wp_pass
    ports:
      - "3306:3306"

volumes:
  db_data:
```

