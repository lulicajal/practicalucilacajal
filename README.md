### *Salesforce Consultant*
#  `Evalución práctica` - Lucila Belén Cajal


# *Ejercicio 2*

### 1. ¿Qué es un servidor HTTP?

Un servidor HTTP es un programa informático (o software) que procesa una aplicación del lado del servidor realizando conexiones con el cliente,  logrando generar así una respuesta en cualquier lenguaje o aplicación del lado del cliente. El código recibido por el cliente es “traducido” por un navegador web. Para la transmisión de todos estos datos suele utilizarse un protocolo(Un protocolo es un conjunto de reglas para la comunicación entre dos computadoras.). Generalmente se usa el protocolo HTTP (de sus siglas en inglés, significa “Hipertext Transfer Protocol”.). 

(Al otro lado del canal de comunicación, está el servidor, el cual "sirve" los datos que ha pedido el cliente)
 
 
### 2. Qué son los verbos HTTP? Mencionar los más conocidos

Los verbos HTTP son los métodos de petición utilizados en HTTP. Estos indican qué acción se quiere llevar a cabo sobre un recurso determinado. 

Los más conocidos son: 

- GET 
- HEAD
- POST
- PUT
- DELETE
- CONNECT 
- OPTIONS
- TRACE
- PATCH 

### 3. ¿Qué es un request y un response en una comunicación HTTP? ¿Qué son los headers?


En una comunicación HTTP hay dos tipos de mensajes: la solicitud y la respuesta. Cuando un navegador abre una conexión a un servidor y realiza una solicitud (request). El servidor procesa la solicitud del cliente y devuelve una respuesta (response).	

Una *petición al servidor (request)* consta de una línea de petición que contiene alguna información básica sobre la petición (utilizando un verbo HTTP) y de diversas líneas que constituyen los headers.


Y una *respuesta del servidor (response)* consta de una línea de status que contiene alguna información básica sobre la respuesta del servidor, de diversas líneas que constituyen los headers y finalmente una línea en blanco seguida de la respuesta del servidor, normalmente un código HTML extenso. 

Los headers son los parámetros que se envían en una petición o respuesta HTTP al cliente o al servidor para proporcionar información esencial sobre la transacción en curso.


### 4.	¿Qué es un queryString? (En el contexto de una url)

Es un término informático utilizado para hacer referencia a la parte de una URL donde los datos se pasan a una aplicación web y/o a una base de datos back-end.
Se utiliza porque el protocolo HTTP no tiene estado por diseño. Para que un sitio web sea algo más que un folleto, debe mantener el estado (almacenar datos).


### 5.¿Qué es el responseCode? ¿Qué significado tiene los posibles valores devueltos?

El *responseCode (código de respuesta)* es el responsable de indicar si se ha completado satisfactoriamente una solicitud HTTP específica.

Los posibles valores de respuesta podrían agruparse en: 



<h3 id="Respuestas_informativas">Respuestas informativas</h3> 

Indican el estado de la solicitud, y en caso de corresponder, si se debe realizar una siguiente acción. Pueden ser las siguientes: 

<dl>
 <li><code>100 Continue</code>
 <dd>Esta respuesta provisional indica que todo hasta ahora está bien y que el cliente debe continuar con la solicitud o ignorarla si ya está terminada.</dd>
 <li><code>101 Switching Protocol</code>
 <dd>Este código se envía en respuesta a un encabezado de solicitud {{HTTPHeader("Upgrade")}} por el cliente e indica que el servidor acepta el cambio de protocolo propuesto por el agente de usuario.</dd>
 <li><code>102 Processing</code>
 <dd>Este código indica que el servidor ha recibido la solicitud y aún se encuentra procesandola, por lo que no hay respuesta disponible.</dd>
  <li><code>103 Early Hints</code>
 <dd>Este código de estado está pensado principalmente para ser usado con el encabezado {{HTTPHeader("Link")}}, permitiendo que el agente de usuario empiece a pre-cargar recursos mientras el servidor prepara una respuesta.</dd>
</dl>

<h3 id="Respuestas_satisfactorias">Respuestas satisfactorias</h3>

Indica que la petición fue recibida correctamente, entendida y aceptada.

Tipos de verbos HTTP que utilizan generalmente:

`GET`: El recurso se ha obtenido y se transmite en el cuerpo del mensaje.</li>

`HEAD`: Los encabezados de entidad están en el cuerpo del mensaje.

`PUT`: El recurso que describe el resultado de la acción se transmite en el cuerpo del mensaje.</li>

`TRACE`: El cuerpo del mensaje contiene el mensaje de solicitud recibido por el servidor.<span class="hidden"> </span><span class="hidden"> </span><span class="hidden"> </span><span class="hidden"> </span></li>

Las respuestas pueden ser las siguientes:

