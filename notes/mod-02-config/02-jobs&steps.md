Dentro de jobs puede haber varios job.
Dentro de cada job puede haber varios steps.
<!-- 
name: Nombre del Workflow

on: [push] 

jobs: 
  nombre-del-job:
    runs-on: ubuntu-latest
    
    steps:
    - name: Nombre del step
      run: acción a ejecutar
    - name: Nombre del step
      run: acción a ejecutar
  
  nombre-del-job:
    runs-on: ubuntu-latest
    
    steps:
    - name: Nombre del step
      run: acción a ejecutar
-->
> En cada job es necesario definir en qué SO se ejecuta (runs-on)

Los Jobs se ejecutan de forma independiente y paralela.

Si queremos que un job se ejecute cuando termine otro job, añadimos la directiva "needs:"
<!-- 
jobs: 
  primer-job:
    runs-on: ubuntu-latest
    
    steps:
    - name: Nombre del step
      run: acción a ejecutar
 
  segundo-job:
    runs-on: ubuntu-latest
    needs: primer-job
    
    steps:
    - name: Nombre del step
      run: acción a ejecutar
-->