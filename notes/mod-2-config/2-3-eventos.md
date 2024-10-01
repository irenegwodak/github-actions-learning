Es importante utilizar los nombres correctos de los triggers.

Se pueden añadir varios triggers a un workflow
<!-- 
on: [push, pull_request]
 -->

Se pueden acotar las ramas en las que debe suceder el evento

<!-- 
 on: 
    push:
        branches:
            - main
    pull_request:
        branches:
            - main

 -->

Github docs - https://docs.github.com/es/actions/writing-workflows/choosing-when-your-workflow-runs/events-that-trigger-workflows