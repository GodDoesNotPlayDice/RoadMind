Un _Blueprint_ es un objeto de Flask, introducido en la versión 0.7, que funciona como una versión “miniatura” de una aplicación, destinada a recopilar operaciones para registrar más tarde en la app principal. [Flask](https://flask.palletsprojects.com/en/stable/blueprints/) A diferencia de un objeto `Flask`, un blueprint no ejecuta nada por sí mismo; simplemente guarda rutas, vistas y configuraciones hasta que se registra.

# Por qué usar Blueprints
**Factorización del código**: Dividen una aplicación grande en módulos lógicos, facilitando el mantenimiento y la escalabilidad.

**Prefijos de URL**: Puedes registrar un mismo blueprint varias veces con distintos `url_prefix` para montar las mismas rutas en diferentes puntos de la app.

**Reutilización**: Encapsulan funcionalidades completas (rutas, vistas, plantillas, archivos estáticos), permitiendo compartir código entre proyectos sin copiar y pegar.

**Organización de recursos**: Permiten definir carpetas de plantillas y archivos estáticos específicos por módulo, manteniendo la estructura limpia.


# Anatomía de un Blueprint

```python
from flask import Blueprint, render_template, abort

# Definición de un blueprint para manejar frutas
fruits_bp = Blueprint(
    'fruits',                   # nombre interno del blueprint
    __name__,                   # ubicación del módulo para recursos
    url_prefix='/fruits',       # prefijo común para todas las rutas
    template_folder='templates/fruits'  # carpeta de plantillas del blueprint
)

@fruits_bp.route('/')
def list_fruits():
    # Lista de frutas (manzanas y peras)
    return render_template('list.html', fruits=['apple', 'pear'])
```

El primer argumento (‘fruits’) es el nombre interno, usado para generar endpoints (`fruits.list_fruits`).
`__name__` indica al blueprint dónde buscar carpetas de plantillas y archivos estáticos.
`template_folder` y `static_folder` permiten encapsular recursos específicos de este módulo.

## Registro de Blueprints
```python
from flask import Flask
from yourapp.fruits import fruits_bp

app = Flask(__name__)
app.register_blueprint(fruits_bp)  # Monta las rutas en '/fruits'
# O bien con otro prefijo:
app.register_blueprint(fruits_bp, url_prefix='/frutas')
```
Al registrar el blueprint, Flask añade todas sus rutas al mapa de URL de la app, respetando el prefijo si lo proporcionas.