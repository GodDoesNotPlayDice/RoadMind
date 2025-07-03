## ¿Qué son y por qué usarlos?
La arquitectura de microservicios ha revolucionado la forma en que se construyen y despliegan las aplicaciones, ofreciendo una alternativa a las arquitecturas monolíticas tradicionales. Comprender qué son los microservicios y por qué se han vuelto tan populares es fundamental para cualquier desarrollador o arquitecto que busque crear sistemas **escalables, resilientes y fáciles de mantener.**

[[Ventajas y Desventajas]]
# ¿Qué son los Micro servicios?
La arquitectura de microservicios es un enfoque de diseño arquitectónico y organizativo para el desarrollo de software donde una aplicación se estructura como una colección de pequeños **servicios autónomos,** modelados en **torno a un dominio de negocio**. En otras palabras, en lugar de construir una sola aplicación monolítica, se construye un conjunto de **pequeños servicios.**

1) **Es autónomo:** Puede ser desarrollado, desplegado, escalado y reiniciado independientemente de otros servicios.
2) **Está especializado:** Se enfoca en una tarea o un conjunto de tareas específicas dentro del dominio de negocio.
3) **Se comunica a través de la red:** Utiliza APIs ligeras, a menudo RESTful, o protocolos de mensajería para interactuar con otros microservicios.
4) **Tiene su propia base de datos:** Cada micro-servicio gestiona su propia base de datos, lo que permite elegir la tecnología de almacenamiento más adecuada para sus necesidades.
5) **Puede estar escrito en diferentes lenguajes y tecnologías:** Los equipos pueden elegir la tecnología más adecuada para cada micro-servicio

## Ejemplo Básico y Avanzado

### Básico
Imagina una aplicación de comercio electrónico. En una arquitectura monolítica, todo el código para la gestión de productos, el carrito de compras, el procesamiento de pagos y la gestión de usuarios estaría en una sola base de código.

En una arquitectura de microservicios, cada una de estas funcionalidades sería un micro-servicio independiente.
- **Servicio de Productos:** Gestiona la información de los productos, como el nombre, la descripción, el precio y el inventario.
- **Servicio de Carrito de Compras:** Gestiona el carrito de compras de cada usuario.
- **Servicio de Pagos:** Procesa los pagos.
- **Servicio de Usuarios:** Gestiona la información de los usuarios, como el nombre, la dirección y la información de pago.
### Avanzado
Consideremos una plataforma de streaming de video como Netflix.
- **Servicio de Recomendaciones:** Utiliza algoritmos de aprendizaje automático para recomendar contenido a los usuarios.
- **Servicio de Transmisión de Video:** Gestiona la transmisión de video a los dispositivos de los usuarios.
- **Servicio de Facturación:** Gestiona la facturación de los usuarios.
- **Servicio de Búsqueda:** Permite a los usuarios buscar contenido.

### Escenario Hipotético
Una empresa de logística quiere modernizar su sistema de gestión de envíos. En lugar de un monolito, decide adoptar microservicios.

- **Servicio de Seguimiento de Envíos:** Proporciona información en tiempo real sobre la ubicación de los envíos.
- **Servicio de Gestión de Rutas:** Optimiza las rutas de entrega.
- **Servicio de Notificaciones:** Envía notificaciones a los clientes sobre el estado de sus envíos.
- **Servicio de Facturación:** Genera facturas para los clientes.

