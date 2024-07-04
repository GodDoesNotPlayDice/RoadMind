## Sqlite3

### Detalles de `SQLite3::Database.new`

**`SQLite3::Database.new`**: Este método de la clase `SQLite3::Database` se utiliza para crear una nueva conexión a una base de datos SQLite. Si la base de datos especificada por el nombre del archivo no existe, SQLite la creará automáticamente.


## PostgreSQL

### Dependencias de instalación

1. **Instalar PostgreSQL y herramientas de desarrollo**
```zsh
sudo pacman -S postgresql-libs postgresql
```

2. **Inicializar el Directorio de Datos de PostgreSQL**:
```zsh
sudo -iu postgres initdb --locale=C.UTF-8 --encoding=UTF8 -D '/var/lib/postgres/data'
```

3. **Verificar y ajustar los permisos del directorio de datos**:
```zsh
sudo chown -R postgres:postgres /var/lib/postgres/data
```

4. **Iniciar el servicio de PostgreSQL**:
```zsh
sudo systemctl start postgresql
sudo systemctl enable postgresql
```

### Creación del Rol en PostgreSQL

1. **Acceder a PostgreSQL como el usuario PostgreSQL**:
```zsh
sudo -i -u postgres
```
2. **Abrir el shell de PostgreSQL**:
```zsh
psql
```
3. **Crear el rol**:
```
CREATE ROLE raz WITH LOGIN PASSWORD 'tu_contraseña';
ALTER ROLE nombre_del_rol CREATEDB;
```
4. **Salir de la shell sql y usuario postgress**
```sql
\q ; exit
```

### Actualizar Rails

1. **Actualizar el archivo `config/database.yml`**
Ejemplo donde se agrega el usuario.
```yaml
# PostgreSQL. Versions 9.3 and up are supported.
#
# Install the pg driver:
#   gem install pg
# On macOS with Homebrew:
#   gem install pg -- --with-pg-config=/usr/local/bin/pg_config
# On Windows:
#   gem install pg
#       Choose the win32 build.
#       Install PostgreSQL and put its /bin directory on your path.
#
# Configure Using Gemfile
# gem "pg"
#
default: &default
  adapter: postgresql
  encoding: unicode
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>

development:
  <<: *default
  database: mercado_auto_development
  username: raz
  password: tu_contraseña
  host: localhost

test:
  <<: *default
  database: mercado_auto_test
  username: raz
  password: tu_contraseña
  host: localhost

production:
  <<: *default
  database: mercado_auto_production
  username: mercado_auto
  password: <%= ENV["MERCADO_AUTO_DATABASE_PASSWORD"] %>
  host: localhost
```

2. **Instalar las dependencias**:
```zsh
bundle install
```
3. **Crea y Migra la base de datos**
```zsh
rails db:create
rails db:migrate
```
