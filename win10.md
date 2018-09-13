# Instalación y configuración de Hadoop en modo local (*standalone*)


Esta guía describe la instalación y configuración  de Apache Hadoop en modo standalone. 
Esta es la instalación más simple.

### Paso 1

Descargue Java SE Development Kit (JDE) 8u181 (jdk-8u181-linux-x64.tar.gz). 

http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html


### Paso 2

En el explorador de archivos, descomprima el archivo `jdk-8u181-linux-x64.tar.gz`.


### Paso 3

Habra Terminal, navegue hasta el folder de descargas (`/home/USER/Downloads`), y 
descomprima el archivo con

    tar -xvf jdk-8u181-linux-x64.tar


### Paso 4

Mueva el archivo a su directorio home. Puede usar el comando `mv` o la utilidad de 
manejo de archivos.

    mv jdk1.8.0_181 ~/jdk1.8.0_181

### Paso 5

Descargue Apache Hadoop 3.1.1 de https://hadoop.apache.org/releases.html


### Paso 6

Descomprima el archivo desde Terminal (ubicado en el folder `Downloads`):

    tar -xvf hadoop-3.1.1.tar
    
    
### Paso 7

Mueva el archivo a su directorio `home` y renombrelo. Puede usar el comando `mv` o la utilidad de 
manejo de archivos.

    mv hadoop-3.1.1 ~/hadoop


### Paso 8

Edite su archivo `.bashrc` usando un editor de textos. Puede hacer esto desde
la línea de comandos con:

    code ~/.bash_profile
    
Agregue los siguientes comandos (reemplace `USER` por su nombre de usuario):

    export JAVA_HOME="/home/USER/jdk1.8.0_181"
    export PATH="$JAVA_HOME/bin:$PATH"

    export HADOOP_HOME="/home/jdvelasq/hadoop"
    export HADOOP_COMMON_LIB_NATIVE_DIR="$HADOOP_HOME/lib/native"
    export HADOOP_OPTS="-Djava.library.path=$HADOOP_HOME/lib/native"
    export HADOOP_OPTS="-Djava.library.path=$HADOOP_HOME/lib/native"
    export HADOOP_ROOT_LOGGER="ERROR,console"
    export HADOOP_CLASSPATH=$JAVA_HOME/lib/tools.jar
    export PATH="$HADOOP_HOME:$HADOOP_HOME/bin:$PATH"


### Paso 9

Verifique la instalación. En Terminal digite 

    source ~/.bashrc

para hacer efectivos los cambios. Luego digite `hadoop` en la línea de comandos. 
Como resultado, debe imprimirse la ayuda de hadoop en la pantalla.


**Nota.--** En este paso, Apache Hadoop se puede ejecutar en modo *standalone*.

**Nota.--** Hadoop usará el sistema local de archivos como sistema HDFS.
