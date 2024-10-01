Las Claves SSH no deben ser expuestas por lo que se pueden añadir como "secreto" a un repositorio.

Para poder utilizarlo es necesario configurarlo el acceso SSH (común en configuraciones CI/CD), creando el entorno necesario para que el sistema pueda hacer conexiones SSH de manera segura

- Crear un directorio si no existe (mkdir -p) en el home (~/) llamado (.ssh). Directorio donde SSH guarda las claves y la configuración del cliente.
<!-- mkdir -p ~/.ssh -->

- Tomar el valor del secreto SSH_KEY y escribirlo dentro de la carpeta [.ssh] en un archivo [id_rsa], que es el archivo predeterminado para almacenar la clave privada SSH.
<!-- echo "${{ secrets.SSH_KEY }}" > ~/.ssh/id_rsa -->

- Cambiar los permisos del archivo para que solo admin pueda leer y escribir. SSH requiere que la clave privada tenga estos permisos para funcionar correctamente.
<!-- chmod 600 ~/.ssh/id_rsa -->

- Escanear la clave pública del servidor SSH que escucha en 127.0.0.1 (la dirección de loopback o localhost) y la añade al archivo [~/.ssh/known_hosts]. Esto se hace para evitar advertencias al intentar conectar por SSH, ya que SSH normalmente genera advertencias si no reconoce la clave pública de un servidor. El uso del flag -H "hashea" la dirección IP en el archivo known_hosts para mejorar la privacidad.
<!-- ssh-keyscan -H 127.0.1.1 >> ~/.ssh/known_hosts -->

<!-- 
  - name:  Github ssh
    run: |
        mkdir -p ~/.ssh
        echo "${{ secrets.SSH_KEY }}" > ~/.ssh/id_rsa
        chmod 600 ~/.ssh/id_rsa
        ssh-keyscan -H 127.0.0.1 >> ~/.ssh/known_hosts
-->