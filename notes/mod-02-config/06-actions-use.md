Ejemplo de código para instalar Node

<!--
- name: Setup Node.js environment
uses: actions/setup-node@v4.0.4

- name: node version
run: node --version 

- name: install dependencies
  run: npm install
-->

Podemos usar el "with" después del "uses"
Permite enviar parámetros al action

<!-- 
      - name: Setup Node.js environment
        uses: actions/setup-node@v4.0.4
        with:
          node-version: 'latest'
 -->