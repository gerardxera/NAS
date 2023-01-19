# Instalación de OpenMediaVault ( OMV ) en una Raspberry Pi

OpenMediaVault ( OMV ) es una solución de almacenamiento conectado a la red de código abierto ( NAS ).
OMV tiene una interfaz basada en la web que se puede utilizar para configurar casi todos los aspectos del servidor. Con complementos y extensiones, 
también puede ejecutar Docker y Portainer, lo que facilita al sistema para ejecutar una gran cantidad de aplicaciones.

Para seguir este artículo, necesitará una Raspberry Pi recién instalada. Usaré un Pi 4(4GB) con Raspberry Pi OS Lite(64-bit) como sistema operativo instalado,
ya que (OMV) no funcionará en sistemas con un entorno de escritorio. Instalaré OpenMediaVault 6, es la última versión al momento de escribir.
– Llevaré a cabo toda la configuración a través de SSH.

# Accedemos el servidor Pi via terminal o PuTTY

Introducimos el siguente comando para conectarnos con su usuario y IP de la Pi server. Nos solicitara la contraseña de dicho usuario para acceder.
```
ssh: pi@192.168.1.?? 
```

Actualice la máquina con:
```
sudo apt update
sudo apt upgrade
```

# Instalación de OMV 6 en una Raspberry Pi 4

Ahora ejecute el siguiente comando para descargar y ejecutar el script de instalación para OMV:
```
sudo wget -O - https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash
```
Este comando viene de aquí, que es de omv-extras.org un grupo que construye complementos para OMV y también facilita la instalación en Raspberry Pi.
La instalacion de OMV tarda unos 30 minutos, al final reiniciará la máquina –, saldra de la sesión SSH del terminal.
Es importante que este script no se interrumpa mientras funciona, déjelo hacer lo suyo. 
Después del reinicio, dale al Pi unos 5 minutos para terminar la configuración y la primera ejecución de OMV.

OMV realiza muchos cambios en la máquina y es completamente posible que termine con una nueva dirección IP o que los inicios de sesión SSH ya no funcionen. En mi caso ninguno cambió.

# OMV primer inicio de sesión

OMV apunta el puerto 80, que es el puerto HTTP estándar. Debería poder acceder a su servidor recién instalado en
```
http://IP_ADDRESS_PI
```
Donde IP_ADDRESS_PI es la dirección de su servidor. Inicie sesión con el nombre de usuario y contraseña predeterminados:
```
Nombre de usuario: admin
Contraseña: openmediavault
```
Ahora debería ver la página de inicio de OMV

Cambie la contraseña del usuario administrador. Esto se hace haciendo clic en el icono de la persona en la esquina superior derecha, selecciona cambiar la contraseña.

Ya está listo para la instalación inicial y la configuración de OMV 6.

