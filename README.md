### *Salesforce Consultant*
#  `Evalución práctica` - Lucila Belén Cajal

BORRADOR: RESPUESTA 5 

<h2 id="Respuestas_informativas">Respuestas informativas</h2>

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

<h2 id="Respuestas_satisfactorias">Respuestas satisfactorias</h2>

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

<h2 id="Redirecciones">Redirecciones</h2>

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

<h2 id="Errores_de_cliente">Errores de cliente</h2>

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
 <dt>{{HTTPStatus(405, "405 Method Not Allowed")}}</dt>
 <dd>El método solicitado es conocido por el servidor pero ha sido deshabilitado y no puede ser utilizado. Los dos métodos obligatorios, <code>GET</code> y <code>HEAD</code>, nunca deben ser deshabilitados y no deberían retornar este código de error.</dd>
 <dt>{{HTTPStatus(406, "406 Not Acceptable")}}</dt>
 <dd>Esta respuesta es enviada cuando el servidor, después de aplicar una <a href="/en-US/docs/HTTP/Content_negotiation#Server-driven_negotiation">negociación de contenido servidor-impulsado</a>, no encuentra ningún contenido seguido por la criteria dada por el usuario.</dd>
 <dt>{{HTTPStatus(407, "407 Proxy Authentication Required")}}</dt>
 <dd>Esto es similar al código 401, pero la autenticación debe estar hecha a partir de un proxy.</dd>
 <dt>{{HTTPStatus(408, "408 Request Timeout")}}</dt>
 <dd>Esta respuesta es enviada en una conexión inactiva en algunos servidores, incluso sin alguna petición previa por el cliente. Significa que el servidor quiere desconectar esta conexión sin usar. Esta respuesta es muy usada desde algunos navegadores, como Chrome, Firefox 27+, o IE9, usa mecanismos de pre-conexión HTTP para acelerar la navegación. También hay que tener en cuenta que algunos servidores simplemente desconecta la conexión sin enviar este mensaje.</dd>
 <dt>{{HTTPStatus(409, "409 Conflict")}}</dt>
 <dd>Esta respuesta puede ser enviada cuando una petición tiene conflicto con el estado actual del servidor.</dd>
 <dt>{{HTTPStatus(410, "410 Gone")}}</dt>
 <dd>Esta respuesta puede ser enviada cuando el contenido solicitado ha sido borrado del servidor.</dd>
 <dt>{{HTTPStatus(411, "411 Length Required")}}</dt>
 <dd>El servidor rechaza la petición porque el campo de encabezado <code>Content-Length</code> no esta definido y el servidor lo requiere.</dd>
 <dt>{{HTTPStatus(412, "412 Precondition Failed")}}</dt>
 <dd>El cliente ha indicado pre-condiciones en sus encabezados la cual el servidor no cumple.</dd>
 <dt>{{HTTPStatus(413, "413 Payload Too Large")}}</dt>
 <dd>La entidad de petición es más larga que los límites definidos por el servidor; el servidor puede cerrar la conexión o retornar un campo de encabezado <code>Retry-After</code>.</dd>
 <dt>{{HTTPStatus(414, "414 URI Too Long")}}</dt>
 <dd>La URI solicitada por el cliente es más larga de lo que el servidor está dispuesto a interpretar.</dd>
 <dt>{{HTTPStatus(415, "415 Unsupported Media Type")}}</dt>
 <dd>El formato multimedia de los datos solicitados no está soportado por el servidor, por lo cual el servidor rechaza la solicitud.</dd>
 <dt>{{HTTPStatus(416, "416 Requested Range Not Satisfiable")}}</dt>
 <dd>El rango especificado por el campo de encabezado <code>Range</code> en la solicitud no cumple; es posible que el rango está fuera del tamaño de los datos objetivo del URI.</dd>
 <dt>{{HTTPStatus(417, "417 Expectation Failed")}}</dt>
 <dd>Significa que la expectativa indicada por el campo de encabezado <code>Expect</code> solicitada no puede ser cumplida por el servidor.</dd>
 <dt>{{HTTPStatus(418, "418 I'm a teapot")}}</dt>
 <dd>El servidor se rehúsa a intentar hacer café con una tetera.</dd>
 <dt>{{HTTPStatus(421, "421 Misdirected Request")}}</dt>
 <dd>La petición fue dirigida a un servidor que no es capaz de producir una respuesta. Esto puede ser enviado por un servidor que no está configurado para producir respuestas por la combinación del esquema y la autoridad que están incluidos en la URI solicitada</dd>
 <dt>{{HTTPStatus(422, "422 Unprocessable Entity")}} ({{Glossary("WebDAV")}})</dt>
 <dd>La petición estaba bien formada pero no se pudo seguir debido a errores de semántica.</dd>
 <dt>{{HTTPStatus(423, "423 Locked")}} ({{Glossary("WebDAV")}})</dt>
 <dd>El recurso que está siendo accedido está bloqueado.</dd>
 <dt>{{HTTPStatus(424, "424 Failed Dependency")}} ({{Glossary("WebDAV")}})</dt>
 <dd>La petición falló debido a una falla de una petición previa.</dd>
 <dt>{{HTTPStatus(426, "426 Upgrade Required")}}</dt>
 <dd>El servidor se rehúsa a aplicar la solicitud usando el protocolo actual pero puede estar dispuesto a hacerlo después que el cliente se actualice a un protocolo diferente. El servidor envía un encabezado <font face="consolas, Liberation Mono, courier, monospace"><span style="background-color: rgba(220, 220, 220, 0.5);">Upgrade</span></font> en una respuesta para indicar los protocolos requeridos.</dd>
 <dt>{{HTTPStatus(428, "428 Precondition Required")}}</dt>
 <dd>El servidor origen requiere que la solicitud sea condicional. Tiene la intención de prevenir problemas de 'actualización perdida', donde un cliente OBTIENE un estado del recurso, lo modifica, y lo PONE devuelta al servidor, cuando mientras un tercero ha modificado el estado del servidor, llevando a un conflicto.</dd>
 <dt>{{HTTPStatus(429, "429 Too Many Requests")}}</dt>
 <dd>El usuario ha enviado demasiadas solicitudes en un periodo de tiempo dado.</dd>
 <dt>{{HTTPStatus(431, "431 Request Header Fields Too Large")}}</dt>
 <dd>El servidor no está dispuesto a procesar la solicitud porque los campos de encabezado son demasiado largos. La solicitud PUEDE volver a subirse después de reducir el tamaño de los campos de encabezado solicitados.</dd>
 <dt>{{HTTPStatus(451, "451 Unavailable For Legal Reasons")}}</dt>
 <dd>El usuario solicita un recurso ilegal, como alguna página web censurada por algún gobierno.</dd>
