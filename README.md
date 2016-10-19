# **edu_ciaa_eclipse_env**

Jerarquia de archivos prearmada para programar la edu-ciaa en Eclipse

## Guía de instalación

### Install gcc-arm-none-eabi y Eclipse Luna		


- Descargar gcc-arm-none-eabi de https://launchpad.net/gcc-arm-embedded/+download

- instalar en ./gcc-arm-none-eabi/

- Descargar Eclipse Luna IDE For C/C++ Developers de https://eclipse.org/downloads/packages/eclipse-ide-cc-developers/lunasr2

-Instalar en ./eclipseLuna


### Install OpenOCD y Drivers del On-Board debugger


- Solo para sistemas de 64-bits:

sudo apt-get install libgtk2.0-0:i386 libxtst6:i386 libpangox-1.0-0:i386 libpangoxft-1.0-0:i386 libidn11:i386 libglu1-mesa:i386 libncurses5:i386 libudev1:i386 libusb-1.0:i386 libusb-0.1:i386 gtk2-engines-murrine:i386 libnss3-1d:i386 libwebkitgtk-1.0-0

- Driver del chip FT2232 y el paquete libusb

sudo apt-get install libftdi-dev
sudo apt-get install libusb-1.0-0-dev

- Instalar pkg-config (Necesario para compilar OpenOCD)

sudo apt-get install pkg-config

- Descargar, Descomprimir, Compilar e Instalar OpenOCD (si wget no funciona emplear un web-browser)

wget http://ufpr.dl.sourceforge.net/project/openocd/openocd/0.9.0/openocd-0.9.0.tar.bz2
tar -xvjf openocd-0.9.0.tar.bz2

cd openocd-0.9.0
./configure --enable-ftdi 
make
sudo make install


### Correr Eclipse-IDE					


con PWD = edu_ciaa_env

- Chequear que ·/eclipseLuna/eclipse sea ejecutable. si no lo es, correr

$ chmod +x eclipseLuna/eclipse

- Correr eclipseLuna/eclipse

- Seleccionar como workspace la carpeta edu_ciaa_env/workspace


### Instalar Plug-In GNU-ARM-Eclipse			


En caso que Plug-In GNU-ARM-Eclipse no esté instalado:

- En eclipse ir a Help⇒Install New Software

- Agregar en el sitio de descarga para la instalación la siguiente dirección: http://gnuarmeclipse.sourceforge.net/updates

- Seleccionar todos los paquetes e instalar

- En caso de tener problemas con el proxy, desactivar SOCKS en la configuración de proxy del Eclipse


### Copiar Proyecto Template			


- Opción 1: Importar el proyecto disponible en el MASTER del siguiente repositorio:

https://github.com/EcaDigital-IB/libs_edu_ciaa_baremetal.git

- Opción 2: Descargar el contenido de dicho repositorio y sobrescribir los archivos y carpetas en:

./workspace/edu_ciaa_baremetal/

