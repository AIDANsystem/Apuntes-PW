---
title: Tema 2 - Lenguajes para la web
draft: false
tags:
---

## Lenguajes de marcado
### XML
**XML** es un formato sencillo y flexible utilizado fundamentalmente para el **intercambio de datos** en la Web. Es un estándar libre y abierto que define las reglas para la codificación de documentos en un formato basado en texto, legible tanto por la máquina como por el humano. Es la base del desarrollo de APIs, y ha propiciado el desarrollo de la web y de aplicaciones con intercambio de datos. Es utilizado por servidores (por ejemplo, para almacenar ficheros), bases de datos (por ejemplo, para devolver resultados de consultas) y servicios web.
Un documento XML presenta las siguientes características:
- Está basado en **marcas** (entre *<* y *>*) y contenido, todo ello como cadenas de caracteres.
- Un procesador analiza las marcas y estructura el contenido para pasarlo a la aplicación.
- Hay tres tipos de etiqueta: inicio (*\<tag\>*), final (*\</tag\>*) y etiquetas de elemento vacío (*\<tag /\>*).
- Un elemento es un componente que comienza y acaba con etiquetas (por ejemplo, el elemento DIV en *\<div\>contenido\</div\>*).
- Un atributo es una variable con un dato asociado que puede contenerse dentro de las etiquetas de inicio o de elemento vacío (por ejemplo, el atributo CLASS en el elemento DIV: *\<div class="miclase"\>...\</div\>*).
- Todo documento se inicia con la declaración XML, que incluye metainformación sobre el propio documento: *\<?xml version="1.0" encoding="UTF-8"?\>*.
Ejemplo de documento XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>  <!-- XML UTF-8 -->
<message private="true">                <!-- root element -->
	<from id=“alba@miempresa.es”>Alba Lopez</from>
	<to id=“Roberto@miempresa.es”>Roberto Manuel</to>
	<subject>Mañana en mi fiesta de cumpleaños!</subject>
	<content language=“spanish">
		Oye, Roberto, no te olvides de llamarme para organizar la fiesta.
	</content>
