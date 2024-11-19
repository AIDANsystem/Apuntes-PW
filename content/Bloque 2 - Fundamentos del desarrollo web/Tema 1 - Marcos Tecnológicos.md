---
title: Tema 1 - Marcos Tecnológicos
draft: false
tags:
---

## Pila de tecnología
El término **pila de tecnología** se refiere al conjunto de herramientas, lenguajes y software que se utiliza para el desarrollo y despliegue de un producto web o una aplicación móvil. Por lo general, se compone de las tecnologías usadas en el lado del servidor (**back-end**) y las tecnologías usadas en el lado del cliente (**front-end**). El back-end, desarrollado con lenguajes de programación como Java, Ruby o PHP, contiene el comportamiento interno de la aplicación, y el usuario nunca accede a él. Por otro lado, el front-end es la parte visual de la aplicación, con la que interactúa el usuario, y se desarrolla principalmente con lenguajes de marcado como HTML y CSS y el lenguaje de programación Javascript.

## Web frameworks
Un **framework** es un *software abstracto* que ofrece funciones genéricas para ser utilizadas o adaptadas por el código del desarrollador y facilitar así el desarrollo de aplicaciones específicas. Para considerarse un framework, debe ser independiente al dominio de la aplicación, ser universal y ofrecer un entorno reutilizable. Algunas características distintivas de un framework son:
- Inversión del control: el flujo del sistema lo controla el framework
- Extensibilidad: el desarrollador puede extender su funcionalidad.
- Estabilidad: el código del framework es transparente al desarrollo, que no preverá cambios en el código que afecten a su aplicación.
- Compatibilidad hacia atrás: la aplicación seguirá siendo compatible a pesar de evolucionar.

Un **web framework** es un framework diseñado para el desarrollo de aplicaciones web a través de invocaciones a servicios web, APIs u otro tipo de recursos. Su objetivo principal debe ser automatizar partes del desarrollo web y otras actividades comunes (como el acceso a la base de datos) para que no tengan que ser implementadas una y otra vez. Pueden ser de back-end o de front-end. Algunas de sus características son:
- Sistema basado en plantillas: mecanismos para la generación automática de documentos web a partir de un lenguaje de marcas, favoreciendo la reutilización de código.
- Gestión de caché.
- Acceso a base de datos y gestión de objetos de datos: acceso a múltiples bases de datos sin tener que modificar el código fuente de la aplicación, y creación de objetos de mapeo y correspondencia con el esquema de la base de datos mediante objetos de clases o formatos tipo JSON o XML.
- Funciones de seguridad, como autenticación, autorización y  listas de acceso a las funciones de la aplicación.
- Enrutado.
- Programación asíncrona, encapsulando la dificultad de las técnicas de desarrollo de comunicación asíncrona con el servidor.
- Generación de código, como patrones arquitecturales o plantillas.
- Servicios web.
- Integración: mecanismos de integración con otros frameworks o herramientas.
Para elegir un web framework, un objetivo importante es reducir el **time-to-market**, para lo que Mozilla recomienda seguir una serie de criterios de elección:
- Curva de aprendizaje.
- Productividad.
- Potenciación del uso de buenas prácticas.
- Desempeño (tiempo de ejecución y carga del sitio web).
- Escalabilidad vertical (cambiar a un hardware más potente), horizontal (ampliar el número de servidores web y bases de datos) y geográfica (redistribuir los usuarios según su localización más cercana a un servidor).
- Soporte de caché.
- Seguridad web.
Todos los web frameworks se basan en **tecnologías Javascript**, que es el único lenguaje de programación considerable para front-end. Al final, los web frameworks permiten desarrollar documentos ricos e interactivos de forma sencilla, escalable y mantenible.

Un **micro-framework** es un framework minimalista, que ofrece un conjunto mínimo de funcionalidades necesario para el desarrollo de un producto web. En general, un micro-framework solo ofrece control y gestión de solicitudes y respuestas HTTP e integración con APIs, pero no ofrece seguridad, validación, motor de plantillas ni mapeo de objetos de acceso a datos, a menos que se añadan como extensiones.