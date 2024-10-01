Igual que las env var, se pueden crear Secrets en Github.

Este valor, una vez creado, ya no se puede ver en la web, solo editar o eliminar.

-----
[https://docs.github.com/es/actions/writing-workflows/choosing-what-your-workflow-does/accessing-contextual-information-about-workflow-runs#vars-context]

Settings/Security - Secrets and variables/Actions/Secrets/New repository secret
También se utiliza la interpolación con el objeto [secrets]

<!-- 
${{ secrets.MY_REPOSITORY_SECRET }}"
-->