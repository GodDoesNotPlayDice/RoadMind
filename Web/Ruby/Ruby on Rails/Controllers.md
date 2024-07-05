Esta clase esta heredando del controlador padre
```ruby
Class ProductsController < AplplicationController
end
```

>  cual controlador padre hereda del controlador abuelo cual es el **`base`**

```ruby
class ApplicationController < ActionController::Base
end
```

## Variables
Las variables son asignadas de la siguiente manera utilizando los métodos de activerecord

**`@productos = Producto.all`** como ejemplo para tomar todos los productos.

## Vista por objeto
Para hacer la vista por objeto necesitamos agregar esta lógica al controlador, que lo que hace principalmente es englobar en una variable la búsqueda por el parámetro id.

```ruby
class ProductosController < ApplicationController
  def index
    @productos = Producto.all
  end

  def show
    @producto = Producto.find(params[:id])
  end
end
```

