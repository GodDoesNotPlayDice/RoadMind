

## Enfoque de ruby on rails

Ruby on rails tiene un enfoque de **MVC**
**M** ⇒ Consultas, Validaciones, Relaciones entre tablas.
**V** ⇒ HTML, PDF, CSV, JSON
**C** ⇒ Logica
## Raíz del Proyecto

1. **app/**: Contiene el código principal de la aplicación, dividido en varios subdirectorios:
    - **controllers/**: Controladores que manejan las solicitudes y responden con vistas o redirecciones.
    - **models/**: Modelos que interactúan con la base de datos.
    - **views/**: Vistas que renderizan las respuestas HTML.
    - **helpers/**: Métodos auxiliares para las vistas.
    - **assets/**: Archivos estáticos como imágenes, hojas de estilo (CSS), y archivos JavaScript.
    - **mailers/**: Lógica para el envío de correos electrónicos.
    - **jobs/**: Trabajos en segundo plano.
    - **channels/**: Canales de ActionCable para WebSockets.
2. **bin/**: Contiene binarios ejecutables como `rails`, `rake`, etc.
3. **config/**: Archivos de configuración para la aplicación, la base de datos, el entorno, etc.
    - **environments/**: Configuraciones específicas del entorno (desarrollo, producción, pruebas).
    - **initializers/**: Archivos que inicializan las configuraciones necesarias al inicio de la aplicación.
    - **locales/**: Archivos de traducción.
    - **routes.rb**: Define las rutas de la aplicación.
4. **db/**: Contiene los archivos relacionados con la base de datos:
    - **migrate/**: Migraciones para crear y modificar tablas.
    - **seeds.rb**: Semillas de datos para la base de datos.
5. **lib/**: Archivos de biblioteca extendida y tareas personalizadas de Rake.
    - **tasks/**: Tareas personalizadas de Rake.
6. **log/**: Archivos de registro (logs) de la aplicación.
7. **public/**: Archivos estáticos públicos y la página de inicio predeterminada.
8. **storage/**: Archivos cargados para Active Storage.
9. **test/** o **spec/**: Pruebas unitarias, de integración y de sistema.
10. **tmp/**: Archivos temporales.
11. **vendor/**: Gemas y dependencias de terceros.

### Archivos en la Raíz

1. **config.ru**: Configuración de Rack para servidores web.
2. **Dockerfile**: Archivo de configuración para Docker
3. **.dockerignore**: Especifica archivos y directorios que Docker debe ignorar.
4. **Gemfile**: Lista de gemas necesarias para la aplicación.
5. **Gemfile.lock**: Registra las versiones exactas de las gemas instaladas.
6. **.git/**: Directorio de control de versiones de Git.
7. **.gitattributes**: Configuraciones de atributos para Git.
8. **.gitignore**: Archivos y directorios que Git debe ignorar.
9. **Rakefile**: Define las tareas disponibles para Rake.
10. **README.md**: Archivo de documentación del proyecto.
11. **.ruby-version**: Especifica la versión de Ruby para el proyecto.


## Commands
`rails new <name_of_project>` : crear proyecto, defecto trae sqlite
`rails new <name_of_project> -d postgresql`  : crear proyecto con la base de datos postgress


