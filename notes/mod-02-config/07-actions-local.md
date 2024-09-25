**Crear local Actions.**

Crear
    /.github/actions

Se pueden crear subcarpetas
    /.github/actions/local
  
Y dentro crear [action.yml] por convención. Al importar no hará falta indicar el nombre porque por defecto buscará este.

**código del YAML**

Se pueden poner **nombre** y **descripción**.
En [runs] hace falta indicar [using: 'composite']
Poner [steps]

<!-- 
name: 'My action'
description: 'Test action'

runs:
  using: 'composite'

  steps:
    - name: 'Hello world'
      run: echo "Hello world"
 -->

Dentro de los steps hace falta especificar el shell:
<!-- shell: bash -->


Para importar en el workflow:
<!-- 
steps:
    name: ...
    uses: ./.github/actions/local-actions/
-->
