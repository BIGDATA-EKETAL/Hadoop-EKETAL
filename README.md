# Hadoop-EKETAL

En este repositorio se encuentra el código fuente de Hadoop compilado con la herramienta para eventos distribuidos.

# Construcción desde código fuente
Para construir Hadoop desde el codigo fuente, debe tener una plataforma con lo siguiente:

* Un ambiente Unix (Linux, OS X, etc).
* git
* Maven 3.3.9 o más nuevo.
* Oracle JDK 8 o más nuevo.
* Ambiente EKETAL en: https://github.com/unicesi/eketal

Instrucciones para construir desde master:

* Checkout Hadoop master:

  $ git clone
  
 * Build Hadoop master:
 
  $cd hadoop
  $mvn clean package -DskipTests 
 
# Ejecute la construcción en su máquina

Estos son los pasos para ejecutar Hadoop y un ejemplo básico con EKETAL en su máquina local:

* Inicie una instancia de Hadoop de una sola máquina:

  $ hadoop namenode -format
  $ start-dfs.sh
  
* Para crear un directorio de enytrada dentro de HDFS de Hadoop

  $ $HADOOP_HOME/bin/hadoop fs -mkdir /user/input
  
* Para transferir y almacenar un archivo de datos de sistemas locales en Hadoop en el sistema de archivos utilizando el comando put, para este caso vamos a ejecutar el ejemplo Wordcount que consta de contar las palabras y sus concurrencias que pueden haber en el archivo para esto utilizamos los siguientes comandos:

  $ $HADOOP_HOME/bin/hadoop fs -put /home/file.txt /user/input
  $ $HADOOP_HOME/bin/hadoop jar hadoop-examples-*.jar Wordcount input output
  
* Para mostrar los datos obtenidos se hace con el siguiente comando:

  $ $HADOOP_HOME/bin/hadoop fs -cat /user/output/outfile
