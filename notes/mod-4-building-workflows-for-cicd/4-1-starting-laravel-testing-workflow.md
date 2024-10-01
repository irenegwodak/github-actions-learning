Setear servicios
Configurar tecnologías
Instalar dependencias


Para un proyecto Laravel:
- Configurar servicio MySQL versión 8.9 en el puerto 3306 con las siguientes variables de entorno:
  - MYSQL_ROOT_PASSWORD: root
  - MYSQL_DATABASE: laravel

- Configurar los steps:
  - Checkout (Se clona el código del repositorio.)
  - Configurar PHP v8.2 con las siguientes extensiones:
    - mbstring, bcmath, pdo, pdo_mysql
  - Instalar dependencias del proyecto de Laravel con Composer:
    - composer install -no-interaction
  
<!-- 
name: Laravel CI
on: [push]
      
jobs:
  laravel-test:
    runs-on: ubuntu-latest    

    services:
      mysql:
        image: mysql:8.0
        ports:
          - 3306:3306
        env:
          MYSQL_ROOT_PASSWORD: root
          MYSQL_DATABASE: laravel

    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Set Up PHP
        uses: shivammathur/setup-php@v2
        with:
          php-version: 8.2
          extensions: mbstring, bcmath, pdo, pdo_mysql
      
      - name: Install packages
        run: composer install -no-interaction
-->