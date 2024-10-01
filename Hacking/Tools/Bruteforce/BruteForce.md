## Hydra
**Descripción**: Una de las herramientas más conocidas para realizar ataques de fuerza bruta 
contra varios protocolos, incluidos HTTP, FTP, SSH, Telnet, MySQL, VNC, SMB, entre otros.

```
hydra -l usuario -P diccionario.txt <IP> ftp
```

**Protocolos soportados**: HTTP, FTP, SSH, Telnet, POP3, IMAP, SMB, RDP, VNC, y muchos más.

## Medusa
**Descripción**: Similar a Hydra, pero con más flexibilidad en cuanto a la configuración de ataques paralelos. Está diseñada para ataques rápidos contra múltiples servicios y es muy eficiente.

```bash
medusa -h <IP> -u usuario -P diccionario.txt -M ssh
```

**Protocolos soportados**: HTTP, FTP, SSH, Telnet, SMB, VNC, MySQL, PostgreSQL, y más.

## John the Ripper
**Descripción**: Popular herramienta de cracking de contraseñas. Originalmente fue diseñada para crackear contraseñas hash, pero tiene módulos para fuerza bruta en contraseñas cifradas de varios tipos.

```bash
john --wordlist=diccionario.txt hashfile
```

**Protocolos soportados**: Cracking de hashes (MD5, SHA, etc.), contraseñas de archivos ZIP, RAR, PDF, etc.

## Patator
**Descripción**: Framework modular para ataques de fuerza bruta. Es extremadamente flexible y puede configurarse para varios protocolos y servicios.

```bash
patator ssh_login host=<IP> user=usuario password=FILE0 0=diccionario.txt
```

**Protocolos soportados**: SSH, FTP, HTTP, VNC, Telnet, y otros servicios.


## Ncrack
**Descripción**: Herramienta de fuerza bruta de alta velocidad desarrollada por los creadores de Nmap. Es ideal para probar contraseñas en servicios de red.

```bash
ncrack -p 22 -U usuarios.txt -P diccionario.txt <IP>
```

**Protocolos soportados**: SSH, RDP, FTP, HTTP, POP3, SMB, VNC, y más.


## Burp Suite (Intruder)
**Descripción**: Burp Suite es una plataforma para pruebas de seguridad web, y su componente **Intruder** puede usarse para realizar ataques de fuerza bruta sobre formularios web, cookies y parámetros HTTP.

**Usos**: Fuerza bruta de formularios web, credenciales HTTP.


## Gobuster
**Descripción**: Utilizado para fuerza bruta en directorios web y subdominios. Aunque no es específicamente para credenciales, es útil para descubrir rutas ocultas en un servidor web.

```bash
gobuster dir -u http://<IP> -w diccionario.txt
```

**Protocolos soportados**: HTTP, DNS.


## SQLMap
**Descripción**: Aunque no es una herramienta de fuerza bruta en el sentido clásico, **SQLMap** puede usarse para automatizar ataques de inyección SQL, lo que puede incluir extracción de credenciales a través de la explotación de bases de datos.

```bash
sqlmap -u "http://<IP>/vulnerable.php?id=1" --dump
```


## WFuzz
**Descripción**: Una herramienta de fuzzing y fuerza bruta web que permite atacar parámetros GET/POST, cabeceras HTTP, formularios, y más. Es muy útil para buscar directorios ocultos y vulnerabilidades web.

```bash
wfuzz -c -z file,diccionario.txt --hc 404 http://<IP>/FUZZ
```

## CeWL
**Descripción**: CeWL genera diccionarios personalizados basado en palabras extraídas de un sitio web. Estos diccionarios pueden luego usarse en ataques de fuerza bruta con herramientas como Hydra o John the Ripper.

```bash
cewl http://<IP> -w diccionario.txt
```


## Hashcat
**Descripción**: Herramienta de cracking de contraseñas mediante fuerza bruta en hashes. Soporta varias técnicas como ataques combinados, ataques de diccionario y ataques de máscaras.

```bash
hashcat -m 0 -a 0 hash.txt diccionario.txt
```


## Aircrack-ng
**Descripción**: Suite de herramientas para auditar redes Wi-Fi, que incluye fuerza bruta sobre contraseñas de redes Wi-Fi.

```bash
aircrack-ng -w diccionario.txt captura.cap
```

