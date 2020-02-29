# Lectura de históricos en Linux (Logs)

Los logs de linux tienen la capacidad de almacenar toda los eventos que ocurren
durante la ejecución de los demonios :japanese_ogre: de un sistema operativo (SO) GNU/Linux.

## Ruta de almacenamiento de los históricos

La ruta por defecto para almacenar los históricos de los sistemas GNU/Linux es
`/var/log`

## Algunos logs que se usan con frecuencia

**boot.log** Almacena los eventos que han sucedido al arrancar el SO.
Generalmente usado cuando para equipos remotos.

**cron** Los eventos generados por las tareas programadas se almacenan en el est archivo.
Esto permite conocer los comandos que se están ejecutando de forma automática.

**dmesg** Este log es de los más interesantes debido a que es el encargado de reconocer
los dispositivos conectados a nuestro equipo.

**secure** Cada intento de autenticacion :key: en el equipo se guardará en este log. A continuación se detalla
ejemplos de como analizar :mag: esta información.

## Intentos de logue fallidos a Centos 7

Para analizar el log *secure* podemos usar el comando **grep** o **zgrep**
el cual nos permite agregar filtros en busqueda de información precisa.

- Ejemplo :one: Listado de ip y usuario usado en logueo fallido.

`zgrep -hi "Failed password for " /var/log/secure* | sed "s/invalid user //" | tr -s " " | awk '{print $11" "$9}' | sort | uniq -c | sort -rn | head -20`

 
