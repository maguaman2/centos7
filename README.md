# SSH Claves públicas y privadas

Encriptar información para acceso a servidores CENTOS 7

## Introducción 

El sistema operativo CENTOS y los basados en UNIX en general pueden
trabajar con el paquete **sshd** para permitir conexiones remotas.

Esto es una buena alternativa para las conexiones usando *usuario -> clave*

### Copia entre maquinas remotas 

Copiar desde una maquina hacia un servidores.

Comando: 

`scp origen destino`

- Ejemplo :one: Copiar carpeta etc local a la capeta temporal de un equipo remoto

`scp -r /etc/ 192.168.1.1:/tmp`

- Ejemplo :two: Copiar carpeta etc de una maquina remota a la capeta local (. significa donde esty actualmente)

`scp -r 192.168.1.1:/etc .`

:warning :Este apartado es necesario para posteriormente copiar las claves entre servidores

### Crear clave pública y privada

Las claves :key: *públicas* y *privadas* son generadas en una máquina, :computer: luego la clave *pública*
es copiada al servidor donde nos vamos a conectar. 

