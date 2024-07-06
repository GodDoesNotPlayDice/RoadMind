Los test se crean de la siguiente manera

**nombre del archivo**: `productos_controller_test.rb`

```ruby
require "test_helper"
class ProductosControllerTest < ActionDispatch::IntegrationTest
  test "Productos " do
    get '/productos'
    assert_response :success
  end
end
```

