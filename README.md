
# ECOSISTEMA BIG DATA CON DOCKER

Ambiente para estudio de los principales frameworks de big data en Docker.
<br> Este setup creará contenedores con los frameworks HDFS, HBase, Hive, Presto, Spark, Jupyter, Hue, Mongodb, Metabase, Nifi, Kafka, MySQL y Zookeeper con la siguiente arquitectura:
<br>  

![Ecossistema](ecosystem.jpeg)

## SOFTWARES NECESARIOS
#### Para la creación y uso del ambiente vamos a utilizar Git y Docker
   * Instalación de Docker Desktop en Windows [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows) o Docker en [Linux](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
   * [Instalación de Git](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git)
   
## SETUP
*OBS: Este paso solo debe realizarse una vez. Después de crear el ambiente, utiliza docker-compose para iniciar los contenedores como se muestra en el tema INICIANDO EL AMBIENTE* 

#### Creación del directorio docker:
*OBS: Crea un directorio llamado docker*

   *  Sugerencia en Windows:
      *  Crear en la raíz de tu unidad el directorio docker
         ej: C:\\docker
          
   * Sugerencia en Linux:
      * Crear el directorio en la home del usuario
        ej: /home/user/docker

#### En una terminal/DOS, dentro del directorio docker, realiza el clon del proyecto en GitHub
          git clone https://github.com/fabiogjardim/bigdata_docker.git

#### En el directorio bigdata_docker estarán los siguientes objetos
![ls](ls.JPG)

   
## INICIANDO EL AMBIENTE

  *En Windows abre PowerShell, en Linux una terminal*

### En la terminal, en el directorio bigdata_docker, ejecuta docker-compose
          docker-compose up -d        

### Verificar imágenes y contenedores
 
         docker image ls

![docker image ls](docker_image_ls.JPG)

         docker container ls

![docker container](docker_container_ls.JPG)

## SOLUCIONANDO PROBLEMAS 

  *En Windows abre el Docker Quickstart Terminal*

### Detener un contenedor
         docker stop [nombre del contenedor]      

### Detener todos los contenedores
         docker stop $(docker ps -a -q)
  
### Eliminar un contenedor
         docker rm [nombre del contenedor]

### Eliminar todos los contenedores
         docker rm $(docker ps -a -q)         

### Datos del contenedor
         docker container inspect [nombre del contenedor]

### Iniciar un contenedor
         docker-compose up -d [nombre del contenedor]

### Iniciar todos los contenedores
         docker-compose up -d 

### Acceder al log del contenedor
         docker container logs [nombre del contenedor] 

## Acceso WebUI de los Frameworks
 
* HDFS *http://localhost:50070*
* Presto *http://localhost:8080*
* Hbase *http://localhost:16010/master-status*
* Mongo Express *http://localhost:8081*
* Kafka Manager *http://localhost:9000*
* Metabase *http://localhost:3000*
* Nifi *http://localhost:9090*
* Jupyter Spark *http://localhost:8889*
* Hue *http://localhost:8888*
* Spark *http://localhost:4040*

## Acceso por shell

   ##### HDFS

          docker exec -it datanode bash

   ##### HBase

          docker exec -it hbase-master bash

   ##### Sqoop

          docker exec -it datanode bash
        
   ##### Kafka

          docker exec -it kafka bash

## Acceso JDBC

   ##### MySQL
          jdbc:mysql://database/employees

   ##### Hive

          jdbc:hive2://hive-server:10000/default

   ##### Presto

          jdbc:presto://presto:8080/hive/default

## Usuarios y contraseñas

   ##### Hue
    Usuario: admin
    Contraseña: admin

   ##### Metabase
    Usuario: bigdata@class.com
    Contraseña: bigdata123 

   ##### MySQL
    Usuario: root
    Contraseña: secret   
   
   ##### MongoDB
    Usuario: root
    Contraseña: root
    Base de autenticación: admin

## Imágenes    

[Docker Hub](https://hub.docker.com/u/fjardim)

## Documentación Oficial

* https://zookeeper.apache.org/
* https://kafka.apache.org/
* https://nifi.apache.org/
* https://prestodb.io/
* https://spark.apache.org/
* https://www.mongodb.com/
* https://www.metabase.com/
* https://jupyter.org/
* https://hbase.apache.org/
* https://sqoop.apache.org/
* https://hadoop.apache.org/
* https://hive.apache.org/
* https://gethue.com/
* https://github.com/yahoo/CMAK
* https://www.docker.com/

