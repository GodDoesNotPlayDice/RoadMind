Bueno para comenzar **nmap** es una herramienta de escaneo de muchas cosas en una red, esas cosas pueden ser ips, vulnerabilidades en servicios, versiones de los servicios, datos acerca de las maquinas corriendo en la red, explotación de vulnerabilidades, deteccion de puertos abiertos o cerrados, etc.

## Para comenzar con Nmap
para comenzar no es muy difícil ya que hay ciertos comandos básicos que son super útiles al principio.
### Comandos básicos
- **-sS**: Se utiliza para realizar un escaneo de tipo SYN. Este tipo de escaneo es también conocido como "half-open" o "stealth scanning". En un escaneo SYN, Nmap envía un paquete TCP SYN al puerto de destino y espera la respuesta. Ademas al hacer esto se convierte mas "Sigiloso" al momento de hacer bulla en la red.
- **-Pn**: Se utiliza para indicar a la herramienta que realice el escaneo sin realizar la detección de host en línea. Por defecto, Nmap realiza un "ping scan" para determinar qué hosts están activos antes de intentar realizar el escaneo de puertos. Sin embargo, al usar la opción -Pn, se deshabilita este escaneo de ping y Nmap realiza el escaneo de puertos directamente sin verificar la disponibilidad del host. Ademas amenos yo la ocupo para que abarque todos los puertos disponibles.
- **-sC**: Se utiliza para activar scripts de escaneo en el escáner. Estos scripts son conocidos como "scripts de Nmap" o "Nmap scripts" y están destinados a realizar diversas tareas durante el escaneo, como detectar servicios específicos, identificar vulnerabilidades, recopilar información adicional, entre otros. Nmap ejecuta una serie de scripts predeterminados almacenados en el directorio **scripts**
- **-O**: Se utiliza para habilitar la detección del sistema operativo. Cuando se emplea esta opción, Nmap intenta adivinar el sistema operativo del objetivo basándose en las respuestas a los paquetes de sondeo enviados durante el escaneo.
- **-vvv**: Se utiliza para dar verbose a la operación.
- **-oN**: Se utiliza cuando queremos guardar lo generado en un .**txt**
- **-T(numero)**: Se utiliza para el uso de threads en nmap para disminuir la velocidad del escaneo o aumentarla. 

Al final todas y mas funciones que tienen nmap se pueden juntar en una sola linea tipo así.
```
sudo nmap 12.0.2.5 -sS -Pn -sV -sC -O -vvv -oN nmap.txt -T5
```