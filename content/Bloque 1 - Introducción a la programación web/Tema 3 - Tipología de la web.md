---
title: Tema 3 - Tipología de la web
draft: false
tags:
---

## Estructura general de la web
En general se sigue una estructura cliente-servidor, en la que le navegador web hace de cliente y el servidor web hace de servidor. 
El navegador web es el encargado de interpretar el lenguaje del lado del cliente (*HTTP response*) y renderizar la salida, mientras que el usuario generará eventos que se resolverán mediante código de cliente (*Javascript*) o solicitudes HTTP (*HTTP request*).
Los navegadores actuales sirven como suites de desarrollo avanzadas, que ofrecen herramientas como inspección de código, depuración, medición de carga y tiempos, uso de memoria, edición, etc.

## Tipos de localizaciones
Un **sitio web** tiene como objetivo captar gran cantidad de tráfico y ser visto, por lo que presenta facilidad para el usuario, mientras que un **portal web** tiene como objetivo limitar el tráfico al grupo adecuado de usuarios, a los que se proporcionan servicios.

Un **sitio web estático** es aquel en el que toda solicitud igual al servidor devuelve el mismo código implementado para ese mismo recurso. Es ineficiente para webs que varíen con el tiempo, como una tienda online, pero muy útil si el número de páginas es pequeño y no hay necesidad de personalizar el contenido para cada usuario. La respuesta siempre va acompañada por un código *200 OK* o un código *404 Not Found*. Sólo necesita un servidor web que procese solicitudes *GET*.

Un **sitio web dinámico** es aquel en el que la respuesta devuelta por el servidor se genera para cada petición en base a los datos específicos del *HTTP Request*. Por ejemplo, una tienda virtual obtiene los productos de una base de datos y genera con ellos la *HTTP Response* usando una plantilla *HTML Template* y los productos obtenidos. Necesita la instalación de un **servidor de aplicaciones** que construya las páginas a partir de las plantillas.

Una **aplicación web** es un programa que es accesible mediante un navegador web. Se centra en que el usuario interaccione con el sitio mediante acciones, y la mayor parte del trabajo se realiza en el lado del cliente. La transferencia cliente-servidor es mayormente de datos en lugar de páginas renderizadas.

Una **Single-page application (SPA)** es un tipo de aplicación web que no requiere recarga de la página durante su uso y aprovecha tecnologías AJAX y de micro-servicios. Un ejemplo es Gmail. Ofrecen ventajas como carga rápida, desarrollo más simple, facilidad para transformar a aplicación móvil y guardado de datos en caché de manera efectiva, pero tiene inconvenientes como ser peor para la optimización SEO, ser menos seguro y presentar problemas en la pila de memoria de Javascript, provocando que la aplicación se ralentice.

Un **servicio web** es un punto de acceso a una función software máquina-máquina y que es referenciable mediante URL. Tiene una **interfaz**, encargada de esconder los detalles de la implementación y definir el formato de datos y el acceso a los mismos. Pueden ser utilizados junto con otros servicios, proveyendo múltiples interfaces que constituyen una **API**, y permiten llevar a cabo transacciones complejas.