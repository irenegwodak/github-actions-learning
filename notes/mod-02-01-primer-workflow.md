Primeros pasos:
 - Crear una carpeta en nuestro repo local: 
   - /.github
 - Crear una carpeta dentro:
   - /workflows 
 - Dentro generamos los archivos de configuración

1. **Definir nombre** representativo para workflow 
  
2. **Eventos**: Necesitamos indicarle con qué trigger se va a ejecutar el Job

3. **Jobs**: Ejecutar dentro de servidor.
   - Primero indicamos que inicia un job [jobs:]
     - Especificamos nombre del job
       - Indicamos el SO [runs-on:SO]
       - Indicamos que se inician los pasos [steps:]
        - Indicamos nombre del step [-name:]
        - Indicamos qué se ejectua [run:]

En cada job es necesario definir en qué SO se ejecuta (runs-on)

<!-- 
name: Nombre del Workflow

on: [push] 

jobs: 
  nombre-del-job:
    runs-on: ubuntu-latest
    
    steps:
    - name: Nombre del step
      run: acción a ejecutar
-->