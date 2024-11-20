# Escaneo de red

```bash
sudo arp-scan 10.10.12.1/24
```

```
Starting arp-scan 1.10.0 with 256 hosts (https://github.com/royhills/arp-scan)
10.10.12.1      52:54:00:12:35:00       (Unknown: locally administered)
10.10.12.2      52:54:00:12:35:00       (Unknown: locally administered)
10.10.12.3      08:00:27:9f:a0:9e       (Unknown)
10.10.12.11     08:00:27:f2:73:57       (Unknown)
```


# Escaneo de servicios

```bash
sudo nmap -A -p- -sS -sV -sC -O -Pn 10.10.12.11 -oN nmap.txt -vvv
```

