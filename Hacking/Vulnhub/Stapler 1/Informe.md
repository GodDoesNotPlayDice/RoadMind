# Escaneo en la red

```bash
sudo arp-scan 10.10.12.1/24
```

**IP** → `10.10.12.9`

# Nmap

```
PORT      STATE  SERVICE     REASON         VERSION
20/tcp    closed ftp-data    reset ttl 64
21/tcp    open   ftp         syn-ack ttl 64 vsftpd 2.0.8 or later
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_Can't get directory listing: PASV failed: 550 Permission denied.
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to 10.10.12.5
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 1
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
22/tcp    open   ssh         syn-ack ttl 64 OpenSSH 7.2p2 Ubuntu 4 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 8121cea11a05b1694f4ded8028e89905 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDc/xrBbi5hixT2B19dQilbbrCaRllRyNhtJcOzE8x0BM1ow9I80RcU7DtajyqiXXEwHRavQdO+/cHZMyOiMFZG59OCuIouLRNoVO58C91gzDgDZ1fKH6BDg+FaSz+iYZbHg2lzaMPbRje6oqNamPR4QGISNUpxZeAsQTLIiPcRlb5agwurovTd3p0SXe0GknFhZwHHvAZWa2J6lHE2b9K5IsSsDzX2WHQ4vPb+1DzDHV0RTRVUGviFvUX1X5tVFvVZy0TTFc0minD75CYClxLrgc+wFLPcAmE2C030ER/Z+9umbhuhCnLkLN87hlzDSRDPwUjWr+sNA3+7vc/xuZul
|   256 5ba5bb67911a51c2d321dac0caf0db9e (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBNQB5n5kAZPIyHb9lVx1aU0fyOXMPUblpmB8DRjnP8tVIafLIWh54wmTFVd3nCMr1n5IRWiFeX1weTBDSjjz0IY=
|   256 6d01b773acb0936ffab989e6ae3cabd3 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJ9wvrF4tkFMApswOmWKpTymFjkaiIoie4QD0RWOYnny
53/tcp    open   domain      syn-ack ttl 64 dnsmasq 2.75
| dns-nsid: 
|_  bind.version: dnsmasq-2.75
80/tcp    open   http        syn-ack ttl 64 PHP cli server 5.5 or later
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Site doesn't have a title (text/html; charset=UTF-8).
123/tcp   closed ntp         reset ttl 64
137/tcp   closed netbios-ns  reset ttl 64
138/tcp   closed netbios-dgm reset ttl 64
139/tcp   open   netbios-ssn syn-ack ttl 64 Samba smbd 4.3.9-Ubuntu (workgroup: WORKGROUP)
666/tcp   open   doom?       syn-ack ttl 64
| fingerprint-strings: 
|   NULL: 
|     message2.jpgUT 
|     QWux
|     "DL[E
|     #;3[
|     \xf6
|     u([r
|     qYQq
|     Y_?n2
|     3&M~{
|     9-a)T
|     L}AJ
|_    .npy.9
3306/tcp  open   mysql       syn-ack ttl 64 MySQL 5.7.12-0ubuntu1
| mysql-info: 
|   Protocol: 10
|   Version: 5.7.12-0ubuntu1
|   Thread ID: 7
|   Capabilities flags: 63487
|   Some Capabilities: SupportsCompression, IgnoreSpaceBeforeParenthesis, Speaks41ProtocolOld, ODBCClient, Support41Auth, LongColumnFlag, InteractiveClient, SupportsTransactions, FoundRows, SupportsLoadDataLocal, Speaks41ProtocolNew, LongPassword, IgnoreSigpipes, DontAllowDatabaseTableColumn, ConnectWithDatabase, SupportsMultipleResults, SupportsMultipleStatments, SupportsAuthPlugins
|   Status: Autocommit
|   Salt: g*#|^\x1CN^\x1BL~\x0DGkvUB#,.
|_  Auth Plugin Name: mysql_native_password
12380/tcp open   http        syn-ack ttl 64 Apache httpd 2.4.18 ((Ubuntu))
|_http-server-header: Apache/2.4.18 (Ubuntu)
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Tim, we need to-do better next year for Initech
```


**vsftpd 2.0.8**: https://github.com/nirae/boot2root/blob/master/bonus/writeup5.md
- No fue necesaria porque no habia nada en www/
**OpenSSH 7.2**: No se encontraron vulns
**dnsmasq 2.75**: Relacionadas a vulnerabilidades de DoS
**PHP cli server 5.5 or later**: https://www.tenable.com/plugins/nessus/76772
- Relacionadas a vulnerabilidades de DoS
**Samba smbd 3.X - 4.X**: 
- CVE-2017-0143 → SMB Remote Code Execution Vulnerability
- https://www.rapid7.com/db/modules/exploit/linux/samba/is_known_pipename/
- Usada esta vulnerabilidad para la explotacion del sistema
**MySQL 5.7.12** : Nada encontrado.
# Explotación
La explotación se realizo por vulnerabilidad de Samba. no fue necesario escalar privilegios.

![[Pasted image 20241108145110.png]]

![[Pasted image 20241108145206.png]]

### Persistencia

![[Pasted image 20241108145259.png]]

### Crackeo de contraseñas
Alguna de las contraseñas crackeadas con **john**  

![[Screenshot from 2024-11-08 16-13-05.png]]

**FTP**: no tiene la password configurada.
además, es posible acceder usando **anonymous**

![[Pasted image 20241108165822.png]]

Existe una nota que dice un nombre usuario nosotros ya vimos que existe una Elly
```
ftp> less note
Elly, make sure you update the payload information. Leave it in your FTP account once your are done, John.
```

**Usuario y password**
`Elly → ylle`

Nos pudimos conectar al **ftp como elly**
![[Pasted image 20241108170229.png]]
