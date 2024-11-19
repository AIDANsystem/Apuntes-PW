---
title: Tema 2 - Fundamentos de Internet
draft: false
tags:
---

### Protocolos
En Internet se utiliza el protocolo TCP/IP para la comunicación entre redes físicas. Cada mensaje ha pasado por una pila de protocolos que han ido añadiendo capas al mismo.
El protocolo IP es un sencillo protocolo de envío de datos en el que cada dispositivo tiene una dirección de 32 bits (en IPv4) separada en 4 bloques de 8 bits que identifica al dispositivo en la red.
El protocolo TCP garantiza la entrega de los mensajes sobre IP, en contraposición al protocolo UDP que no la garantiza. TCP es un protocolo multiplexado, lo que significa que un dispositivo tiene múltiples puertos para que las múltiples aplicaciones que se comunican desde el ordenador y que por tanto tienen la misma IP puedan diferenciarse al enviar y recibir mensajes. Los puertos los controla la IANA (Internet Assigned Numbers Authority), una fundación privada perteneciente a la ICANN. Los puertos del 00 al 1023 se denominan puertos de sistema o *well-known ports*. Algunos ejemplos son:
![[Captura de pantalla 2024-09-24 a las 11.34.43.png]]

Los puertos de 1024 a 49151 son puertos registrados a demanda de las entidades o empresas que los reservan. Algunos son:
![[Captura de pantalla 2024-09-24 a las 11.35.26.png]]

Los puertos 49152 a 65535 son los puertos *never assigned*, puertos privados.

El protocolo DNS (Domain Name System) mapea nombres a direcciones IP.

Una **URI** (Uniform Resource Identifier) es una cadena de caracteres que sirve como localizador, nombre o ambos para los recursos en Internet.
![[Captura de pantalla 2024-09-25 a las 12.56.40.png]]

![[Captura de pantalla 2024-09-25 a las 12.59.29.png]]

### Protocolo HTTP
Establece el conjunto de comandos interpretados por el servidor web. Permite diferentes tipos de peticiones:
- **Peticiones seguras** (sólo lectura):
	- **GET**: devuelve el recurso identificado por una URI.
	- **OPTIONS**: retorna las opciones de comunicación disponibles.
	- **HEAD**: inspecciona la cabecera del recurso (metadatos).
- **Peticiones idempotentes** (puede realizarse de forma idéntica varias veces, devolviendo siempre el mismo resultado):
	- **PUT**: solicita al servidor guardar el cuerpo de la solicitud en la ubicación dada por la URL.
	- **DELETE***: solicita al servidor que elimine el recurso de la URL dada.
- **Peticiones no idempotentes** (realizar múltiples peticiones idénticas podría causar efectos adicionales):
	- **POST**: envío de información al servidor (por ejemplo, la información para rellenar un formulario).
	- **PATCH**: solicita aplicar cambios a un recurso concreto identificado por la URI.
- Otras peticiones:
	- **CONNECT**: establece una conexión sin cierre con el servidor.
	- **TRACE**: prueba de eco de retorno.

Los **códigos de estado** son identificadores y metainformación asociados a la respuesta recibida por el servidor. Son de tres cifras, pero es la primera la que indica lo importante de la respuesta. Los tipos son:
- **1xx** - Códigos informativos.
- **2xx** - Códigos de éxito.
- **3xx** - Códigos de redirección.
- **4xx** - Códigos de error en cliente.
- **5xx** - Códigos de error en el servidor.
Algunos ejemplos de códigos comunes son:
- 100 - Continue.
- 200 - OK.
- 203 - Non-Authoritative Information.
- 301 - Moved Permanently.
- 404 - Not Found.
- 408 - Request Timeout.
- 500 - Internal Server Error.
- 503 - Service Unavailable.

Los **tipos de medio** nos indican la naturaleza de la respuesta que el servidor envía. Indica el formato de la respuesta: si es un mp4, texto plano, un PDF, etc. La encargada de registrar un tipo de medio es la IANA. Algunos ejemplos son:
- text/html (.html)
- text/plain (.txt)
- image/gif (.gif)
- image/jpeg (.jpg)
- video/quicktime (.mov)
- application/octet-stream (.exe)

Por tanto, al descargar una página web, el buscador web hace una serie de GETs con los elementos de la página, cuya respuesta sigue la estructura *<Código de estado> <tipo de* *medio> <bits de información>*.

Para el desarrollo de páginas web, para el desarrollo independiente de back y front-end podemos usar herramientas que simulen la otra parte. Para desarrollar el front, podemos usar [JSON placeholder](https://jsonplaceholder.typicode.com), que simula el back-end de una web. Igualmente, para desarrollar el back podemos usar [Postman](https://www.postman.com), que simula el front de una web.

En un ejemplo en el que implementamos las APIs CRUD (Create, Read, Update, Delete) de una página web que almacene tareas, implementamos lo siguiente:
- Para Read:
	- *GET /tareas* o *Get /tareas/\<id\>*
- Para Create:
	- *POST /tareas*
- Para Update:
	- *PUT /tareas/\<id\>*
	- *PATCH /tareas/\<id\>*
- Para delete:
	- DELETE */tareas/\<id\>*
Con códigos de respuesta:
- *200 - OK*
- *201 - Created*
- *204 - No content*
- *404 - Not found*
- *400 - Bad request*