# Escaneo de red

```
sudo arp-scan 10.10.12.1/24
```

```
Starting arp-scan 1.10.0 with 256 hosts (https://github.com/royhills/arp-scan)
10.10.12.1      52:54:00:12:35:00       (Unknown: locally administered)
10.10.12.2      52:54:00:12:35:00       (Unknown: locally administered)
10.10.12.3      08:00:27:9f:a0:9e       (Unknown)
10.10.12.10     08:00:27:f2:73:57       (Unknown)
```

**IP** → 10.10.12.10

# Escaneo de Puertos

```
PORT      STATE SERVICE  REASON         VERSION
22/tcp    open  ssh      syn-ack ttl 64 OpenSSH 5.3 (protocol 2.0)
80/tcp    open  http     syn-ack ttl 64 Apache httpd 2.2.15 ((CentOS))
| http-robots.txt: 1 disallowed entry 
|_/staff
|_http-server-header: Apache/2.2.15 (CentOS)
|_http-title: DC416
| http-methods: 
|   Supported Methods: GET HEAD POST OPTIONS TRACE
|_  Potentially risky methods: TRACE
50000/tcp open  ibm-db2? syn-ack ttl 64
```

# Web fuzzing

Uso de `ffuf` para hacer fuzzing en la web.

```bash
ffuf -w /usr/share/wordlists/dirb/common.txt -u http://10.10.12.10/FUZZ
```

Wordlist utilizada.
```
 :: URL              : http://10.10.12.10/FUZZ
 :: Wordlist         : FUZZ: /usr/share/wordlists/dirb/common.txt
```

Se obtuvo un 
```
.htpasswd [Status: 403, Size: 288, Words: 21, Lines: 11, Duration: 32ms]
.htaccess [Status: 403, Size: 288, Words: 21, Lines: 11, Duration: 38ms]
.hta [Status: 403, Size: 283, Words: 21, Lines: 11, Duration: 42ms]
admin [Status: 301, Size: 310, Words: 20, Lines: 10, Duration: 8ms]
cgi-bin/ [Status: 403, Size: 287, Words: 21, Lines: 11, Duration: 7ms]
index.html [Status: 200, Size: 1269, Words: 127, Lines: 34, Duration: 7ms]
robots.txt [Status: 200, Size: 31, Words: 3, Lines: 4, Duration: 9ms]
staff [Status: 301, Size: 310, Words: 20, Lines: 10, Duration: 8ms]
```

Si vamos a `http://10.10.12.10/admin` nos redirigirá a un enlace de descarga.

![[Pasted image 20241109185514.png]]

Se descarga un archivo python ya compilado `enc.pyc`   
![[Pasted image 20241109185559.png]]

## Desencriptación 
Primero vemos en que version de python fue compilado

![[Pasted image 20241109190154.png]]

Luego para desencriptar el archivo usamos [uncompyle2](https://github.com/wibiti/uncompyle2)

![[Pasted image 20241109190240.png]]

Vemos que nos entrega este contenido.

```
DESC = 'C4N YOU 1D3N71FY 7H3 FL46?'
str1 = 'FLAG4{'
str2 = '______'
str3 = '0'
str4 = '_____________________'
str5 = '__________________'
str6 = '____'
str7 = '1'
str8 = '_______'
str9 = '1'
str10 = '____________________'
str11 = '__________________________'
str12 = '}'
```


si nos guiamos en base a esto. [th3jackers](https://github.com/VulnHub/ctf-writeups/blob/05ceec63c98bb42348462d3ba384d521db3654be/2015/th3jackers/misc100.md)

```
____________________t
________h
_________i
___________________s

_________i
__________________________z

__________j
_____________________u
___________________s
7

_a

____________l
_________i
7
7
____________l
_____e

__________j
0
___________k
3

;
)

______f
____________l
_a
_______g
{
_______g
1
______________________v
3
-
_____________m
3
-
____________________t
________h
4
-
______f
____________l
_a
_______g
}
```

La flag es.
```
`FLAG4{f0urd1g1tz}`
```


