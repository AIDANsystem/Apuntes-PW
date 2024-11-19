---
title: Tema 3 - Principios de diseño y arquitectura
draft: false
tags:
---

## Principios de diseño
Se siguen los principios de Tim Berners-Lee (cientfífico padre de la World Wide Web):
- Simplicidad.
- Modularidad (dividir nuestro sistema en módulos).
- Ser parte de un diseño modular (considerar nuestro sistema como parte de un sistema mayor ofreciendo interfaces apropiadas).
- Tolerancia (sé liberal en los requisitos pero conservativo en lo que haces).
- Descentralización.
- Test de invención (si alguien ya hubiese inventado el sistema que estás desarrollando, ¿funcionaría en conjunto con el tuyo?).
- Principio de la potencia mínima (elegir el lenguaje menos potente posible para optimizar la sencillez del diseño, implementación y utilización).

## Arquitectura de la Web
La arquitectura del software es el diseño de más alto nivel de la estructura de un sistema, programa y aplicación. Sus objetivos son:
- Identificar los módulos principales del sistema.
- Identificar la funcionalidad y responsabilidades de cada módulo.
- Definir las interacciones posibles entre módulos.

Los **estilos arquitectónicos** son factores comunes en la estructura, el estilo y los elementos utilizados para dar respuesta a demandas similares. Representan formas diferentes de estructurar un sistema usando componentes y conectores, siguiendo decisiones esenciales sobre los elementos de la arquitectura y estableciendo restricciones sobre esos elementos y las relaciones entre ellos.
Algunos ejemplos de estilos arquitectónicos son:
- **Modelo cliente servidor**: el sistema se organiza en servidores que ofrecen servicios a otros elementos, y clientes que usan los servicios ofrecidos por los servidores. Ofrece una serie de ventajas, como la flexibilidad, la fácil integración de elementos y el fácil mantenimiento local, pero también supone algunos inconvenientes, como el difícil mantenimiento a nivel global, los potenciales cuellos de botella, el difícil manejo de errores, la difícil distribución de datos y la baja confidencialidad y eficiendia.
- **Arquitectura en capas**: modela la interacción entre subsistemas organizándolos en capas. Cada capa presta servicios a la capa superior y actúa como cliente de la inferior. Los conectores entre capas los definen los protocolos utilizados. Soporta el desarrollo incremental de sistemas. También ofrece unas ventajas, como que la arquitectura es cambiable y portable, que las capas son fácilmente reemplazables y que si se cambia una interfaz solo es necesario modificar la capa adyacente, y unos inconvenientes, como que es difícil de estructurar (por ejemplo, el usuario podría requerir acceso a capas internas, lo que es imposible en este modelo) y que el rendimiento puede ser malo.
- **Arquitectura Cliente/Servidor en capas**: en realidad no es un estilo arquitectónico por sí mismo, sino un estilo heterogéneo que mezcla los dos estilos. 

## Modelos basados en Cloud
El **Cloud Computing** es un paradigma de la computación que consiste en delegar la misma en terceros. Ofrece muchísimas ventajas al delegar el control y la configuración a otra empresa.

El **SaaS** o **Software as a Service** es un ejemplo de Cloud Computing que consiste en utilizar una aplicación almacenada y procesada en un servidor remoto, sin tener que instalar nada y recibiendo los resultados de la misma en remoto. Proporciona un modelo de subscripción, asegura la seguridad de los datos, puede escalarse y hace que las aplicaciones sean accesibles desde cualquier dispositivo conectado a internet. Algunos ejemplos de aplicaciones SaaS son Dropbox y Google Drive.

El **PaaS** o **Platform as a Service** es otro ejemplo de Cloud Computing en el que se ofrece un entorno remoto para desarrollar, gestionar, personalizar y distribuir aplicaciones del cliente. Sus funciones principales son:
- Ofrece un entorno remoto unificado.
- Permite centrarse en el desarrollo en lugar de en la configuración y la infraestructura subyacente.
- El proveedor gestiona la seguridad, los sistemas operativos y demás.
- Facilita la colaboración remota
Un ejemplo de aplicación PaaS es Google App Engine.

El **IaaS** o **Infrastructure as a Servide** es el último ejemplo de Cloud Computing que vamos a ver, en el que el proveedor proporciona acceso a infraestructura remota, como servidores, almacenamiento y redes, dejando al cliente usarlos para lo que quiera. Así, la infraestructura es escalable, se ahorra en coste de compra de hardware propio y su manteminiento y se virtualizan las tareas administrativas. Un ejemplo es Amazon Web Services (AWS).

## Microservicios
Los microservicios son un estilo arquitectónico en el que las aplicaciones complejas se dividen en servicios que se pueden desplegar independientemente del resto, realizan una tarea de forma eficaz, son independientes del lenguaje con otros microservicios y se pueden comunicar con otros microservicios mediante APIs. Este estilo no es el adecuado para comenzar una aplicación, sino que se debe adoptar para enfrentarse a problemas de escalabilidad. Los microservicios ofrecen ventajas como que son pequeños (fáciles de desarrollar, mantener y desplegar), que son independientes, que es sencillo organizar equipos de proyecto con metodologías ágiles para su desarrollo y que es sencillo aislar errores en ellos. Sin embargo, hay algunos inconvenientes en su uso: suponen un mayor consumo de memoria, su desarrollo conjunto a nivel de sistema es complejo y su despliegue y mantenimiento en conjunto es costoso en producción.