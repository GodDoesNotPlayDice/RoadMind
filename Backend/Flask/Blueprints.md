Un _Blueprint_ es un objeto de Flask, introducido en la versión 0.7, que funciona como una versión “miniatura” de una aplicación, destinada a recopilar operaciones para registrar más tarde en la app principal. [Flask](https://flask.palletsprojects.com/en/stable/blueprints/) A diferencia de un objeto `Flask`, un blueprint no ejecuta nada por sí mismo; simplemente guarda rutas, vistas y configuraciones hasta que se registra.




# ¿Para que sirve?

## Modularidad  
Separas tu código en partes lógicas (auth, productos, pedidos…) sin tener todas las rutas en un único archivo gigante.

## Reutilización
Puedes empaquetar un conjunto de rutas en un Blueprint y usarlo en varios proyectos o en múltiples instancias de la misma app.

## Orden
Facilita la navegación y el mantenimiento: cada módulo vive en su carpeta con sus `routes.py`, `models.py`, `schemas.py`, etc.


# Ejemplo de blueprint

## Definir blueprint
```python
# app/modules/products/routes.py

from flask import Blueprint, jsonify

# Creamos el blueprint, le damos un nombre y la carpeta de templates estática (opcional)
products_bp = Blueprint(
    'products',           # nombre interno
    __name__,             # ayuda a Flask a encontrar recursos relativos
    template_folder='templates'  # si tuvieras templates aquí
)

@products_bp.route('/', methods=['GET'])
def list_products():
    # lógica para obtener productos
    return jsonify([{"id":1, "name":"Lana Merino"}])

```


### `Blueprint()`




## Registrar el Blueprint en la app principal
```python
# app/__init__.py

from flask import Flask
from .modules.products.routes import products_bp

def create_app():
    app = Flask(__name__)
    # ...
    app.register_blueprint(products_bp, url_prefix='/products')
    return app

```

Todas las rutas definidas en `products_bp` quedarán “bajo” `/products` (por ejemplo, `GET /products/`).

Mantienes tu app limpia y escalable: cada módulo (auth, orders, notifications…) define y registra su propio Blueprint.



