Podemos agregar nuestros propios servidores.

En el repo/Settings/Actions/Runners/New self-hosted-runner (botón).
Se selecciona el SO (Linux, Windows, macOS) y la arquitextura (x64, ARM, ARM64) y se siguen los pasos.

> Como ejemplo: para una [máquina_virtual] (servidor) en Linux.

Seleccionando Linux x64: github.com/[username]/[repo-name]/settings/actions/runners/new?arch=x64&os=linux

Ejecutamos las instrucciones en la [máquina_virtual]:
- [Download]: Descargar y preparar entorno para un Github Actions runner: 
  - Crear y cambiar a un nuevo directorio
  - Descargar el runner
  - Validar el hash del runner descargado
  - Extraer el runner
<!-- 
# Create a folder
$ mkdir actions-runner && cd actions-runnerCopied!

# Download the latest runner package
$ curl -o actions-runner-linux-x64-2.319.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.319.1/actions-runner-linux-x64-2.319.1.tar.gz

# Optional: Validate the hash
$ echo "[hash]
actions-runner-linux-x64-2.319.1.tar.gz" | shasum -a 256 -c

# Extract the installer
$ tar xzf ./actions-runner-linux-x64-2.319.1.tar.gz
-->

- [Configure]: Configuración del runner en el servidor:
    - Ejecuta un script proporcionado por Github donde se configura el runner:
         - Agregar a un grupo ([Default] by default)
         - Nombre ([Test] by default)
         - Viene con etiquetas predefinidas, se pueden añadir más (opcional)
         - Definir work-folder ([_work] by default)
    - run.sh: ejecuta el runner y queda a la escucha de peticiones de ejecución de workflows de Github Actions
<!-- 
# Create the runner and start the configuration experience
$ ./config.sh --url https://github.com/[username]/[repo-name] --token [generated-token]

# Last step, run it!
$ ./run.sh
 -->
Una vez configurado y en marcha podemos verlo y conocer su estado en: github.com/[username]/[repo-name]/settings/actions/runners

El comando ./run.sh es manual, para ejecutarlo de forma automática en el YAML:
Se llama con las etiquetas del self-hosted-runner que queremos usar:
<!--
runs-on: [labels]
-->
Si solo indicamos **una etiqueta**, Github buscará **cualquier runner** que coincida con esa etiqueta.
Si se indican **varias etiquetas**, Github buscará los runners que **coincidan con todas las etiquetas**. **Deseable** para que el trabajo se ejecute en el entorno de nuestra elección.

