**Crear local Actions.**

Crear: /.github/actions/una-carpeta-por-action/action.yml

Al importar se especifica la ruta y YAML buscará [action.yml].
No es posible crear un [nombre-personalizado.yml] dentro de un directorio porque da error:
    <!-- Error: Can't find 'action.yml', 'action.yaml' or 'Dockerfile' under '/home/runner/work/github-actions-learning/github-actions-learning/.github/actions/local/hola-mundo.yml'. Did you forget to run actions/checkout before running your local action? -->

**código yaml del local action**
En [runs] hace falta indicar [using: 'composite']
En [steps] hace falta indicar [shell: bash]

<!-- 
name: 'My action'
description: 'Test action'

runs:
  using: 'composite'

  steps:
    - name: 'Hola mundo'
      run: echo "Hola mundo"
      shell: bash
 -->

Para **importar** en el workflow indicar la ruta:
<!-- 
steps:
    name: ...
    uses: ./.github/actions/subcarpeta/
-->
