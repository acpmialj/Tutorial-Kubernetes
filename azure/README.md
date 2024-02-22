# Acceso a carpetas compartidas de Azure desde kubernetes

## Pre-requisitos
Instalación driver kubernetes-CSI para carpetas de Azure en minikube, desde:

https://github.com/kubernetes-sigs/azurefile-csi-driver/blob/master/docs/install-csi-driver-v1.29.2.md

## Carpeta a compartir
Se ha creado una cuenta de almacenamiento **ipmdstorage**. Dentro de ella se ha creado una carpeta compartida **ipmdfs**, sin backup. 

## Conexión
Para establecer la conexión se necesita 

* El nombre del servidor: ipmdstorage.file.core.windows.net (cuenta.file.core.windows.net)
* La carpeta: ipmdfs
* El nombre de usuario (que es el nombre de la cuenta): ipmdstorage
* La contraseña asociada a la cuenta

Los campos nombre_usuario/contraseña se almacenan en un secreto de kubernetes. 

En los ficheros de configuración de pods, se indica

* El nombre de la carpeta
* El secreto a usar, que contiene el resto de la información necesaria
