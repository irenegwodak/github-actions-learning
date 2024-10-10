Workflow dispatch: Ejecución del un workflow de forma manual configurando el evento en el workflow.yml, de esta manera aparece un botón en el navegador que permite ejecurat el WF manualmente.

<!-- 
on: workflow_dispatch
 -->

Se puede personalizar

<!-- 
on: workflow_dispatch
    inputs:
        test:
            description: 'test'
            required: true
            default: 'test'
 -->
