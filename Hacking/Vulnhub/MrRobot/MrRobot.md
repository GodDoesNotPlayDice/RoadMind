
# Mr. Robot Tematica
**Elliot Alderson**, un brillante programador con problemas de ansiedad social, trabaja como ingeniero de ciberseguridad de día y como justiciero de noche. Su vida da un giro cuando unos ciberterroristas lo reclutan.

# Reconocimiento de los equipos en red
```bash
ip a -> 10.0.2.15
sudo arp-scan 
```

La `10.0.2.4` → es la maquina MR-Robot
```bash
Interface: eth0, type: EN10MB, MAC: 08:00:27:d2:26:79, IPv4: 10.0.2.15
WARNING: host part of 10.0.2.1/24 is non-zero
Starting arp-scan 1.10.0 with 256 hosts (https://github.com/royhills/arp-scan)
10.0.2.1        52:54:00:12:35:00       QEMU
10.0.2.2        52:54:00:12:35:00       QEMU
10.0.2.3        08:00:27:48:e2:4b       PCS Systemtechnik GmbH
10.0.2.4        08:00:27:f2:e6:75       PCS Systemtechnik GmbH

4 packets received by filter, 0 packets dropped by kernel
Ending arp-scan 1.10.0: 256 hosts scanned in 2.091 seconds (122.43 hosts/sec). 4 responded

```

# Escaneo de puertos de la dirección IP
```bash
sudo nmap 10.0.2.4 -sS -Pn -sV -sC -O -vvv -oN nmap.txt 
```

```bash
PORT    STATE  SERVICE  REASON         VERSION
22/tcp  closed ssh      reset ttl 64
80/tcp  open   http     syn-ack ttl 64 Apache httpd
|_http-server-header: Apache
|_http-favicon: Unknown favicon MD5: D41D8CD98F00B204E9800998ECF8427E
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Site doesn't have a title (text/html).
443/tcp open   ssl/http syn-ack ttl 64 Apache httpd
|_http-server-header: Apache
| ssl-cert: Subject: commonName=www.example.com
| Issuer: commonName=www.example.com
| Public Key type: rsa
| Public Key bits: 1024
| Signature Algorithm: sha1WithRSAEncryption
| Not valid before: 2015-09-16T10:45:03
| Not valid after:  2025-09-13T10:45:03
| MD5:   3c16:3b19:87c3:42ad:6634:c1c9:d0aa:fb97
| SHA-1: ef0c:5fa5:931a:09a5:687c:a2c2:80c4:c792:07ce:f71b

```

# Fuzzing web puerto 80
Se usa el comando `gobuster` para encontrar directorios y archivos ocultos en el servidor web.
```bash
gobuster dir -u http://http://10.0.2.4/ -w /usr/share/wordlists/dirb/common.txt
```

```bash
Gobuster v3.6
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.0.2.4/
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirb/common.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.6
[+] Timeout:                 10s
===============================================================
Starting gobuster in directory enumeration mode
===============================================================
/.hta                 (Status: 403) [Size: 213]
/.htaccess            (Status: 403) [Size: 218]
/.htpasswd            (Status: 403) [Size: 218]
/0                    (Status: 301) [Size: 0] [--> http://10.0.2.4/0/]
/admin                (Status: 301) [Size: 230] [--> http://10.0.2.4/admin/]
/atom                 (Status: 301) [Size: 0] [--> http://10.0.2.4/feed/atom/]
/audio                (Status: 301) [Size: 230] [--> http://10.0.2.4/audio/]
/blog                 (Status: 301) [Size: 229] [--> http://10.0.2.4/blog/]
/css                  (Status: 301) [Size: 228] [--> http://10.0.2.4/css/]
/dashboard            (Status: 302) [Size: 0] [--> http://10.0.2.4/wp-admin/]
/favicon.ico          (Status: 200) [Size: 0]
/feed                 (Status: 301) [Size: 0] [--> http://10.0.2.4/feed/]
/images               (Status: 301) [Size: 231] [--> http://10.0.2.4/images/]
/image                (Status: 301) [Size: 0] [--> http://10.0.2.4/image/]
/Image                (Status: 301) [Size: 0] [--> http://10.0.2.4/Image/]
/index.html           (Status: 200) [Size: 1188]
/index.php            (Status: 301) [Size: 0] [--> http://10.0.2.4/]
/intro                (Status: 200) [Size: 516314]
/js                   (Status: 301) [Size: 227] [--> http://10.0.2.4/js/]
/license              (Status: 200) [Size: 19930]
/login                (Status: 302) [Size: 0] [--> http://10.0.2.4/wp-login.php]
/page1                (Status: 301) [Size: 0] [--> http://10.0.2.4/]
/phpmyadmin           (Status: 403) [Size: 94]
/readme               (Status: 200) [Size: 7334]
/rdf                  (Status: 301) [Size: 0] [--> http://10.0.2.4/feed/rdf/]
/robots               (Status: 200) [Size: 41]
/robots.txt           (Status: 200) [Size: 41]
/rss                  (Status: 301) [Size: 0] [--> http://10.0.2.4/feed/]
/rss2                 (Status: 301) [Size: 0] [--> http://10.0.2.4/feed/]
/sitemap              (Status: 200) [Size: 0]
/sitemap.xml          (Status: 200) [Size: 0]
/video                (Status: 301) [Size: 230] [--> http://10.0.2.4/video/]
/wp-admin             (Status: 301) [Size: 233] [--> http://10.0.2.4/wp-admin/]
/wp-content           (Status: 301) [Size: 235] [--> http://10.0.2.4/wp-content/]
/wp-config            (Status: 200) [Size: 0]
/wp-includes          (Status: 301) [Size: 236] [--> http://10.0.2.4/wp-includes/]
/wp-cron              (Status: 200) [Size: 0]
/wp-links-opml        (Status: 200) [Size: 228]
/wp-load              (Status: 200) [Size: 0]
/wp-mail              (Status: 403) [Size: 3018]
/wp-login             (Status: 200) [Size: 2654]
/wp-settings          (Status: 500) [Size: 0]
/wp-signup            (Status: 302) [Size: 0] [--> http://10.0.2.4/wp-login.php?action=register]
/xmlrpc.php           (Status: 405) [Size: 42]
/xmlrpc               (Status: 405) [Size: 42]

===============================================================
Finished
===============================================================
```

Se encontró el file `robots.txt` cuyo contenido es.
```bash
User-agent: *
fsocity.dic
key-1-of-3.txt
```

Dos archivos cuales parecen ser
- `fsocity.dic`: diccionario de palabras.
- `key-1-of-3.txt`: clave 1 de 3.
	- `073403c8a58a1f80d943455fb30724b9`

