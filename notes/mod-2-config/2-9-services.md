https://docs.github.com/es/actions/use-cases-and-examples/using-containerized-services

Los contenedores de servicios son contenedores de Docker que ofrecen una manera sencilla y portátil de alojar servicios. Si por ejemplo se tiene que ejecutar pruebas de integración que requieran acceso a una base de datos y a una memoria caché.

Se pueden configurar contenedores de servicios para cada trabajo en un Workflow. GitHub crea un contenedor de Docker nuevo para cada servicio configurado en el Workflow y destruye el contenedor de servicios cuando se termina el Workflow.

Para ello se usa [services:], se indica el servicio y se añaden sus parámetros.

En Docker.hub podemos encontrar servicios, el que usamos en el ejemplo:
https://hub.docker.com/_/mysql

Ejemplo:
<!-- 
services:
    mysql:
    image: mysql:5.7  <-- version de mysql
    env:
        MYSQL_ROOT_PASSWORD: password
    ports:
        - 3306:3306 <-- rango de puertos
-->