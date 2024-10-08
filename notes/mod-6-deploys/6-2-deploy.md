En este caso vamos a utilizar un Action del marketplace para poder ejecutar comandos en el servidor remoto.

(solo con linux)
[https://github.com/marketplace/actions/ssh-remote-commands]
<!-- 
- name: remote ssh with pass
  uses: appleboy/ssh-action@master
  if: success()
  with:
    host: ${{ secrets.HOST }}
    username: ${{ secrets.USERNAME }}
    key: ${{ secrets.SSH_KEY }}
    port: ${{ secrets.PORT }}
    script: |
      whoami
      cd /home/folder/actions
      git pull origin main
-->
if: success() <!-- Si lo demás funcionó correctamente -->
script:
- whoami <!-- para probar que se ha conectado -->
- cd /home/folder/actions <!-- ir a la raíz del proyecto -->
- git pull origin main <!-- pull dentro del servidor -->