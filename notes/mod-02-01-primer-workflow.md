Primeros pasos:
 - Crear una carpeta en nuestro repo local: 
   - /.github
 - Crear una carpeta dentro:
   - /workflows 
 - Dentro generamos los archivos de configuración

(ejemplo: test_1.yml)
1. **Definir nombre** representativo para workflow 
   - (name: Nombre del workflow)
  
2. **Eventos**: Necesitamos indicarle con qué trigger se va a ejecutar el Job
  - (on: [push]) <- Con cualquier push del repo.

3. **Jobs**: Ejecutar dentro de servidor.
   - (jobs:) <- primero indicamos que inicia un job
   - (nombre-del-job) <- s
      - (runs-on: sistema operativo)
      - (steps:
        - name: nombre del step)