# ¿Por qué Usar Micro-Servicios?
La arquitectura de microservicios ofrece una serie de ventajas sobre las arquitecturas monolíticas tradicionales
- **Escalabilidad:** Cada microservicio puede ser escalado independientemente de los demás, lo que permite optimizar el uso de los recursos. Si el servicio de "Recomendaciones" de Netflix experimenta un aumento en la demanda, se puede escalar solo ese servicio sin afectar a los demás.
- **Flexibilidad Tecnológica:** Los equipos pueden elegir la tecnología más adecuada para cada microservicio, lo que permite aprovechar las últimas innovaciones. Por ejemplo, el servicio de "Recomendaciones" podría usar Python y un framework de machine learning, mientras que el servicio de "Transmisión de Video" podría usar Java para un mejor rendimiento.
- **Despliegue Independiente:** Los microservicios pueden ser desplegados independientemente de los demás, lo que permite realizar actualizaciones y correcciones de errores de forma más rápida y segura. Si se encuentra un error en el servicio de "Carrito de Compras" de la tienda online, se puede corregir y desplegar ese servicio sin necesidad de desplegar toda la aplicación.
- **Resiliencia:** Si un microservicio falla, los demás siguen funcionando, lo que mejora la resiliencia del sistema. Si el servicio de "Pagos" falla, los usuarios aún pueden navegar por la tienda online y ver los productos.
- **Organización:** Los microservicios facilitan la organización de los equipos en torno a dominios de negocio específicos, lo que mejora la productividad y la agilidad. Un equipo puede ser responsable del servicio de "Productos", mientras que otro equipo es responsable del servicio de "Carrito de Compras".
- **Reutilización:** Los microservicios pueden ser reutilizados en diferentes aplicaciones, lo que reduce la duplicación de código. El servicio de "Usuarios" podría ser utilizado tanto por la tienda online como por la aplicación móvil.

## Ejemplos
### Escalibilidad
Una tienda online experimenta un aumento en el tráfico durante el Black Friday. Con una arquitectura monolítica, sería necesario escalar toda la aplicación, incluso las partes que no están experimentando un aumento en la demanda. Con una arquitectura de microservicios, solo es necesario escalar los servicios que están experimentando un aumento en la demanda, como el servicio de "Productos" y el servicio de "Carrito de Compras".

### Flexibilidad Tecnológica
Una empresa quiere implementar un nuevo servicio de análisis de datos. Con una arquitectura monolítica, sería necesario utilizar la misma tecnología que el resto de la aplicación. Con una arquitectura de microservicios, se puede utilizar la tecnología más adecuada para el servicio de análisis de datos, como Python y Spark.

### Despliegue Independiente
Un equipo encuentra un error en el servicio de "Gestión de Inventario". Con una arquitectura monolítica, sería necesario desplegar toda la aplicación para corregir el error. Con una arquitectura de microservicios, solo es necesario desplegar el servicio de "Gestión de Inventario".

### Resiliencia
El servicio de "Recomendaciones" de una plataforma de streaming de video falla. Con una arquitectura monolítica, toda la plataforma podría dejar de funcionar. Con una arquitectura de microservicios, los usuarios aún pueden ver videos, aunque no reciban recomendaciones.

### Organización
Una empresa tiene un equipo responsable del "Frontend" y otro del "Backend". Con una arquitectura de microservicios, se pueden crear equipos más pequeños y especializados, como un equipo responsable del servicio de "Productos" y otro del servicio de "Carrito de Compras".

### Reutilización
Una empresa tiene una tienda online y una aplicación móvil. Con una arquitectura de microservicios, el servicio de "Usuarios" puede ser utilizado tanto por la tienda online como por la aplicación móvil.

# Cuando usar Micro-Servicios
Si bien la arquitectura de microservicios ofrece muchas ventajas, no es la solución adecuada para todos los proyectos.
- **Complejidad:** La arquitectura de microservicios es más compleja que la arquitectura monolítica, ya que implica la gestión de múltiples servicios, la comunicación entre ellos y la gestión de datos distribuidos.
- **Tamaño del Equipo:** La arquitectura de microservicios requiere un equipo con experiencia en el desarrollo, despliegue y gestión de sistemas distribuidos.
- **Dominio de Negocio:** La arquitectura de microservicios es más adecuada para aplicaciones con un dominio de negocio complejo y bien definido.
- **Escalabilidad:** La arquitectura de microservicios es más adecuada para aplicaciones que requieren una alta escalabilidad.

La arquitectura monolítica puede ser una mejor opción para:
- **Aplicaciones pequeñas y sencillas:** Aplicaciones con un pequeño número de funcionalidades y un dominio de negocio sencillo.
- **Proyectos con plazos ajustados:** La arquitectura monolítica es más rápida de desarrollar que la arquitectura de microservicios.
- **Equipos pequeños:** La arquitectura monolítica requiere un equipo más pequeño que la arquitectura de microservicios.
- **Prueba de concepto (POC):** Para validar una idea rápidamente, un monolito puede ser más eficiente.