Parámetros en los Composite (local actions)

Para crear parámetros en una Action se usa el **Contexto** [input:]
Se puede poner una descripción [description:]
Se puede indicar si es obligatorio [required:]
Se puede definir un valor por defecto [default:]

[contextos](https://docs.github.com/es/actions/writing-workflows/choosing-what-your-workflow-does/accessing-contextual-information-about-workflow-runs)

Para acceder a los parámetros de inputs en el flujo de trabajo se usa la interpolación:
<!-- 
"${{ inputs.message }}"
 -->



Nuestro ejemplo:
<!-- 

name: 'Hola mundo Action'
description: 'Test Hola mundo'

inputs:
    message:
        description: "the message to print"
        required: true
        default: "message test"

runs:
  using: 'composite'

  steps:
    - name: 'Echo message'
      run: echo "Hola ${{ inputs.message }}"
      shell: bash

 -->





## 
Checkout: Utiliza la acción oficial de GitHub para hacer un checkout del código del repositorio (bajar el código fuente a la máquina de CI/CD).

Si miramos la documentación del Action [Checkout](https://docs.github.com/es/actions/writing-workflows/choosing-what-your-workflow-does/accessing-contextual-information-about-workflow-runs#inputs-context)


<!-- 
- uses: actions/checkout@v4
  with:
    # Repository name with owner. For example, actions/checkout
    # Default: ${{ github.repository }}
    repository: ''

    # The branch, tag or SHA to checkout. When checking out the repository that
    # triggered a workflow, this defaults to the reference or SHA for that event.
    # Otherwise, uses the default branch.
    ref: ''
 -->

 El código del Action es:
 ```yaml
name: 'Checkout'
description: 'Checkout a Git repository at a particular version'
inputs:
  repository:
    description: 'Repository name with owner. For example, actions/checkout'
    default: ${{ github.repository }}
  ref:
    description: >
      The branch, tag or SHA to checkout. When checking out the repository that
      triggered a workflow, this defaults to the reference or SHA for that
      event.  Otherwise, uses the default branch.
    #   otros inputs
outputs:
  ref:
    description: 'The branch, tag or SHA that was checked out'
  commit:
    description: 'The commit SHA that was checked out'
runs:
  using: node20
  main: dist/index.js
  post: dist/index.js
```
