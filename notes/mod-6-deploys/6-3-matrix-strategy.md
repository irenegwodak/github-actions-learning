Una estrategia de matriz (o matrix) permite usar variables en una definición de trabajo para crear automáticamente varias ejecuciones de trabajos basadas en las combinaciones de las variables. Por ejemplo, puedes usar una estrategia de matriz para probar el código en varias versiones de un lenguaje o en varios sistemas operativos.

[https://docs.github.com/es/actions/writing-workflows/choosing-what-your-workflow-does/running-variations-of-jobs-in-a-workflow]

Se define en el job con el atributo 'strategy' y dentro todas las variables que queremos probar
<!-- 
jobs:
  example_matrix:
    strategy:
      matrix:
        version: [10, 12, 14]
        os: [ubuntu-latest, windows-latest]
-->
De forma predeterminada, GitHub maximizará el número de trabajos **ejecutados en paralelo** en función de la disponibilidad del ejecutor. El orden de las variables de la matriz determina el orden en el que se crean los trabajos.
En el ejemplo el orden será:
<!-- {version: 10, os: ubuntu-latest} -->
<!-- {version: 10, os: windows-latest} -->
<!-- {version: 12, os: ubuntu-latest} -->
<!-- {version: 12, os: windows-latest} -->
<!-- {version: 14, os: ubuntu-latest} -->
<!-- {version: 14, os: windows-latest} -->
