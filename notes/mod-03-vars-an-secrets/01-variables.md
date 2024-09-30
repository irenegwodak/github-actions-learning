Variables de entorno
Las más usadas son a nivel Job, para que cada Step tenga acceso a dichas variables.

<!-- env: -->

<!-- Example
name:
on:
jobs:
  job-name:
    runs-on: 
    env:
        MY_VAR: valor
    steps:
 -->

 Las variables se inyectan directamente en el servidor, podemos acceder a ellas solo con el nombre.