<dl>
  <li><code>200 OK</code>
 <dd>La solicitud ha tenido éxito. El significado de un éxito varía dependiendo del método HTTP:</dd>
  <li><code>201 Created</code>
 <dd>La solicitud ha tenido éxito y se ha creado un nuevo recurso como resultado de ello. Ésta es típicamente la respuesta enviada después de una petición PUT.</dd>
 <li><code>202 Accepted</code>
 <dd>La solicitud se ha recibido, pero aún no se ha actuado. Es una petición "sin compromiso", lo que significa que no hay manera en HTTP que permite enviar una respuesta asíncrona que indique el resultado del procesamiento de la solicitud. Está pensado para los casos en que otro proceso o servidor maneja la solicitud, o para el procesamiento por lotes.</dd>
 <li><code>203 Non-Authoritative Information</code>
 <dd>La petición se ha completado con éxito, pero su contenido no se ha obtenido de la fuente originalmente solicitada, sino que se recoge de una copia local o de un tercero. Excepto esta condición, se debe preferir una respuesta de 200 OK en lugar de esta respuesta.</dd>
  <li><code>204 No Content</code>
 <dd>La petición se ha completado con éxito pero su respuesta no tiene ningún contenido, aunque los encabezados pueden ser útiles. El agente de usuario puede actualizar sus encabezados en caché para este recurso con los nuevos valores.</dd>
 <li><code>205 Reset Content</code>
 <dd>La petición se ha completado con éxito, pero su respuesta no tiene contenidos y además, el agente de usuario tiene que inicializar la página desde la que se realizó la petición, este código es útil por ejemplo para páginas con formularios cuyo contenido debe borrarse después de que el usuario lo envíe.</dd>
 <li><code>206 Partial Content</code>
 <dd>La petición servirá parcialmente el contenido solicitado. Esta característica es utilizada por herramientas de descarga como wget para continuar la transferencia de descargas anteriormente interrumpidas, o para dividir una descarga y procesar las partes simultáneamente.</dd>
 <li><code>207 Multi-Status</code>
 <dd>Una respuesta Multi-Estado transmite información sobre varios recursos en situaciones en las que varios códigos de estado podrían ser apropiados. El cuerpo de la petición es un mensaje XML.</dd>
 <li><code>208 Multi-Status</code>
 <dd>El listado de elementos DAV ya se notificó previamente, por lo que no se van a volver a listar.</dd>
 <li><code>226 IM Used</code>
 <dd>El servidor ha cumplido una petición <code>GET</code> para el recurso y la respuesta es una representación del resultado de una o más manipulaciones de instancia aplicadas a la instancia actual.</dd>
</dl>

<h3 id="Redirecciones">Redirecciones</h3>

<dl>
 <li><code>300 Multiple Choice</code>
 <dd>Esta solicitud tiene más de una posible respuesta. User-Agent o el usuario debe escoger uno de ellos. No hay forma estandarizada de seleccionar una de las respuestas.</dd>
 <li><code>301 Moved Permanently</code>
 <dd>Este código de respuesta significa que la URI  del recurso solicitado ha sido cambiado. Probablemente una nueva URI sea devuelta en la respuesta.</dd>
 <li><code>302 Found</code>
 <dd>Este código de respuesta significa que el recurso de la URI solicitada ha sido cambiado temporalmente. Nuevos cambios en la URI serán agregados en el futuro. Por lo tanto, la misma URI debe ser usada por el cliente en futuras solicitudes.</dd>
 <dd></dd>
 <li><code>303 See Other</code> 
 <dd>El servidor envía esta respuesta para dirigir al cliente a un nuevo recurso solicitado a otra dirección usando una petición GET.</dd>
 <li><code>304 Not Modified</code>
 <dd>Esta es usada para propósitos de "caché". Le indica al cliente que la respuesta no ha sido modificada. Entonces, el cliente puede continuar usando la misma versión almacenada en su caché.</dd>
 <li><code>305 Use Proxy</code> 
 <dd>Fue definida en una versión previa de la especificación del protocolo HTTP para indicar que una respuesta solicitada debe ser accedida desde un proxy. Ha quedado obsoleta debido a preocupaciones de seguridad correspondientes a la configuración de un proxy.</dd>
 <li><code>306 unused</code>
 <dd>Este código de respuesta ya no es usado más. Actualmente se encuentra reservado. Fue usado en previas versiones de la especificación HTTP1.1.</dd>
 <li><code>307 Temporary Redirect</code>
 <dd>El servidor envía esta respuesta para dirigir al cliente a obtener el recurso solicitado a otra URI con el mismo método que se usó la petición anterior. Tiene la misma semántica que el código de respuesta HTTP <code>302 Found</code>, con la excepción de que el agente usuario <em>no debe</em> cambiar el método HTTP usado: si un <code>POST</code> fue usado en la primera petición, otro <code>POST</code> debe ser usado en la segunda petición.</dd>
</dl>

<dl>
 <li><code>308 Permanent Redirect</code>
 <dd>Significa que el recurso ahora se encuentra permanentemente en otra URI, especificada por la respuesta de encabezado HTTP <code>Location:</code>. Tiene la misma semántica que el código de respuesta HTTP <code>301 Moved Permanently</code>, con la excepción de que el agente usuario <em>no debe</em> cambiar el método HTTP usado: si un <code>POST</code> fue usado en la primera petición, otro <code>POST</code> debe ser usado en la segunda petición.</dd>
