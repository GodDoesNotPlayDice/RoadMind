### Donde es el archivo barril de las rutas

El archivo se encuentra en **`config`** y en **`routes.rb`**, donde podemos alojar rutas tal que así
```ruby
get "products" => "products#index"
```
## Vista por objeto
Métodos de las rutas: [Guide](https://guides.rubyonrails.org/routing.html)

Para lograr esto debemos usar **`productos/:id`** y utilizar **`productos#show`**
**show**: en este caso sirve para mostrar un único objeto en concreto.

Y para resolver la ruta se agrega **`as: producto`**, al final el resultado queda asi

```ruby
 get 'productos/:id' => 'productos#show', as: 'producto'
```
