# FundamentosNube
Emilio Enrique Rivas Rubio
15197809

docker compose de la carpeta web:

version: '3.1'                            -Se especifíca la versión en la cual se trabajará
                                          
services:                                 -Se establecen los parametros del servicio al que se hara conexión

  measurementapp:                         -Apartado donde se establece la imagen y sus condiciones
  
    image: webdevops/php-apache:7.4       -Se pone la imagen y la versión con la que se conforma el contenedor
    
    restart: always                       -Establecimiento de las condiciones de reinicio
    
    environment:                          -Es donde se pone el ambiente de desarrollo del programa
    
      PHP_DISPLAY_ERRORS: 1               -Configuración en tiempo de ejecución manual de PHP
      
    ports:                                -El apartado en el cual se tiene que poner el puerto de conexión
    
      - 82:80                             -Es el puerto en el cual está la conexión al contenedor
      
    volumes:                              -Se escoje el volumen para el ahorro en el tiempo de escritura
    
      - ./appcode:/app                    -Es el comando que permite la conexión al IDE



docker compose de la carpeta web:

version: '3.1'                            -Se especifíca la versión en la cual se trabajará

services:                                 -Se establecen los parametros del servicio al que se hara conexión

  mydatabase:                             -Se establece que se hara conexión a una base de datos
  
    image: mariadb                        -Se pone la imagen que será el sistema de gestión de base de datos mariadb
    
    restart: always                       -Establecimiento de las condiciones de reinicio
    
    environment:                          -Es donde se pone el ambiente de desarrollo del programa
    
      MYSQL_ROOT_PASSWORD: mydbroot       -La contraseña del usuario de la base de datos.
      
      MYSQL_DATABASE: mydbclass           -Nombre de la base de datos a la que se hace conexión
      
      MYSQL_USER: mydbuser                -Nombre del usuario que hara la conexión de la base de datos
      
      MYSQL_PASSWORD: mydbpassword        -La contraseña de la base de datos a la que se hace conexión.
      
    ports:                                -El apartado en el cual se tiene que poner el puerto de conexión
    
      - 3889:3306                         -Es el puerto en el cual se encuentra la conexión a la base de datos.
      - 
    volumes:                              -Se escoje el volumen para el ahorro en el tiempo de escritura
    
      - ./files:/var/lib/mysql/           -Es el directorio de los archivos de la base de datos
      - 
      - ./logs:/var/log/mysql/            -Son los ficheros de registro de problemas en la conexión a la bd
      - 
      - ./conf:/etc/mysql/conf.d/         -Es el archivo que se genera cuando se inicia el contenedor