</dl>

<h3 id="Errores_de_cliente">Errores de cliente</h3>

<dl>
 <li><code>400 Bad Request</code>
 <dd>Esta respuesta significa que el servidor no pudo interpretar la solicitud dada una sintaxis inválida.</dd>
 <li><code>401 Unauthorized</code> 
 <dd>Es necesario autenticar para obtener la respuesta solicitada. Esta es similar a 403, pero en este caso, la autenticación es posible.</dd>
 <li><code>402 Payment Required</code>
 <dd>Este código de respuesta está reservado para futuros usos. El objetivo inicial de crear este código fue para ser utilizado en sistemas digitales de pagos. Sin embargo, no está siendo usado actualmente.</dd>
 <li><code>403 Forbidden</code>
 <dd>El cliente no posee los permisos necesarios para cierto contenido, por lo que el servidor está rechazando otorgar una respuesta apropiada.</dd>
 <li><code>404 Not Found</code> 
 <dd>El servidor no pudo encontrar el contenido solicitado. Este código de respuesta es uno de los más famosos dada su alta ocurrencia en la web.</dd>
 <li><code>405 Method Not Allowed</code> 
 <dd>El método solicitado es conocido por el servidor pero ha sido deshabilitado y no puede ser utilizado. Los dos métodos obligatorios, <code>GET</code> y <code>HEAD</code>, nunca deben ser deshabilitados y no deberían retornar este código de error.</dd>
 <li><code>406 Not Acceptable</code> 
 <dd>Esta respuesta es enviada cuando el servidor, después de aplicar una <a href="/en-US/docs/HTTP/Content_negotiation#Server-driven_negotiation">negociación de contenido servidor-impulsado</a>, no encuentra ningún contenido seguido por la criteria dada por el usuario.</dd>
 <li><code>407 Proxy Authentication Required</code> 
 <dd>Esto es similar al código 401, pero la autenticación debe estar hecha a partir de un proxy.</dd>
 <li><code>408 Request Timeout</code>  
 <dd>Esta respuesta es enviada en una conexión inactiva en algunos servidores, incluso sin alguna petición previa por el cliente. Significa que el servidor quiere desconectar esta conexión sin usar. Esta respuesta es muy usada desde algunos navegadores, como Chrome, Firefox 27+, o IE9, usa mecanismos de pre-conexión HTTP para acelerar la navegación. También hay que tener en cuenta que algunos servidores simplemente desconecta la conexión sin enviar este mensaje.</dd>
 <li><code>409 Conflict</code> 
 <dd>Esta respuesta puede ser enviada cuando una petición tiene conflicto con el estado actual del servidor.</dd>
 <li><code>410 Gone</code>
 <dd>Esta respuesta puede ser enviada cuando el contenido solicitado ha sido borrado del servidor.</dd>
 <li><code>411 Length Required</code> 
 <dd>El servidor rechaza la petición porque el campo de encabezado <code>Content-Length</code> no esta definido y el servidor lo requiere.</dd>
 <li><code>412 Precondition Failed</code>  
 <dd>El cliente ha indicado pre-condiciones en sus encabezados la cual el servidor no cumple.</dd>
 <li><code>413 Payload Too Large</code>   
 <dd>La entidad de petición es más larga que los límites definidos por el servidor; el servidor puede cerrar la conexión o retornar un campo de encabezado <code>Retry-After</code>.</dd>
 <li><code>414 URI Too Long</code>    
 <dd>La URI solicitada por el cliente es más larga de lo que el servidor está dispuesto a interpretar.</dd>
 <li><code>415 Unsupported Media Type</code>  
 <dd>El formato multimedia de los datos solicitados no está soportado por el servidor, por lo cual el servidor rechaza la solicitud.</dd>
 <li><code>416 Requested Range Not Satisfiable</code>  
 <dd>El rango especificado por el campo de encabezado <code>Range</code> en la solicitud no cumple; es posible que el rango está fuera del tamaño de los datos objetivo del URI.</dd>
 <li><code>417 Expectation Failed</code>  
 <dd>Significa que la expectativa indicada por el campo de encabezado <code>Expect</code> solicitada no puede ser cumplida por el servidor.</dd>
 <li><code>418 I'm a teapot</code>  
 <dd>El servidor se rehúsa a intentar hacer café con una tetera.</dd>
 <li><code>421 Misdirected Request</code> 
 <dd>La petición fue dirigida a un servidor que no es capaz de producir una respuesta. Esto puede ser enviado por un servidor que no está configurado para producir respuestas por la combinación del esquema y la autoridad que están incluidos en la URI solicitada</dd>
 <li><code>422 Unprocessable Entity</code>  
 <dd>La petición estaba bien formada pero no se pudo seguir debido a errores de semántica.</dd>
 <li><code>423 Locked</code>  
 <dd>El recurso que está siendo accedido está bloqueado.</dd>
 <li><code>424 Failed Dependency</code>   
 <dd>La petición falló debido a una falla de una petición previa.</dd>
  <li><code>426 Upgrade Required</code> 
 <dd>El servidor se rehúsa a aplicar la solicitud usando el protocolo actual pero puede estar dispuesto a hacerlo después que el cliente se actualice a un protocolo diferente. El servidor envía un encabezado <font face="consolas, Liberation Mono, courier, monospace"><span style="background-color: rgba(220, 220, 220, 0.5);">Upgrade</span></font> en una respuesta para indicar los protocolos requeridos.</dd>
  <li><code>428 Precondition Required</code> 
 <dd>El servidor origen requiere que la solicitud sea condicional. Tiene la intención de prevenir problemas de 'actualización perdida', donde un cliente OBTIENE un estado del recurso, lo modifica, y lo PONE devuelta al servidor, cuando mientras un tercero ha modificado el estado del servidor, llevando a un conflicto.</dd>
  <li><code>429 Too Many Requests</code>  
 <dd>El usuario ha enviado demasiadas solicitudes en un periodo de tiempo dado.</dd>
  <li><code>431 Request Header Fields Too Large</code>
 <dd>El servidor no está dispuesto a procesar la solicitud porque los campos de encabezado son demasiado largos. La solicitud PUEDE volver a subirse después de reducir el tamaño de los campos de encabezado solicitados.</dd>
  <li><code>451 Unavailable For Legal Reasons</code> 
 <dd>El usuario solicita un recurso ilegal, como alguna página web censurada por algún gobierno.</dd>
