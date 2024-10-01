El fuzzing en simples palabras es el escaneo sobre sub directorios dentro de una web, esto sirve para ver si hay un filtrado de alguna URL que no debería de ser accesible por información delicada de usuarios o del sistema.

## Web Fuzzing

### wfuzz
Un popular framework de fuzzing para aplicaciones web. Permite probar parámetros GET/POST, cabeceras, cookies, entre otros.
```python
pip install wfuzz
```

### ffuf:
Rápido fuzzer escrito en Go. Excelente para fuzzing de directorios, archivos y parámetros web.
```bash
sudo apt install ffuf
```

### Dirb:
Herramienta de fuzzing para descubrir directorios y archivos ocultos en servidores web.
```bash
sudo apt install dirb
```

## Fuzzing de binarios

### AFL (American Fuzzy Lop)
Fuzzer de código binario que realiza fuzzing de forma muy eficiente utilizando mutaciones de entrada y monitoreo de cobertura.
```bash
sudo apt install afl
```

### libFuzzer
Un fuzzer de entrada para código de usuarios en C/C++, que usa sanitizers para ayudar en la detección de errores.
```bash
clang -fsanitize=fuzzer program.c
```

## Fuzzing de APIs

### restler-fuzzer
Fuzzer especializado para APIs REST. Automatiza el proceso de fuzzing en endpoints de API.
```bash
git clone https://github.com/microsoft/restler-fuzzer
```

### fuzzapi
Herramienta de fuzzing de APIs RESTful con soporte para pruebas de múltiples configuraciones y casos.

```python
pip install fuzzapi
```

## Network Fuzzing
### boofuzz
Herramienta de fuzzing de protocolos de red. Puede fuzzear sockets, archivos y otras interfaces de comunicación.
```python
pip install boofuzz
```

## Fuzzing de archivos y formatos

### zzuf
Fuzzer simple pero efectivo que muta entradas de archivos para encontrar fallos en programas que procesan datos.
```bash
sudo apt install zzuf
```