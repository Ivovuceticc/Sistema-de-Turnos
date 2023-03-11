# Sistema-de-Turnos

--Desarrollo de un sistema distribuido simple--
-Es un sistema web de reservas, el cual utiliza una arquitectura de microservicios interoperable y la utilizacion de una API rest.

--Propósito--
-Tiene como proposito permitir que los usuarios reserven, mediante una web, un turno eligiendo una fecha, hora y sucursal.

--Requerimientos funcionales--
1-El sistema debe permitir reservar un turno a un usuario no registrado, ingresando un
email y eligiendo la fecha, la hora y la sucursal. [RF-1]
2-El sistema debe mostrar la ubicación de las sucursales en un mapa. [RF-2]
3- El sistema no debe permitir que 2 usuarios reserven un mismo turno (misma fecha y
hora, en una misma sucursal). [RF-3]

--Requerimientos no funcionales--
1- El sistema ofrecerá una interfaz web como cliente gráfico que debe ser compatible
con los navegadores modernos. [RNF-1]
2-La interfaz web deberá desarrollarse como SPA sin ningún framework de front-end[RNF-2]
3-El sistema deberá implementar una arquitectura de microservicios en el servidor. Uno de los microservicios será un “API Gateway”, es
decir un intermediario entre el cliente web (ofreciendo una API REST) y el resto de los microservicios. [RNF-3]
4-Los microservicios deberán desarrollarse utilizando Node.js, sin ningún framework de servidor. Para las peticiones de HTTP sólo podrán
utilizarse los módulos nativos de Node.js. [RNF-4]
5-El mapa con sucursales debe realizarse utilizando la API HTTP de Cartes.io.[RNF-5]
6-Los turnos se almacenarán en un archivo plano con formato JSON[RNF-6]
7-Las sucursales se leerán de un archivo plano con formato JSON que puede ser escrito manualmente o mediante un script.[RNF-7]

--Casos de uso de reserva de turno(RF-1)--
 Flujo principal:
1. El usuario completa el formulario para registrar un turno.
2. El sistema verifica que el turno esté disponible y pide confirmación del
mismo.
3. El usuario confirma el turno.
4. El sistema registra el turno.
● Flujo alternativo A:
○ 2.1. El sistema verifica que el turno no está disponible y notifica al usuario.
● Flujo alternativo B:
○ 4.1. El usuario no confirma el turno.

--Arquitectura--
-El sistema se desarrollo siguiendo una arquitectura clasica de microservicios. Cuanta con un componente denominado "API Gateway" que funciona como un intermediario entre el cliente web y el resto de los microservicios. Cada servicio es un proceso que contiene un conjunto de funcionalidades relacionadas y ofrece una interfaz HTTP para que pueda comunicarse con el mismo.
El resto de los servicios que componen el sistema son:
1-Gestion de reservas: Ofrece una interfaz ABM para la manipulación de los datos del
JSON.
2-Gestion de sucursales: Encargado de informar las sucursales donde se pueden reservar turnos.

--Documentación adicional--
Se adjunta un archivo de la comunicación con la API.
