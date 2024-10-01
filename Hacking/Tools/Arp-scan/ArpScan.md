Básicamente `arp-scan` puede usarse para escanear o enumerar dispositivos que se encuentren en la misma red. 


## Uso basico
### Determinar la interfaz de red

Primero, identifica la interfaz de red que estás utilizando (por ejemplo, `eth0`, `wlan0`, etc.). Para ello, puedes usar el siguiente comando `ip a`
### Escanear la red local

Una vez que conozcas la interfaz, ejecuta el siguiente comando para escanear todos los dispositivos en la red local:

```bash
sudo arp-scan --interface=INTERFAZ -l
```

Sustituye `INTERFAZ` por la interfaz de red que determinaste en el paso anterior (por ejemplo, `eth0` o `wlan0`). El parámetro `-l` indica que se escaneará la red local (local network).

### Ejemplo:

Si tu interfaz de red es `wlan0`, el comando sería:

```bash
sudo arp-scan --interface=wlan0 -l
```

