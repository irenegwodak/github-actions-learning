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

Se prioriza la variable del step a la del job (global).

Las variables se inyectan directamente en el servidor, podemos acceder a ellas solo con el nombre.

------
[https://docs.github.com/es/actions/writing-workflows/choosing-what-your-workflow-does/accessing-contextual-information-about-workflow-runs#vars-context]
Se pueden crear variables de entorno alojadas en el repositorio desde la web de Github:
Settings/Security - Secrets and variables/Actions/Variables/New repository variables
Se utiliza la interpolación con el objeto [vars]
<!-- 
${{ vars.MY_REPOSITORY_VARIABLE }}"
-->
