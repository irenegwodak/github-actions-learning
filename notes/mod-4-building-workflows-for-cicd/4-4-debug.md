En Laravel hay un archivo que almacena un log con los errores detallados en storage/logs/laravel.log, en Github Actions esto no es así.

Artifacts:
Permite subir cualquier archivo y poder descargarlos después. De esta forma podemos crear un archivo de debug con detalles.

Sería necesario saber dónde se cargan los logs de la aplicación para poder debugear después.

<!-- 
      - name: Artifact
        uses: actions/upload-artifact@v3
        with:
          name: artifacts
          path: composer.json
-->


El arhivo que se ha subido se puede encontrar en el Action/Summary/Artifacts(abajo)

Si queremos que Artifacts se ejecute cuando determinados Steps hayan fallado podemos usar:

<!--  
steps.(id).outcome == success/fail
-->

o funciónes:

<!-- 
if: failure()
if: success()
if: away() 
-->
