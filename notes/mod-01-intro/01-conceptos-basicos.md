CICD es una práctica donde va a haber cambios continuos
CI - integrar cambios y automatización

Herramientas: Jenkins y Github Actions

# Clase 3 - Conceptos
- [01] Workflows
- [02] Eventos/Triggers
- [03] Jobs
- [04] Actions
- [05] Runners

> 01 [Workflows] Archivo YAML que define acciones (instrucciones) que se ejecutan automáticamente en respuesta al resto de conceptos.
> 02 [Eventos]/Triggers: Disparado que inicia un workflow (ej: push, PR)
> 03 [Jobs]. Unidades de trabajo dentro de un workflow (ej: ejecutar pruebas unitarias, deployment automático, compilar código) en **servidor**.
    > 03.1 [Step]. Pasos dentro de un job. Secuencial por defecto.
        Ejemplo de steps dentro de un jobJobs
            1 configurar entorno
            2 instalar dependencias
            3 ejecutar pruebas
> 04. [Action]. Bloques de código reutilizable.
       (Marketplace en Github)
> 05. [Runner]. Entorno donde se ejecturan los [Jobs]. Máquinas virtuales que ejecutan los jobs de un wrorkflow que pueden ser configurados en distintos SO.