</dl>

<h3 id="Errores_de_servidor">Errores de servidor</h3>

<dl>
  <li><code>500 Internal Server Error</code>  
 <dd>El servidor ha encontrado una situación que no sabe cómo manejarla.</dd>
  <li><code>501 Not Implemented</code> 
 <dd>El método solicitado no está soportado por el servidor y no puede ser manejado. Los únicos métodos que los servidores requieren soporte (y por lo tanto no deben retornar este código) son <code>GET</code> y <code>HEAD</code>.</dd>
  <li><code>502 Bad Gateway</code> 
 <dd>Esta respuesta de error significa que el servidor, mientras trabaja como una puerta de enlace para obtener una respuesta necesaria para manejar la petición, obtuvo una respuesta inválida.</dd>
  <li><code>503 Service Unavailable</code> 
 <dd>El servidor no está listo para manejar la petición. Causas comunes puede ser que el servidor está caído por mantenimiento o está sobrecargado. Hay que tomar en cuenta que junto con esta respuesta, una página usuario-amigable explicando el problema debe ser enviada. Estas respuestas deben ser usadas para condiciones temporales y el encabezado HTTP <code>Retry-After:</code> debería, si es posible, contener el tiempo estimado antes de la recuperación del servicio. El webmaster debe también cuidar los encabezados relacionados al caché que son enviados junto a esta respuesta, ya que estas respuestas de condición temporal deben usualmente no estar en el caché.</dd>
  <li><code>504 Gateway Timeout</code>  
 <dd>Esta respuesta de error es dada cuando el servidor está actuando como una puerta de enlace y no puede obtener una respuesta a tiempo.</dd>
  <li><code>505 HTTP Version Not Supported</code> 
 <dd>La versión de HTTP usada en la petición no está soportada por el servidor.</dd>
  <li><code>506 Variant Also Negotiates</code>
 <dd>El servidor tiene un error de configuración interna: negociación de contenido transparente para la petición resulta en una referencia circular.</dd>
  <li><code>507 Insufficient Storage</code> 
 <dd>El servidor tiene un error de configuración interna: la variable de recurso escogida está configurada para acoplar la negociación de contenido transparente misma, y no es por lo tanto un punto final adecuado para el proceso de negociación.</dd>
  <li><code>508 Loop Detected</code>  
 <dd>El servidor detectó un ciclo infinito mientras procesaba la solicitud.</dd>
  <li><code>510 Not Extended</code>   
 <dd>Extensiones adicionales para la solicitud son requeridas para que el servidor las cumpla.</dd>
  <li><code>511 Network Authentication Required</code>  
 <dd>El código de estado 511 indica que el cliente necesita autenticar para obtener acceso a la red.</dd>
</dl>



### 6.	¿Cómo se envía la data en un Get y cómo en un POST? 



En GET la data de la petición se envía como parte del enlace, añadiendo así los datos codificados a la URI (Uniform Resource Identifier: es una cadena de caracteres que identifica un recurso en Internet) definida. El mismo está restringido a código ASCII. 
Cuenta con una limitación en cuanta a la data que se puede enviar porque los enlaces tienen límites de caracteres.
Por el contrario, el método POST  incluye los datos de la petición directamente sobre el cuerpo de manera interna y no tan expuesta en comparación al método GET. 

El proceso de someter data para ambos métodos comienza de la misma manera - el buscador (browser) construye un set de data del formulario y la codifica según los atributos dados.
En el método GET la información es visible en la URL lo que aumenta las vulnerabilidades y el riesgo de hacking. Por el contrario, el método POST no muestra variables en la URL y también se pueden utilizar múltiples técnicas de codificación, lo que lo hace resistente.
Los datos del método GET se pueden almacenar en caché, mientras que los datos del método POST no.

