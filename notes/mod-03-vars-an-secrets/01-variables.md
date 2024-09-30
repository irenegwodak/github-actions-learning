Variables de entorno.

Se pueden usar a nivel Job donde todos los Steps tengan acceso o a nivel Step donde solo ese Step tenga acceso

<!-- env: -->

<!-- Example
name:
on:
jobs:
  job-name:
    runs-on: 
    env:
        MY_VAR: a nivel Job
    steps:
      - name: step-name
        env:
            MY_VAR: a nivel step
 -->

 Las variables se inyectan directamente en el servidor, podemos acceder a ellas solo con el nombre.