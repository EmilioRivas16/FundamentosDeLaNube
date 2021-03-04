### Part 1 - Emilio Enrique Rivas Rubio ###

Registration: 15197809

docker compose from the web folder:

version: '3.1'                          -Specify the version in which it will work

services:                               -The parameters of the service to which connection will be made are established

measurementapp:                         -Section where the image and its conditions are established

image: webdevops / php-apache: 7.4      -It puts the image and the version with which the container conforms

restart: always                         -Setting restart conditions

environment:                            -It is where the program development environment is placed

  PHP_DISPLAY_ERRORS: 1                 -Manual PHP runtime configuration
  
ports:                                  -The section in which you have to put the connection port

  - 82:80                               -It is the port in which the connection to the container is
  
volumes:                                -Choose the volume to save on writing time

  - ./appcode:/app                      -It is the command that allows the connection to the IDE


docker compose from the web folder:

version: '3.1'                          -Specify the version in which it will work

services:                               -The parameters of the service to which connection will be made are established

mydatabase:                             -It is established that a connection will be made to a database

image: mariadb                          -The image that will be the mariadb database management system is placed

restart: always                         -Setting restart conditions

environment:                            -It is where the program development environment is placed

  MYSQL_ROOT_PASSWORD: mydbroot         -The password of the database user.
  
  MYSQL_DATABASE: mydbclass             -Name of the database to which connection is made
  
  MYSQL_USER: mydbuser                  -Name of the user who will make the database connection
  
  MYSQL_PASSWORD: mydbpassword          -The password of the database to which the connection is made.
  
ports:                                  -The section in which you have to put the connection port

  - 3889: 3306                          -It is the port on which the connection to the database is located.
  -
volumes:                                -Choose the volume to save on writing time

  - ./files:/var/lib/mysql/             -It is the directory of the database files
  -
  - ./logs:/var/log/mysql/              -They are the log files of problems in the connection to the database
  -
  - ./conf:/etc/mysql/conf.d/           -It is the file that is generated when the container starts
  
  
Container overview:

It has the utility of implementing applications very quickly

Contains the PHP language

The web server it uses is Apache

The database manager you use is mariaDB
