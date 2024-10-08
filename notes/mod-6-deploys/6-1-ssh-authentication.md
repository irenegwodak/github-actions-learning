Para conectarnos desde github actions al servidor remoto es necesario  autenticarnos en el servidor utilizando una clave SSH. Para ello es necesario configurar la conexión ssh.
[https://codigofacilito.com/articulos/autenticacion_servidores_remotos]

Primero es necesario crear las claves pública y privada del servidor y guardar la pública en Secrets de Github Actions para poder llamarla en el flujo.

En el workflow se puede configurar de la siguiente forma:
<!-- 
  - name:  Github ssh
    run: |
        mkdir -p ~/.ssh
        echo "${{ secrets.SSH_KEY }}" > ~/.ssh/id_rsa
        chmod 600 ~/.ssh/id_rsa
        ssh-keyscan -H 127.0.0.1 >> ~/.ssh/known_hosts
-->

## Pasos:
- Crear un directorio si no existe (mkdir -p) en el home (~/) llamado (.ssh). Directorio donde SSH guarda las claves y la configuración del cliente.
<!-- mkdir -p ~/.ssh -->

- Tomar el valor del secreto SSH_KEY y escribirlo dentro de la carpeta [.ssh] en un archivo [id_rsa], que es el archivo predeterminado para almacenar la clave privada SSH.
<!-- echo "${{ secrets.SSH_KEY }}" > ~/.ssh/id_rsa -->

- Cambiar los permisos del archivo para que solo admin pueda leer y escribir. SSH requiere que la clave privada tenga estos permisos para funcionar correctamente.
<!-- chmod 600 ~/.ssh/id_rsa -->

- Escanear la clave pública del servidor SSH que escucha en 127.0.0.1 (la dirección de loopback o localhost) y la añade al archivo [~/.ssh/known_hosts]. Esto se hace para evitar advertencias al intentar conectar por SSH, ya que SSH normalmente genera advertencias si no reconoce la clave pública de un servidor. El uso del flag -H "hashea" la dirección IP en el archivo known_hosts para mejorar la privacidad.
<!-- ssh-keyscan -H 127.0.1.1 >> ~/.ssh/known_hosts -->
También es posible guardar la dirección IP como secreto
<!-- ssh-keyscan -H ${{ secrets.HOST }} >> ~/.ssh/known_hosts -->

Para comprobar que se ha conectado correctamente
<!-- 
- name: check server connection
  run: ssh user@ip "ls -al"
-->