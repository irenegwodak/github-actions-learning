Aprovechando los contextos vamos a controlar un step con condicionales.

Se pueden poner ID a los steps

<!-- 
- name: Run Tests
  id: tests
  run: vendor/bin/phpunit 
-->

Para luego usarlos en el condicional
Si [Run Tests] se ejecuta correctamente, [Deploy] se ejecutará.
<!-- 
    - name: deploy
      if: steps.tests.conclusion == 'success'
      run: echo "Deploying..."
-->