Además, se utiliza el método GET para recuperar los datos. Por el contrario, el método POST se utiliza para almacenar o actualizar los datos.


### 7.	¿Qué verbo http utiliza el navegador cuando accedemos a una página?

El verbo HTTP que utiliza el navegador, generalmente, cuando accedemos a una página es el verbo GET.

### 8.	Explicar brevemente qué son las estructuras de datos JSON y XML dando ejemplo de estructuras posibles.

JSON es un lenguaje de modelador que está basado en un subconjunto del lenguaje de programación JavaScript de datos que está construido por una colección de pares de nombre y valor o por una lista ordenada de valores. 

XML es un lenguaje cuyo formato está basado en texto para representar información estructurada: datos, documentos, configuración, etc..

JSON usa una notación simple, mientras que el XML usa una estructura de tags personalizadas para representar los objetos.
El formato XML soporta diferentes tipos de datos, entre ellos: imágenes y gráficos, lo que no es posible transmitir en el formato JSON, dado que este último solo ofrece soporte a números y textos.


EJEMPLO DE JERARQUIZACIÓN DE DATOS EN XML: 

```
<Person> 

  <person> 

      <name>Ford Prefect</name> 

      <gender>male</gender> 

  </person> 

  <person> 

      <name>Arthur Dent</name> 

      <gender>male</gender> 

  </person> 

  <person> 

      <name>Tricia McMillan</name> 

      <gender>female</gender> 

  </person>

</Person>
```

MISMO EJEMPLO EN JSON 

```
{ 

>"persons": [ 
      { 
            "name": "Ford Prefect", 
            "gender": "male" 
      }, 
      { 
            "name": "Arthur Dent", 
            "gender": "male" 
      }, 
      { 
            "name": "Tricia McMillan", 
            "gender": "female" 
      } 
  ] 
}
```



### 9.	Explicar brevemente el estándar SOAP

SOAP es un estándar basado en XML para la transmisión de mensajes en HTTP y otros protocolos de Internet. Es un protocolo ligero para el intercambio de información en un entorno descentralizado y distribuido. Se basa en XML y consta de tres partes: 
- Un sobre que define una infraestructura para describir el contenido del mensaje y cómo procesarlo. 
- Un conjunto de normas de codificación para expresar instancias de tipos de datos definidos por la aplicación. 
- Una convención para representar llamadas y respuestas a procedimiento remoto. 

SOAP permite el enlace y la utilización de servicios Web encontrados definiendo una ruta de mensaje para el direccionamiento de mensajes.


### 10.	Explicar brevemente el estándar REST Full


Es un servicio que funciona como un estándar para compartir información, en un sistema de doble vía: Consulta y Respuesta (Request => Response).

Es considerada una técnica de arquitectura de software, es decir, un conjunto de principios y patrones de comunicación que ayudan a crear una forma de pensar y construir las APIs. Este tipo de arquitectura se define por un conjunto de restricciones entre los elementos, componentes, conectores y datos usados.

Las respuestas obtenidas suelen ser en formato JSON o en estructuras XML. 


### 11.	¿Qué son los headers en un request? ¿Para qué se utiliza el key Content-type en un header?



Los headers en un request son los parámetros que se envían en una petición o respuesta HTTP al cliente o al servidor para proporcionar información esencial sobre la transacción en curso.

El key Content Type en un header se utiliza para informar el tipo de contenido que será retornado o enviado.
En un request, es utilizado para indicar el tipo de medio del recurso. El tipo de medio es una cadena enviada junto con el archivo que indica el formato del archivo. Por ejemplo, para un archivo de imagen, su tipo de medio será imagen/png o imagen/jpg, etc. 
En un response, informa al cliente sobre el tipo de contenido devuelto. El navegador llega a conocer el tipo de contenido que tiene que cargar en la máquina.


***

# *Ejercicio 3*

En el repositorio, 3 imágenes identificadas como "Ejercicio 3", las cuales muestran los screenshoot de cada resolución. 

La diferencia entre las llamadas 1 y 3: la última a pesar de ser exactamente igual a la primera, el resultado fue obtenido más rápido. Puede verse reflejado en la parte de *TIME*.

***
# *Ejercicio 4*

Link de Trailhead: https://trailblazer.me/id/lcajal1


***


# *Ejercicio 5*


Explicar que son conceptualmente, qué datos almacenan en forma estándar y cómo se relacionan el resto (algunos no se relacionan entre sí) cada uno de los siguientes objetos de Salesforce:

### •	Lead: 

El lead es un cliente potencial que demostró interés en un producto o servicio ofrecido por la marca por medio de la interacción con contenidos y otros materiales.
Se almacena su información de contacto en la base de datos. 


### •	Account:

Account es el campo que almacena información sobre clientes. Hay dos tipos de cuentas. Las cuentas comerciales que almacenan información sobre las empresas, y las cuentas personales que almacenan información sobre personas individuales.

### •	Contact:

Contact es el campo que almacena la información de contacto de los clientes. 

### •	Opportunity:

Esta función nos muestra los acuerdos en curso. Los registros realizan un seguimiento de detalles acerca de acuerdos, incluyendo para qué cuentas son, quiénes son las personas implicadas y las cantidades de las ventas potenciales.



