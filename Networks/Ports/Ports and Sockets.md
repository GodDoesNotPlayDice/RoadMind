Un puerto es donde van a llegar o salir distintos paquetes de información, el paquete se transforma vise y versa con el puerto, y cuando unimos la IP con el puerto se denomina socket.

Quien inicia la acción siempre es el cliente, ya que el cliente es quien manda la petición y el servidor es quien la responde nunca es al revés.

No se puede tener mas de un socket repetido.

Ejemplo: Con navegadores y puertos efímeros.

![[Pasted image 20231126130242.png]]


## Rango de puertos
Los puertos conocidos son desde el 0 al 1023 y estos puertos solo los puede abrir un root, ya que son puertos críticos, estos puertos pueden ser MTP, FTP, TELNET, etc.

Luego tenemos los puertos registrados que van del 1024 hasta 49151 y lo define la IANA, y estos puertos si son asignados para juegos, aplicaciones, etc.

Y port ultimo tenemos los efímeros, estos van del 49152 - 65535 y son puertos que duran mientras exista la conexión y luego muere para ser reutilizado.![[Pasted image 20231126125818.png]]
 
## IANA
Internet Assigned Numbers Authority es la entidad que supervisa la asignación global de direcciones IP, sistemas autónomos, servidores raíz de nombres de dominio DNS y otros recursos relativos a los protocolos de Internet.
## NAS
Un NAS es un rack que tiene varios servidores con distintos tipos de puertos y conexiones
![[Pasted image 20231126132004.png]]
## Tipos de puertos
**Puertos bien conocidos**:
- **SSH (22)**: 
- **Email (133)**: 
- **FTP (21)**:
- **HTTP (80)**: