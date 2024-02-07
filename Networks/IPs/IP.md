Una dirección IP (Internet Protcol) es la que es la encargada de identificar  un dispositivo dentro de una Red.
El encargado de entregar estas IP es el DHCP, cual asigna un rango de IPs
Se pueden tener todas las IPs publicas que uno quiera, pero hay que conversarlo con el proveedor de internet.
Como nos comunicamos?
- Nosotros hacemos una petición a un sitio o recurso.
- Esta petición se envía en un paquete con la IP privada al Router con la IP publica de destino
- El Router ve el destinatario y cambia la IP privada por la IP WAN y se lo manda al destinatario.
## Tipos de IP
Los tipos de ip son importantes ya que nos ayudara a identificar que tipo de IP estamos tratando, ya sea de IPv4 o IPv6
- **IPv4**: Principalmente son un numero binario de 32 bits, permitiendo un espacio de 2^32 de direcciones posibles. Las direcciones IP se pueden expresar como números de notación decimal, se dividen los 32 bits de la dirección en cuatro octetos, El valor decimal de cada octeto esta comprendido en el intervalo de 0 a 225.
- **IPv6**: Es la evolucion de la **Ipv4** cuya alcanzaba solo 2^32 bits, este tipo de Ip alcanza 2^128, y esta se expresa en una notacion hexadecimal, la unica caracteristica es que tendriamos una unica IP para cada dispositivo.
- **IP-Publica**: La IP publica es la cual sale del router al internet, y es una direccion unica en todo el mundo.
- ![[Pasted image 20231123165336.png]]![[Pasted image 20231124175749.png]]

## Quien provee el Internet?
Los proveedores de internet son los ISP, ellos son simplemente quienes te brindan el acceso a internet. ósea la compañía.
## Que es Internet?
La internet es una red cuya nos permite conectarnos entre nosotros, son interconexiones de redes.
## Registros de Internet (RIR)
Los registros de Internet lo que hacen es distribuir ciertos rangos de IP publica para la region donde pertenecen.
- **ARIN**: Norteamérica, Canadá, Estados Unidos
- **RIPE NCC**: Europa, Medio oriente y Asia
- **APNIC**: Asia y costa del pacifico
- **LACNIC**: Latinoamérica
- **AFRINIC**: Continente africano
![[Pasted image 20231125113139.png]]

## Rotación de IPs
Los proveedores de internet cuando tienen mas usuarios que IP, hacen una rotación de la IP publica ya que cuando hay dispositivos desconectados se reciclan IPs

## WAN
La Wide Área Network es la IP o las IPs locales de tu Área según tu RIR, y esta asignada al Router hace conexión con las LAN, para poder enviar paquetes a otras IPs.
## LAN
La Local Área Network es la red interna que interconecta todos los dispositivos de una red local, esta IP para nada es publica y todas las redes locales o en su mayoría son iguales.
Se caracterizan por ser de este estilo 192.168.1.XXX (0-255)
![[Pasted image 20231125121936.png]] ![[Pasted image 20231125121943.png]]


## NAT
La Network Address Translation su papel es el de traducir la IP privada a la IP publica esta accion la hace el Router vise y versa en internet.
![[Pasted image 20231125123210.png]]

## Gateway
El Gateway es simplemente la dirección del Router en la RED, comúnmente es la 192.168.1.1 

## Ejemplo de una RED con LAN, WAN y NAT y GATEWAY.
![[Pasted image 20231125121152.png]]