### •	Product:

Contiene información para el seguimiento de lo que está comercializando. 
Este campo muestra: 

a.	Activo: Si la entrada de la lista de precios (producto y precio de la lista) está activa 

b.	Creado por: Usuario que creó el producto.

c.	Fecha: Fecha de cierre de un producto de oportunidad concreto.

d.	Descuento: Descuento del producto como porcentaje.

e.	Autor de la última modificación: El último usuario que ha realizado una modificación en los campos del producto de oportunidad.

g.	Descripción de partida: Texto para distinguir este producto de oportunidad de otro.

i.	Precio de la lista:Precio del producto dentro de la lista de precios, incluida la divisa.

k.	Oportunidad:	Nombre de la oportunidad para este producto de oportunidad.

m.	Producto:	Elemento incluido en la lista relacionada Productos de una oportunidad.

o.	Cantidad:	Número de unidades del producto de la oportunidad.

q.	Precio de venta:	Precio de los productos en el producto de oportunidad. En un producto de oportunidad sin una programación relacionada, el precio de venta es modificable. 

s.	Subtotal:	Diferencia entre el precio estándar y el precio de descuento. Cantidades de divisa convertida si la divisa de la oportunidad es diferente de la divisa del usuario.

u.	Precio total:	Suma de todas las cantidades de producto para un producto de oportunidad. 


### •	PriceBook:

Es una lista de productos y sus precios asociados.

De manera estándar se muestra  una lista maestra de todos los productos con sus precios predeterminados. Enumera automáticamente todos los productos y precios estándar.

### •	Quote:

Representan los precios propuestos de los productos y servicios de su empresa. Usted crea una cotización a partir de una Opportunity  y sus Products.

### •	Asset:

Representan los productos específicos que sus clientes han comprado. 
Se utiliza para almacenar información sobre los productos de sus clientes.

### •	Case:

Es una pregunta, un comentario o un problema de un cliente. Los agentes del servicio de atención al cliente pueden revisar casos para ver cómo pueden ofrecer un mejor servicio. Los representantes de ventas utilizan casos para ver cómo afectan al proceso de ventas.

De manera estándar se recopilan casos desde los formularios de contacto  preferidos por los clientes. 

### •	Article:

Son documentos de información. 
Los artículos pueden incluir información sobre procesos, cómo restablecer su producto a sus valores predeterminados o preguntas más frecuentes como cuánto almacenamiento admite su producto.

---

