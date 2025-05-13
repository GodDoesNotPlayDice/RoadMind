La arquitectura de microservicios es un estilo arquitectónico que organiza una aplicación como una colección de servicios **ligeramente acoplados** y **finamente granulados**, cada uno enfocado en una única capacidad de negocio. Estos servicios se desarrollan, despliegan y escalan de forma independiente, comunicándose entre sí mediante protocolos ligeros (por ejemplo **REST** o **mensajería**)

# Características

## Enfoque
La **arquitectura de microservicios es un enfoque moderno y flexible** para el diseño de aplicaciones. En lugar de construir una sola aplicación monolítica, la descomponemos en pequeños servicios independientes.

Cada servicio se centra en una tarea específica y se comunica con otros servicios a través de interfaces bien definidas.

## Idea
La idea es que **cada microservicio sea como una pieza de lego** que encaje perfectamente en el rompecabezas de la aplicación completa. Cada servicio puede ser desarrollado, probado, desplegado y escalado de forma independiente, lo que facilita la agilidad y la entrega continua de software.

## Tecnología
Un microservicio puede usar su propia tecnología y lenguaje de programación, lo que nos **brinda la libertad de elegir la mejor herramienta** para cada tarea.


# Ejemplo
- **El Gateway/API:** actúa como punto de entrada para las solicitudes de los clientes y enruta las peticiones a los microservicios correspondientes.
- **User Service:** el primer microservicio que se encargará de la gestión de usuarios.
- **Product Service:** será otro microservicio y se dedicará a atender todo lo relacionado con los productos.
- **Order Service:** gestionará las órdenes de compra, también como microservicio.
- **Payment Service:** como otro microservicio que procesa los pagos. Este microservicio es directamente invocado por el de pedidos, veremos más adelante que se puede hacer de varias maneras.
- **BBDD:** cada microservicio tiene su propia BBDD, también pueden compartirla y dividir schemas, tablas, colecciones, etc.
- **Cliente:** finalmente, el cliente o los clientes que interactúan con los microservicios a través del API Gateway.
![[Pasted image 20250505124615.png]]

# Orquestador
La **orquestación** en microservicios es el patrón en el que existe un **coordinador central** (el “orquestador”) que controla el flujo de trabajo entre los diferentes servicios.

El orquestador dicta “quién llama a quién” y en qué orden.

## Ejemplo
- Cliente envía solicitud de compra → llega al **Orquestador**.
- El orquestador llama a **Servicio de Inventario** (¿hay stock?)
- Si hay stock, llama a **Servicio de Pago** (procesar tarjeta)
- Si el pago es exitoso, llama a **Servicio de Envío** (coordinación logística)
- Finalmente, llama a **Servicio de Notificaciones** (envía email/SMS).


