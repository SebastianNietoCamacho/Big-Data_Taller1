# Big-Data_Taller1
Este repositorio contendrá la descripción de cuatro partes de un taller de 'Big Data and Analytic' en donde se realiza la instalación, configuración y uso de herramientas como Hadoop, Spark y Anaconda.


PARTE UNO

Hadoop se encuentra optimizado para ser ejecutado en sistemas operativos basados en el kernel Linux y requiere de la JVM (Java Virtual Machine) para su ejecución.

1. En caso de no poseer un sistema operativo Linux, se debe descargar e instalar VirtualBox o VMWare.

   Se instaló VirtualBox en su versión 6.1.

   <img src="https://user-images.githubusercontent.com/90856580/133651737-0df391a8-f5f1-4d02-9d48-2b2c51639fe3.png" width="350px" hight="100px"> 

2. Teniendo la máquina virtual establecida, se debe instalar sobre esta un sistema operativo basado en Linux como Ubuntu.

   Se instaló Ubuntu en su versión 21.04.
  
   <img src="https://user-images.githubusercontent.com/90856580/133654221-aa7125b4-4e56-4893-8d09-7003dc5c9004.png" width="350px" hight="100px"> 

3. Al tener adecuado el ambiente para la instalación de Hadoop, se deben seguir las instrucciones de la siguiente guía: http://cis.csuohio.edu/~sschung/cis612/Instruction_INSTALLING_HADOOP_Ubuntu.pdf. 
   Los pasos establecidos allí se indicarán a continuación: 
   
   ──► Prerequisitos.
   ```
   $ cp ~/.bashrc ~/.bashrc.bak    
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133661619-692c7b24-20e8-423c-9fcb-0e483a1830ea.png" width="500" hight="300"> 
      
      
   ──► Instalar OpenJDK en Ubuntu.
   ```
   $ sudo apt update 
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133662178-63bd359b-c122-4c6b-a763-904f6b95fede.png" width="500" hight="300"> 
   ```
   $ sudo apt install openjdk-8-jdk -y 
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133663499-7761818b-2531-4867-8b91-d5d0fe1aaee4.png" width="500" hight="300"> 
   
   ```
   $ java -version; javac -version
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133662427-58a16aaa-25de-488f-a1cf-2167bc868bef.png" width="500" hight="300"> 


   ──► Configurar un usuario no-root para el entorno de Hadoop.
   ```
   $ sudo apt install openssh-server openssh-client -y
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133668255-308aaa47-4964-486e-a35f-84fa382731a8.png" width="500" hight="300"> 


   ──► Crear un usuario Hadoop.
   ```
   $ sudo adduser hdoop
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133668398-e222f05d-7ab0-479c-98ee-c7d77be749bb.png" width="500" hight="300"> 
   
   ```
   $ su - hdoop
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133669229-b25fd509-7c9d-4d05-b4f8-67ac6efc416f.png" width="500" hight="300"> 


   ──► Habilitar SSH sin contraseña para el usuario de Hadoop.
   ```
   $ ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133669299-aac8d67c-c1ac-4ffa-a7e5-07b6e5db8a24.png" width="500" hight="300"> 
   
   ```
   $ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
   $ chmod 0600 ~/.ssh/authorized_keys
   $ ssh localhost
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133669457-320c3b8d-14d9-423d-8347-870c67fff1ac.png" width="500" hight="300"> 


   ──► Descargar e instalar Hadoop en Ubuntu.
   ```
   $ wget [yourlink]
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133669995-6cb09d59-c49b-4e49-ad2a-c121111cd409.png" width="500" hight="300"> 
  
  
   ──► Configuración de variables del entorno de Hadoop (.ashrc).
   ```
   $ sudo nano .bashrc
   ```
   
   ```
   $ source ~/.bashrc
   ```


   ──► Edición del archivo hadoop-env.sh.
   ```
   $ sudo nano $HADOOP_HOME/etc/hadoop/hadoop-env.sh
   ```
   
   
   ──► Edición del archivo core-site.xml.
   ```
   $ sudo nano $HADOOP_HOME/etc/hadoop/core-site.xml  
   ```
   
   
   ──► Edición del archivo hdfs-site.xml.
   ```
   $ sudo nano $HADOOP_HOME/etc/hadoop/hdfs-site.xml
   ```
   
   ```
   $ sudo mkdir /home/hdoop/dfsdata/namenode
   $ sudo mkdir /home/hdoop/dfsdata/datanode
   ```
   
   
   ──► Edición del archivo mapred-site.xml.
   ```
   $ sudo nano $HADOOP_HOME/etc/hadoop/mapred-site.xml 
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133671487-6203ff90-6502-4a47-8a68-f8d6e5098389.png" width="500" hight="300"> 


   ──► Edición del archivo yarn-site.xml.
   ```
   $ sudo nano $HADOOP_HOME/etc/hadoop/yarn-site.xml 
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133671518-20de7cc5-e147-427d-85e6-c1801c1cd0d3.png" width="500" hight="300"> 


   ──► Formateo de HDFS NameNode.
   ```
   $ hdfs namenode -format 
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133671661-3f65f35b-9d1c-4ee0-9a28-d78486154540.png" width="500" hight="300"> 


   ──► Iniciar el Cluster de Hadoop.
   ```
   $ ./start-dfs.sh    
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133671960-db319950-bee3-4853-9664-0958b66fb673.png" width="500" hight="300"> 
   
   ```
   $ ./start-yarn.sh 
   $ jps 
   ```
   <img src="https://user-images.githubusercontent.com/90856580/133672313-dd43a780-946d-4613-8e05-c36b683c3a09.png" width="500" hight="300"> 
   
   
   ──► Acceder a la interfaz de usuario de Hadoop desde el navegador.  
   ```
   http://localhost:9870 
   ```
   
   ```
   http://localhost:9864 
   ```
   
   ```
   http://localhost:8088 
   ```


PARTE DOS

MapReduce es el componente de Hadoop que se encarga de procesar grandes volúmenes de datos de manera distribuida y escalable.

1. Una vez instalado Hadoop, se hace uso de la guía oficial de Apache: https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/SingleCluster.html, en su sección de "Execution" para seguir los pasos del 4 al 7 con el fin de ejecutar un programa de ejemplo.

   ```
   $ bin/hdfs dfs -mkdir /user
   $ bin/hdfs dfs -mkdir /user/<username>
   ```
   
   ```
   $ bin/hdfs dfs -mkdir input
   $ bin/hdfs dfs -put etc/hadoop/*.xml input
   ```
   
   ```
   $ bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-3.3.1.jar grep input output 'dfs[a-z.]+'
   ```
   ![image](https://user-images.githubusercontent.com/90856580/133679956-d7eb037f-0a0d-46de-a50b-aa6c98a8a6f5.png)

   ```
   $ bin/hdfs dfs -get output output
   $ cat output/*
   ```
   ![image](https://user-images.githubusercontent.com/90856580/133680013-8dd45d09-f777-4bdf-b5e4-d84da1ebc996.png)



   



