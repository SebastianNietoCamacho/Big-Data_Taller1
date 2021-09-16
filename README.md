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
      ![image](https://user-images.githubusercontent.com/90856580/133661619-692c7b24-20e8-423c-9fcb-0e483a1830ea.png)
      
   ──► Instalar OpenJDK en Ubuntu.
   ```
   $ sudo apt update 
   ```
   ![image](https://user-images.githubusercontent.com/90856580/133662178-63bd359b-c122-4c6b-a763-904f6b95fede.png)

   ```
   $ sudo apt install openjdk-8-jdk -y 
   ```
   ![image](https://user-images.githubusercontent.com/90856580/133662382-6368e9e3-7b66-445c-a5ff-b83f39c4ce06.png)

   ```
   $ java -version; javac -version
   ```
   ![image](https://user-images.githubusercontent.com/90856580/133662427-58a16aaa-25de-488f-a1cf-2167bc868bef.png)



