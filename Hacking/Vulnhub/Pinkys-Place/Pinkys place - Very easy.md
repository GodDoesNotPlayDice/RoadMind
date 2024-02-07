## Escaneo de la maquina
iniciamos un arp-scan a la red para identificar las maquinas en nuestra red, en este caso identificamos la maquina 10.0.2.10
![[Pasted image 20240114134802.png]]

luego realizamos un escaneo de servicios y de puertos a la maquina victima
```
sudo nmap 10.0.2.10 -sT -Pn -sV -sC -p- -O -vvv -oN nmap.txt -T5
```
se detectaron dos puertos con servicios httpd
```
PORT      STATE SERVICE    REASON  VERSION
8080/tcp  open  http       syn-ack nginx 1.10.3
|_http-title: 403 Forbidden
|_http-server-header: nginx/1.10.3
31337/tcp open  http-proxy syn-ack Squid http proxy 3.5.23
| http-open-proxy: Potentially OPEN proxy.
|_Methods supported: GET HEAD
|_http-server-header: squid/3.5.23
|_http-title: ERROR: The requested URL could not be retrieved
64666/tcp open  ssh        syn-ack OpenSSH 7.4p1 Debian 10+deb9u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 df:02:12:4f:4c:6d:50:27:6a:84:e9:0e:5b:65:bf:a0 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC/eH9dt7PVqsTKvqz7gb2G/6/0wUl+dy6gSLPDX0bqkIwc5k0IiCefKqk9MpBbTOU6aUWE3T/y9IYCAjhCaW7QTRrrVn+rUviz+8lABk50s29Z5hBEDwMOme+OZ5rTX3z+8096MgbOdgPMEsQbk3W/eWTDNHXUrU9iijz0zcZgC/HkuS+1E/C8IC3+CR30GQTA+cLXD8CKQ38WEukuNbvAlwEtjw3kMGvv74kzek8cVsWQGPB1y2qLv+miQHaWROiP//WzM5e69gXiFRNcC8spesAzRH0pkYXXTDTGpgG3sBu4G+lGBHncU+30a7i2AEtv+tAy0C2bvFYHqymdFJFv
|   256 0a:ad:aa:c7:16:f7:15:07:f0:a8:50:23:17:f3:1c:2e (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBDZDIHslZJXVJH6dCHGaJRVy8WULZGgoqkKe8gfp/jibTQiMe8lIE8zFX2S8aXxWo4kSBd6i94zKj4YR2TcFj2o=
|   256 4a:2d:e5:d8:ee:69:61:55:bb:db:af:29:4e:54:52:2f (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIEKiR+Y3n+2PC1Zjqgt/sE9mBtaxGwqMxPj19s2cpoYU


```
en los cuales el 8080 nos da forbidden y en el 31337 la url no puede ser retribuida, ademas descubrí que el puerto ssh esta en el 64666

```
8080/tcp  open  http       syn-ack nginx 1.10.3
31337/tcp open  http-proxy syn-ack Squid http proxy 3.5.23
64666/tcp open  ssh        syn-ack OpenSSH 7.4p1 Debian 10+deb9u2 (protocol 2.0)
```

en los casos que tenemos un ngnix o un apache pero de por medio hay un proxy es probable que solo se pueda acceder al servidor http por medio de ese proxy

en este caso es un un loopback por lo que la conexion es interna
