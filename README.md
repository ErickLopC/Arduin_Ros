# Arduin_Ros





# Configuración de Arduino IDE
Se accede a la pagina oficial de [Arduino](https://www.arduino.cc/en/software), se descarga la versión de preferencia en este caso la 1.8.19-64 Linux.

Se descomprime el archivo 

Se abre una terminal (CTRL+ALT+T) y desde dicha terminal se accede a la carpeta de instalación 

```
cd Descargas/arduino-1.8.19-linux64/arduino-1.8.19
```
Se cambia el permiso del Scrip instalador (install.sh) esto se realiza en la misma terminal del paso anterior 

```
sudo chmod+xinstall.sh
```
Dicho comando ejecutara el archivo de instalación sin necesidad de tener cuenta de usuario root.
Se ejecutara la ultima instrucción para el desarrollo de Arduino.

```
$ ./install.sh
```

Nota: Debido al tipo de máquina puede que el acceso directo no se creé en automático, no obstante se puede abrir desde la bóveda de aplicaciones y agregarlo a favoritos 

Se recomienda la instalación de binarios en la estación de trabajo ROS (Instalación del rosserial para Arduino) 

# Instalación de rosserial
```
sudo apt-get install ros-${ROS_DISTRO}-rosserial-arduino
sudo apt-get install ros-${ROS_DISTRO}-rosserial
```

# Configuración del workspace
Para seguir con el siguiente punto es necesario tener un catking workspace creado, pues será el lugar donde se modifican e instalan los paquetes catkin.
 
Los comando para la creación de dicho catking workspace es:

```
mkdir -p ~/catkin_ws/src   Creación del workspace 
cd ~/catkin_ws/            Ubicación 
catkin_make                Creación un enlace CMakeLists.txt en su carpeta 'src
```

El nombre del Workspace a utilizar en este caso es catkin_ws

Antes de continuar se debe compilar el nuevo archivo setup.*sh mediante:

```
source devel/setup.bash
```

Para asegurarse de que su espacio de trabajo esté correctamente superpuesto por el script de configuración, asegúrese de que la variable de entorno ROS_PACKAGE_PATH incluya el directorio en el que se encuentra. 

```
 echo $ROS_PACKAGE_PATH /home/youruser/catkin_ws/src:/opt/ros/kinetic/share
```


Instalación desde Source en la estación de trabajo ROS 
Existen 2 tipos de posible instalación en este caso, se trabajara con el groovy+ (catkin) por lo tanto se escribirán los siguientes comandos

```
cd <ws>/src
git clone https://github.com/ros-drivers/rosserial.git
cd <ws>
catkin_make
catkin_make install
```
Instale ros_lib en el entorno Arduino 
Los pasos anteriores crearon las bibliotecas necesarias, ahora se creara una carpeta llamada ros_lib la cual es el entorno de compilación que arduino necesita para que los programas de arduino trabajen con ros.
En los pasos siguientes, <sketchbook> es el directorio donde el entorno Linux Arduino guarda sus bocetos. Normalmente, este es un directorio llamado sketchbook o Arduino en su directorio de inicio. por ejemplo, 

```
cd Arduino
```

Nota: debe eliminar bibliotecas/ros_lib, si está presente, para poder regenerar, ya que su existencia provoca un error. "rosrun rosserial_arduino make_libraries.py" crea el directorio ros_lib. 

Una vez ubicados en la carpeta de Arduino, se escribirán los siguientes comandos

```
 $ rm -rf ros_lib
 $ rosrun rosserial_arduino make_libraries.py .
```

Nota: Actualmente puedes instalar las bibliotecas de Arduino directamente en el IDE de Arduino. Simplemente abra el Administrador de biblioteca desde el menú IDE en Sketch -> Incluir biblioteca -> Administrar biblioteca. Luego busque "rosserial". Esto es útil si necesita trabajar en un boceto de Arduino pero no desea configurar una estación de trabajo ROS completa.
Finalmente se tiene que corroborar que la instalación fue satisfactoria, por ello se tendrá que abrir una pestaña de arduino y nos dirigimos a la parte superior izquierda, en Archivo/Proyecto/ros_lib



http://wiki.ros.og/rosserial_arduino/Tutorials/Arduino%20IDE%20Setup 


Para la primer practica realizada, se comprobará que exista una comunicación entre el arduino y ROS por lo que se ejecutara y se cargara el siguiente código al arduino. 






















