---
layout: post
title: Configuración
description: Este es mi setup mi personal.  
---
{: .large}
# Artix Linux - Distribución de Linux basada en Arch Linux. 

 ![Artix Linux](/assets/images/pc.jpg)

Como usuario novato de Linux que soy, me desafié a instalar Artix Linux, la ISO de base, el cual no tiene interfaz gráfica. Es como tener Arch linux y también cuenta con todas sus ventajas, pero en su tarjeta de presentación no cuentan con **"Systemd",** ya que es un sistema simple, rápido y gratis.  

#### ¿Pero, qué es Systemd?
[Systemd](https://wiki.archlinux.org/title/systemd_(Espa%C3%B1ol)) es un conjunto de bloques básicos de compilación para un sistema Linux. Proporciona un gestor de sistemas y servicios que se ejecuta como PID 1 e inicia el resto del sistema. systemd proporciona una notable capacidad de paralelización, utiliza la activación de socket y D-Bus para iniciar los servicios, permite el inicio de demonios bajo demanda, realiza un seguimiento de los procesos con el uso de los grupos de control de Linux, mantiene los puntos montaje y servicios de montaje automático e implementa un elaborado sistema de gestión de dependencias basado en un control lógico de los servicios.
#### Systemd como tragedia 
En 2016, systemd comenzó a eliminar los procesos de los usuarios al cerrar la sesión (en lugar de enviarles la señal SIGHUP, como dice POSIX que debería suceder). Esto causó problemas a programas como nohup, screen y tmux, que siguen ejecutándose deliberadamente. La respuesta de Systemd fue decir que deberían incorporar la biblioteca de systemd y usar la nueva API de daemonización de systemd. Y según lo que he investigado, ninguno de ellos lo hizo.

Dos años más tarde, se puede encontrar cientos de solicitudes de soporte en Internet, de usuarios frustrados a quienes systemd les está quitando sus sesiones.

Los errores son molestos, pero así es la vida. Por otro lado, cuando uno es un usuario afectado que ha perdido el trabajo, y la investigación del error lo lleva a una discusión de años en la que alguien niega activamente que el error existe y se niega a solucionarlo, eso es exasperante . No creo que los desarrolladores de systemd merezcan la confianza que requiere el mantenimiento de una parte central de la infraestructura; no parece importarles lo suficiente si han roto cosas.
### Continuando con el tema de Artix Linux 
Hubo gente que hizo esta bifurcación de Arch Linux y la llamaron Arch Open RC y otro grupo de personas que también hicieron un curso similar, como un sistema de inicio y las personas que estaban ejecuntando o que bifurcaron a Manjaro (distribución basada en Arch) en un un RC abierto donde unieron fuerzas para crear Artix Linux. 

Una de las cosas de esto por supuesto, es que tienen las instalaciones de base como Arch, pero cuentan con escritorios configurado de forma predeterminada. 

Solo por cambiar algo el día de hoy