</dl>

<h2 id="Errores_de_servidor">Errores de servidor</h2>

<dl>
 <dt>{{HTTPStatus(500, "500 Internal Server Error")}}</dt>
 <dd>El servidor ha encontrado una situación que no sabe cómo manejarla.</dd>
 <dt>{{HTTPStatus(501, "501 Not Implemented")}}</dt>
 <dd>El método solicitado no está soportado por el servidor y no puede ser manejado. Los únicos métodos que los servidores requieren soporte (y por lo tanto no deben retornar este código) son <code>GET</code> y <code>HEAD</code>.</dd>
 <dt>{{HTTPStatus(502, "502 Bad Gateway")}}</dt>
 <dd>Esta respuesta de error significa que el servidor, mientras trabaja como una puerta de enlace para obtener una respuesta necesaria para manejar la petición, obtuvo una respuesta inválida.</dd>
 <dt>{{HTTPStatus(503, "503 Service Unavailable")}}</dt>
 <dd>El servidor no está listo para manejar la petición. Causas comunes puede ser que el servidor está caído por mantenimiento o está sobrecargado. Hay que tomar en cuenta que junto con esta respuesta, una página usuario-amigable explicando el problema debe ser enviada. Estas respuestas deben ser usadas para condiciones temporales y el encabezado HTTP <code>Retry-After:</code> debería, si es posible, contener el tiempo estimado antes de la recuperación del servicio. El webmaster debe también cuidar los encabezados relacionados al caché que son enviados junto a esta respuesta, ya que estas respuestas de condición temporal deben usualmente no estar en el caché.</dd>
 <dt>{{HTTPStatus(504, "504 Gateway Timeout")}}</dt>
 <dd>Esta respuesta de error es dada cuando el servidor está actuando como una puerta de enlace y no puede obtener una respuesta a tiempo.</dd>
 <dt>{{HTTPStatus(505, "505 HTTP Version Not Supported")}}</dt>
 <dd>La versión de HTTP usada en la petición no está soportada por el servidor.</dd>
 <dt>{{HTTPStatus(506, "506 Variant Also Negotiates")}}</dt>
 <dd>El servidor tiene un error de configuración interna: negociación de contenido transparente para la petición resulta en una referencia circular.</dd>
 <dt>{{HTTPStatus(507, "507 Insufficient Storage")}}</dt>
 <dd>El servidor tiene un error de configuración interna: la variable de recurso escogida está configurada para acoplar la negociación de contenido transparente misma, y no es por lo tanto un punto final adecuado para el proceso de negociación.</dd>
 <dt>{{HTTPStatus(508, "508 Loop Detected")}} ({{Glossary("WebDAV")}})</dt>
 <dd>El servidor detectó un ciclo infinito mientras procesaba la solicitud.</dd>
 <dt>{{HTTPStatus(510, "510 Not Extended")}}</dt>
 <dd>Extensiones adicionales para la solicitud son requeridas para que el servidor las cumpla.</dd>
 <dt>{{HTTPStatus(511, "511 Network Authentication Required")}}</dt>
 <dd>El código de estado 511 indica que el cliente necesita autenticar para obtener acceso a la red.</dd>
</dl>