#### A continuación se adjunta un pequeño diagrama para comprender la relación entre estos objetos


 ![Diagrama](https://github.com/lulicajal/practicalucilacajal/blob/main/Ejercicio5%20final.png)




# *Ejercicio 6*



***
## *Soluciones de Salesforce*

***

### A.	¿Qué es Salesforce?

Salesforce es un software de gestión de relaciones con clientes basada en una nube. Una plataforma CRM integrada que brinda una vista compartida de todos los departamentos de una empresa y de cada cliente.

### B.	¿Qué es Sales Cloud?

Sales Cloud es una plataforma de ventas de Salesforce, que da seguimiento al proceso de ventas, desde perfilar prospectos, hacer el contacto inicial hasta el final de la compra.

### C.	¿Qué es Service Cloud?

Service Cloud es la plataforma de servicios de Salesforce que se concentra en empresas enfocadas en productos tipo servicio, diseñado para mejorar la satisfacción del cliente. 

### D.	¿Qué es Health Cloud?

Health Cloud es una plataforma de Salesforce, diseñada para permitir una conversación personalizada entre los paciente y las entidades sanitarias asociadas. No solo es beneficioso para los equipos de atención médica, sino que también beneficia a los pacientes al establecer comunicaciones digitales con su equipo de atención.

### E.	¿Qué es Marketing Cloud?

Marketing Cloud es la plataforma de Salesforce que sirve para crear y automatizar campañas de marketing. Orientada al marketing de empresas hacia clientes finales.
Funcionalidades de Salesforce

***
## *Funcionalidades de Salesforce*

***

### A.	¿Qué es un RecordType?

Los RecordTypes en Salesforce son los que permiten definir diferentes Business Process, Pages Layouts y Picklist Values en un determinado objeto. 
Así mismo, también ayudan a mostrar distintos tipos de información según el perfil del usuario. 
Un Record Type se puede utilizar cuando un objeto en Salesforce es usado para multiples propósitos, y debe mostrar diferente información en su respectivo Page Layout.

### B.	¿Qué es un ReportType?

Los ReportType son listas de datos generados en función de criterios predefinidos. Se pueden mostrar en filas o columnas y ser públicos, compartidos, ocultos y de solo lectura o con acceso de escritura. Su función es facilitar la comprensión de los datos dentro del sistema. Con esos datos, una empresa puede tomar decisiones informadas sobre qué nuevos productos o servicios crear y cómo comunicarse con sus clientes de manera más efectiva.
Hay cuatro tipos de ReportType que pueden ser creados en Salesforce: Tabular, Matrix, Summary y Joined.  El tipo depende de qué datos y en qué formato quiero mostrar.

### C.	¿Qué es un Page Layout?

PageLayout es el control del diseño de la página y la organización de botones, campos, s-controls, Visualforce, enlaces personalizados y listas relacionadas en páginas de registros de objetos. También ayudan a determinar qué campos son visibles, de solo lectura y obligatorios.
Se utiliza para personalizar el contenido de las páginas de registro de los usuarios.

### D.	¿Qué es un Compact Layout?

Un Compact Layout muestra los campos clave de un registro en la aplicación móvil Salesforce, Lightning Experience y en las integraciones de Outlook y Gmail.
Se utiliza para personalizar los campos que se visualizan en las aplicaciones nombradas anteriormente.

### E.	¿Qué es un Perfil?

Los perfiles en Salesforce son un grupo de configuraciones y permisos que definen a qué puede acceder un usuario en Salesforce Lightning. Según la función laboral del usuario, los administradores de Salesforce pueden asignar a los usuarios un perfil que incluye todas las pestañas, registros y acceso a la página que necesitan.

### F.	¿Qué es un Rol?

Un rol es un acceso a nivel de registro en Salesforce que define el acceso de visibilidad de un usuario. Los roles se pueden usar para especificar los niveles de acceso que un usuario puede tener a los datos de la organización en Salesforce. Básicamente, define lo que un usuario puede ver en la organización de Salesforce.

### G.	¿Qué es un Validation Rule?

Un Validation Rule es la funcionalidad que verifica que los datos que un usuario ingresa en un registro cumplen con los estándares anteriormente especificados para ese mismo registro. 
Los Validation Rules pueden contener una fórmula o expresión que evalúa los datos en uno o más campos y devuelve un valor de "Verdadero" o "Falso". También pueden incluir un mensaje de error para mostrar al usuario cuando la regla devuelve un valor de "Verdadero" debido a un valor no válido.

### H.	¿Qué diferencia hay entre una relación Master Detail y Lookup?

La diferencia entre ambos es que: Lookup no tiene relación con otros registros. No depende de ningún otro objeto, mientras que una relación Master Detail tiene una asociación con otros registros. Por otro lado, Lookup es solo una referencia, puede estar incluso en blanco o NULL.

### I.	¿Qué es un Sandbox?

Un Sandbox es un entorno de prueba que proporciona una forma de copiar y crear metadatos desde su instancia de producción: es un entorno separado donde puede realizar pruebas con datos (registros de Salesforce), incluidas cuentas, contactos y clientes potenciales.

### J.	¿Qué es un ChangeSet?

Un ChangeSet es una funcionalidad de Salesforce destinada a enviar personalizaciones de un entorno de Salesforce a otro. Por ejemplo, se pueden crear y probar nuevos objetos en una organización Sandbox y luego enviarlos a su organización de producción mediante un ChangeSet.


### K.	¿Para qué sirve el import Wizard de Salesforce?

El Import Wizard es una funcionalidad de Salesforce que sirve para facilitar la importación de datos de muchos objetos estándar de Salesforce, incluidas cuentas, contactos, clientes potenciales, soluciones, y cuentas personales. También puede importar datos de objetos personalizados. Puede importar hasta 50.000 registros a la vez.

### L.	¿Para qué sirve la funcionalidad Web to Lead?

La funcionalidad Web to Lead es la que permite crear formularios web para potenciales clientes y así capturar información de los visitantes del sitio web. Esa información se almacena de manera automática en nuevos registros y puede ser utilizada luego en técnicas de marketing. 

### M.	¿Para qué sirve la funcionalidad Web to Case?

La funcionalidad Web to Case sirve para recopilar consultas de Soporte y convertirlas automáticamente en casos a través de formularios personalizables enviados por el mismo cliente en el sitio web. Ayudan a acelerar las respuestas a los clientes, mejorando la productividad del equipo de soporte. 

### N.	¿Para qué sirve la funcionalidad Omnichannel?

La funcionalidad Omnichannel es  una herramienta de Ventas y Soporte, que envía trabajo a los usuarios en tiempo real. Su objetivo es hacer llegar el trabajo adecuado a la persona adecuada para resolverlo.
Admite clientes potenciales, casos, chats, videollamadas SOS, publicaciones en redes sociales, pedidos y objetos personalizados.

### O.	¿Para qué sirve la funcionalidad Chatter?

La funcionalidad Chatter en Salesforce es una aplicación de colaboración en tiempo real que permite a sus usuarios trabajar juntos, comunicarse y compartir información. 
Permite a los distintos usuarios colaborar en oportunidades de ventas, casos de servicio, campañas y proyectos con aplicaciones integradas y acciones personalizadas.

***

## *Conceptos generales*

***

### A.	¿Qué significa SaaS?

SaaS sigficina Software as a Service. Es un modelo de software basado en la nube en el que el proveedor de la nube desarrolla y mantiene el software de las aplicaciones en la nube, proporciona actualizaciones automáticas del mismo y lo pone a disposición de sus clientes a través de Internet.

### B.	¿Salesforce es Saas?

Teniendo en cuenta la definición dada en el punto anterior, se afirma que efectivamente Salesforce es SaaS. 

### C.	¿Qué significa que una solución sea Cloud?

Significa que toda solución o software que pueda utilizar no estará almacenado en mi ordenador ni en mi servidor, sino que estará instalado en Cloud.
Cloud es el nombre que se le da a una red de servidores conectados entre sí para permitir la entrega de productos, servicios y soluciones comerciales a diferentes regiones a través de Internet.

### D.	¿Qué significa que una solución sea On-Premise?

Significa que la solución o software o aplicación que utilice estará instalada en mis servidores u ordenadores. 

### E.	¿Qué es un pipeline de ventas?

Un pipeline de ventas es el proceso de actividades y estrategias que necesita un vendedor para acelerar el ciclo de ventas, transformando clientes potenciales (aquellos que acaban de conocer tu marca o servicio) en clientes efectivos. 

### F.	¿Qué es un funnel de ventas?

Un funnel de ventas es el esquema que representa las etapas del proceso que pasa un usuario hasta convertirse en cliente.

### G.	¿Qué significa Customer Experience?

Customer Experience significa “Experiencia del Cliente”, así mismo definimos que son las percepciones de un cliente después de interactuar racional, física, emocional y/o psicológicamente con cualquier parte de una empresa.

## H.	¿Qué significa omnicanalidad?

La omnicanalidad es la estrategia de comunicación utilizada para estar en contacto con los clientes a través de diferentes canales (email, redes sociales, sitio web, etc.). El uso de los diferentes canales debe hacerse bajo una misma estrategia para llegar al consumidor en el momento indicado.

### I.	¿Qué significa que un negocio sea B2B?¿Qué significa que un negocio sea B2C?¿Qué es un KPI?

B2B significa Business to Business. Que un negocio sea B2B significa que se está realizando una transacción comercial entre empresas. 

B2C significa Business to Consumer. Que un negocio sea B2C significa que se está realizando una transacción comercial desde la empresa directamente al consumidor final. 

KPI significa Key Performance Indicator, y es un indicador/medidor de desempeño o rendimiento. 
Con estas métricas, el directivo de una empresa accede a información que le permite tomar decisiones basadas en datos objetivos y claros sobre cómo va el rendimiento de sus proyectos en un tiempo determinado. Utilizar KPI incluye poner metas que te indiquen el nivel de rendimiento al que aspiras, y comparar constantemente el progreso con la meta trazada.

### J.	¿Qué es una API y en qué se diferencia de una Rest API?

API significa Interfaz de Programación de Aplicaciones y presenta las distintas funciones y reglas que permiten la interacción y comunicación entre aplicaciones. 
La API es un conjunto general de protocolos y se implementa sobre el software para ayudarlo a interactuar con algún otro software. Y en cambio una Rest API solo está orientado a aplicaciones web. En esta última se toma información dada por el servidor y se prosigue de manera independiente a lo que el cliente desee, y se ocupa principalmente de solicitudes y respuestas HTTP.

### K.	¿Qué es un Proceso Batch?

Un proceso batch se encarga de ejecutar de forma automatizada una serie de tareas, ejecutando para ello un archivo en formato .bat. Este tipo de archivos de texto contienen una serie de comandos encargados de ejecutar tareas de forma secuencial.

### L.	¿Qué es Kanban?

Kanban es un sistema visual utilizado para gestionar el trabajo a medida que avanza en un proceso. Se visualiza tanto el proceso (el flujo de trabajo) como el trabajo real que pasa por ese proceso. El objetivo es identificar posibles inconvenientes en el proceso y solucionarlos para que el trabajo pueda fluir a través de forma rentable y a una velocidad o rendimiento óptimos.

### M.	¿Qué es un ERP?

Un ERP según sus siglas “Enterprise Resource Planning” o “Planificación de Recursos Empresariales”. 

Es un conjunto de aplicaciones de software integradas, que permiten automatizar la mayoría de las prácticas de negocio relacionadas con los aspectos operativos o productivos de una empresa. Facilitando y centralizando la información de todas las áreas que la componen: compras, producción, logística, finanzas, recursos humanos, marketing, servicios, proyectos y atención al cliente.
 
### N.	¿Salesforce es un ERP?

No. Salesforce contiene un sistema que permite planificar recursos empresariales pero no proveen ERP. 



# *Ejercicio 7*

En la carpeta del repositorio llamada Ejercicio 7, se detalla con imágenes el paso a paso realizado para la importación del archivo CSV. 

Primero, fui agregando los objetos personalizados que vi que existían en el CSV (Imágenes bajo el nombre de "Objetos personalizados").

Luego, mediante el Asistente de importación (Imagen llamada Wizard), comencé el proceso de importación. 

Finalmente, con el archivo cargado, me aseguré de que cada elemento personalizado de mi Playground coincida con los elementos que se especificaban en el CSV, (imágenes llamadas "Match" e "Import nuevo").

Las imágenes llamadas "Fin 1" y "Fin 2" son las que reflejan el final del proceso de importación. Cuando así se me informa que todos los archivos fueron cargados de manera correcta (aparte del mail que recibí confirmando esto). 
