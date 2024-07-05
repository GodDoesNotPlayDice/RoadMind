Los modelos se van a encargar con todo lo de la base de datos como consultas, validaciones, relaciones con tablas, etc.

se crea usando el siguiente comando.

```zsh
rails generate model Producto title:string description:text price:integer
```

Esto crea una migración, una clase de tipo modelo, y los test.

```
      invoke  active_record
      create    db/migrate/20240704220623_create_productos.rb
      create    app/models/producto.rb
      invoke    test_unit
      create      test/models/producto_test.rb
      create      test/fixtures/productos.yml
```

luego hay que hacer una migración

```
rails db:migrate
```