</message>
```
El elemento *message* es el **elemento raíz**, el elemento padre de todos los demás elementos del documento. Cada documento tiene uno y solo uno, y encapsula a todos los demás elementos.

Actualmente se utiliza XML Schema como lenguaje de descripción para documentos XML. Es un lenguaje que sirve para redactar un documento que define externamente la estructura de un documento XML.

XML ofrece ventajas como ser abierto y estándar, permitir representar casi cualquier tipo general de datos, ser fácil de leer y ofrecer multitud de herramientas para su procesamiento, a pesar de tener desventajas que es un formato muy voluminoso (que genera grandes ficheros, lo que puede influir negativamente en el rendimiento), que algunos datos pueden ser difíciles de encajar en un formato XML válido, y que el código Javascript para navegar por el árbol de etiquetas de XML es voluminoso y tedioso.

### HTML
**HTML** es el lenguaje de marcado basado en texto más utilizado en el front-end. Su versión recomendada actualmente es HTML 5. 

## Lenguaje de diseño CSS
**CSS** es el lenguaje principal de presentación del diseño gráfico en la Web. Junto con HTML y Javascript forma la base del desarrollo web en el front-end. Esta división permite mejorar la accesibilidad, flexibilidad, control y escalabilidad del sitio web.
Hay tres posibles métodos de aplicación de estilos:
- En línea, utilizando el atributo *style* de HTML:
```html
<body style="background-color: #FF0000;">
```
- Interno, incrustando CSS como contenido de la etiqueta *\<style ...\>* en la cabecera del documento HTML:
```html
<style type="text/css">
	body {background-color: #FF000;}
</style>
```
- Externo, vinculando el documento HTML a un fichero de estilos externo de extensión *.css*:
```html
<link rel="stylesheet" type="text/css" href="style/style.css" />
```

CSS cubre tres aspectos diferentes de estilo y maquetación:
- Estilo del texto (fuentes, colores, tipos de enumeraciones, etc.)
- Estilo de las cajas: considerando que todos los elementos de HTML son considerados como cajas con *content, padding (margen interno), border y margin (margen externo)*, permite modificarlos por separado.
- Distribución de las cajas, modificando su posición absoluta y relativa respecto a otras.

Al final, CSS define un conjunto de reglas que se aplican a un documento y modifican el modo en que este es presentado. Cada regla se compone de un **selector**, que indica los elementos HTML afectados por la regla, y un **conjunto de propiedades** que modifican el elemento. Cada modificación de una propiedad recibe el nombre de **declaración**.
```css
h1 {   /* selector */
	color: blue;    /* <------------ declaración -------|                */
	background-color: yellow;  /* <- declaración -------|- propiedades   */
	border: 1px solid black;   /* <- declaración -------|                */
}
```



##  Lenguaje de programación Javascript
**Javascript** es el lenguaje de programación del front-end predominante, mientras que en el back-end hay varias opciones como Java, Ruby o PHP (aunque este último ya está obsoleto) que ofrecen características propias que harán que se use uno u otro para un proyecto.

Javascript permite desarrollar páginas web interactivas y reactivas (los denominados sitios dinámicos). El código se escribe en scripts independientes del contenido y estructura del diseño del documento web. El código puede ser incrustado en marcas HTML o vinculado desde ficheros separados del documentos que deben ser accesibles al cliente.

Un **script** es un programa legible y modificable por el usuario, que realiza operaciones sencillas y/o de control sobre la operación de otros programas:
- Código ejecutado en tiempo de ejecución en vez de compilado, que tiene limitado el acceso a los recursos del cliente por motivos de seguridad.
- Se requiere un entorno de ejecución adecuado que interprete y ejecute las instrucciones del script.
- Puede hacer uso de un conjunto amplio de librerías.
- Generalmente, los lenguajes de scripts son lentos. Distintos motores de Javascript pueden producir distintos resultados o efectos. El rendimiento de Javascript depende de la eficiencia del motor de javascript del cliente y de la capacidad de cómputo del cliente.

Javascript es un lenguaje multiparadigma (permite programación funcional con funciones de primera clase, orientada a objetos e imperativa), con funciones de primera clase (paradigma en el que la salida de una función se puede pasar como argumento a otra sin necesidad de pasarla por una variable) y basado en prototipos (los objetos no se instancian, sino que se clonan a partir de prototipos o son programados de forma explícita por el programador).
Javascript puede incrustarse en el documento HTML y vincularse a un fichero externo en el HEAD: 
```html
<script src="miscript.js"></script>
```

```js
var genericAnimal = Object.create(null);
genericAnimal.name = 'Animal’;
genericAnimal.gender = 'female’;
genericAnimal.description = function() {
	return 'Gender: ' + this.gender + '; Name: ' + this.name;};

var cat = Object.create(genericAnimal);
cat.purr = function() {
return 'Purrrr!'; };

var colonel = Object.create(cat);
colonel.name = 'Colonel Meow’;

var puff = Object.create(cat);
puff.name = 'Puffy';
```

El **DOM (Document Object Model)** es una interfaz independiente del lenguaje y de la plataforma que permite el acceso y actualización dinámica al contenido, estructura y estilo de los documentos a los lenguajes de script. En Javascript, DOM es una API para documentos HTML y XML que proporciona una representación estructural del documento, permitiendo manipular, crear, eliminar y cambiar el código de los elementos escritos en HTML y CSS aplicando valores dinámicos. En DOM, los elementos HTML son objetos, y contiene las propiedades de los elementos, métodos para acceder a los elementos, y puede recoger los eventos para los elementos de HTML. El DOM organiza los elementos en un árbol con cuatro tipos de nodos:
- Nodo documento (página HTML completa).
- Nodo elemento.
- Nodo atributo (en las etiquetas de inicio de HTML).
- Nodo texto (dentro de los elementos).
Javascript DOM permite consultas en los elementos HTML:
```js
const elem = document.getDocumentById("one");
```
Recientemente, se han añadido consultas de selectores CSS:
```js
const first_elem = document.querySelector("li.one");
```


## Otros lenguajes de serialización
### JSON
**JSON (JavaScript Object Notation)** es un lenguaje de intercambio de datos ligero, basado en texto e independiente del lenguaje. Define un conjunto de reglas para la representación de datos estructurados. Se ha popularizado por su uso en APIs y servicios web.
```json
{
	"private": "true",
	"from": {
		“id”: "alba@miempresa.es",
		“text”: “Alba Lopez”
	},
	"to": {
		“id”: "Roberto@miempresa.es",
		“text”: “Roberto Manuel”
	},
	"subject": "Mañana en mi fiesta de cumpleaños!",
	“content": {
		"language": “spanish",
		"text": "Oye, Roberto, no te olvides de llamarme para organizar la fiesta."
	}
}
```

### YAML
**YAML (YAML Ain't Markup Language)** es un lenguaje de serialización legible por el humano utilizado en general para ficheros de configuración. Es orientado a líneas, no ofrece comandos (no es ejecutable), no es un lenguaje de etiquetas (como XML) y utiliza una sintaxis mínima, más parecida al estilo de formato de Python.