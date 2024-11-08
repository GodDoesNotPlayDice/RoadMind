```bash
#!/bin/bash

# Verificar si se ejecuta como root
if [ "$(id -u)" -ne 0 ]; then
    echo "Este script debe ejecutarse como root."
    exit 1
fi

# Pedir el nombre del usuario
read -p "Introduce el nombre del nuevo usuario: " usuario

# Verificar si el usuario ya existe
if id "$usuario" &>/dev/null; then
    echo "El usuario '$usuario' ya existe."
    exit 1
fi

# Crear el usuario con su directorio home
adduser "$usuario"

# Configurar la contraseña para el nuevo usuario
echo "Configurando la contraseña para el usuario '$usuario'..."
passwd "$usuario"

# Agregar el usuario al grupo sudo para que tenga permisos de superusuario
usermod -aG sudo "$usuario"

# Añadir el usuario al archivo sudoers con permisos completos
echo "$usuario ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

# Mostrar los grupos del nuevo usuario para verificar
echo "El usuario '$usuario' se ha creado y añadido al grupo sudo con permisos root."
groups "$usuario"

# Prueba de los permisos sudo
echo "Para probar, inicia sesión con: su - $usuario"
echo "Luego ejecuta: sudo whoami (debería mostrar 'root')"

exit 0
```