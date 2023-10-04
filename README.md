# Arduin_Ros






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


$ sudo apt-get install ros-${ROS_DISTRO}-rosserial-arduino
$ sudo apt-get install ros-${ROS_DISTRO}-rosserial

Para seguir con el siguiente punto es necesario tener un catking workspace creado, pues será el lugar donde se modifican e instalan los paquetes catkin.
 
Los comando para la creación de dicho catking workspace es:

$ mkdir -p ~/catkin_ws/src   Creación del workspace 
$ cd ~/catkin_ws/            Ubicación 
$ catkin_make                Creación un enlace CMakeLists.txt en su carpeta 'src































