# Fundamentos de C++ y Arquitecturas de sistema
Sentar unas bases sólidas en programación de bajo nivel, comprensión de la memoria y del sistema operativo, y familiarizarte con las herramientas imprescindibles para, más adelante, abordar ingeniería inversa y “game hacking”.
## C++
Es fundamental dominar C++ para desarrollar cheats.

| Semana | Contenido                                    | Objetivos concretos                                                        |
| ------ | -------------------------------------------- | -------------------------------------------------------------------------- |
| 1      | **C básico**: tipos, variables, operadores   | Escribir programas “Hello, World!”; manejar I/O con `printf`/`scanf`.      |
| 2      | **C avanzado**: punteros y arrays            | Entender la aritmética de punteros; recorrer y modificar un array.         |
| 3      | **Memoria en C**: stack vs heap, malloc/free | Reservar memoria dinámica; detectar fugas con herramientas como Valgrind.  |
| 4      | **Estructuras y bit-fields**                 | Definir `struct`; empacar datos usando `#pragma pack`; manipular bits.     |
| 5      | **C++ básico**: clases, herencia, RAII       | Crear clases sencillas; gestionar recursos con constructores/destructores. |
| 6      | **Plantillas y STL**                         | Usar `std::vector`, `std::map`; introducirte en plantillas de funciones.   |

## Python 
Aprender bibliotecas importantes como, `ctypes`/`cffi` para invocar funciones de librerías C desde Python y `psutil` para inspeccionar procesos y memoria.

**Objetivo**: escribir scripts que:
1. Arranquen un proceso externo.
2. Lean su espacio de memoria.
3. Modifiquen un valor simple (por ejemplo, un entero).

## Arquitecturas
**Registros generales** (EAX, EBX… RAX, RBX…) y su papel en llamadas a función.
**Modos de direccionamiento**: registro, inmediato, memoria.
**Pila (stack)**: `push`/`pop`, layout de un stack-frame, `calling convention` (stdcall, cdecl).

## Sistemas operativos
**Procesos y hilos**: creación, contexto, sincronización básica.
**Memoria virtual**: páginas, TLB, protecciones (R/W/X).
**Llamadas al sistema**: cómo invocar un syscall desde C/C++ (ej. `int 0x80` en Linux, `syscall` en Windows).


# Videos
<iframe src="https://www.youtube.com/embed/hj4rhfnikVs?list=PLt9cUwGw6CYHKBH5OoR8M2ELGlNlrgBKl" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>

<iframe src="https://www.youtube.com/embed/XgV76LapvGs?list=PL5Ps3A8vf-HyatvoYr-Vs8P5YX5ZG6TU7" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>