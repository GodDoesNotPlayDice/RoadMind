La vista se encuentra en **`views`** y esta es la responsable de proveer **html, pdf, csv, etc.** al cliente.

### Ejemplo con productos

**`views/productos/index.html.erb`** es el cual permite que usemos código ruby, para lograr incrustar código ruby debemos hacer el siguiente símbolo

```ruby
<%= codigo ruby =%>
```



## Layout
El layout es donde se aplicaran todos "globales" como un header, footer, o otro componente.

carpeta donde van esos "componentes" es llamada shared y se les dice parcials.
**shared** es creado en la carpeta **views**
**`shared/_header.html.erb`** es declarado con un _ el parcial antes de cada nombre.

después en el layout **`application.html`**, aplicamos el componente de esta forma.

```ruby
<%= render 'shared/header' %>
```

