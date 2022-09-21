# **EJERCICIO 2**

Las siguientes preguntas están orientadas a la comprensión del protocolo HTTP. Son agnósticas al lenguaje de programación, la idea es comprender los conceptos del estándar:

## \1.   ¿Qué es un servidor HTTP? 

​		**Respuesta:**

​		Definición de servidor HTTP: Un servidor HTTP ( Hypertext Transfer Protocol) o servidor web es un servidor que utiliza el protocolo de transferencia de hipertexto o HTTP para comunicarse con las computadoras cliente, generalmente a través de un navegador de internet. HTTP es el protocolo principal utilizado en los sitios web y los servidores HTTP ocupan la mayoría de los servidores de internet. Otros tipos de servidores se utilizan para usos mas específicos, como un servidor de archivos que utiliza el protocolo de transferencia de archivos FTP en lugar de HTTP.

​      El uso de un servidor HTTP se ve más comúnmente cuando se navega por internet hacia un sitio web, aunque muchas redes internas también utilizan servidores HTTP. En el proceso típico de navegación desde una computadora cliente. El localizador de recursos universal URL se coloca en la barra de direcciones de un navegador. Casi siempre comienza con la definición de que protocolo se utilizara para realzar la solicitud que suele ser el protocolo HTTP. La mayoría de los navegadores utilizan este protocolo de forma predeterminada, incluso cuando no se ingresa específicamente en la barra de direcciones.    

​      Además de proporcionar Páginas web, los servidores HTTP también pueden recibir datos de clientes que utilizan HTTP. Esto es bueno para situaciones en las que se necesita información del servidor HTTP, como completar un formulario, realizar una encuesta o cargar un archivo.

​      El servidor HTTP mas popular en Internet es el *Servidor HTTP Apache*. Apache se considera software de código abierto, lo que significa que el código fuente principal que lo creo es gratuito y los usuarios pueden cambiarlo y mejorarlo. Además de ser gratuito, también tiene la ventaja de utilizar secuencias de comandos. Estos significan que se pueden ejecutar scripts separados del software del servidor principal, lo que permite que una página web sea dinámica y cambie el contenido rápidamente sin interferir con el rendimiento general de la página web. 

## \2.   ¿Qué son los verbos HTTP? Mencionar los más conocidos

​		**Respuesta:**

​		Los verbos HTTP le indican al servidor que debe hacer con los datos identificador por la URL ingresada. Un ejemplo de los Verbos HTTP mas comunes y utilizan son los siguientes:

- ​     **Get** es el que se utiliza para consultar un recurso. Una de las principales características de una petición Get es que no debe causar efectos secundarios en el servidor, no deben producir nuevos registros, ni modificar los existentes. A esta cualidad la llamamos idempotencia, cuando una acción ejecutada un número indefinido de veces, produce siempre el mismo resultado.

- ​			Las peticiones con **POST** se dirigen a un recurso que representa una colección para indicar que el nuevo recurso debe agregarse a dicha colección, por ejemplo, ***POST/cursos\*** para agregar un nuevo recurso a la colección *cursos.* Algunos escenarios más complejos para el uso de POST son los inicios de sesión, agregar a un carrito de compras, procesar un pago nuevo, etc. Estos ejemplos nos dejan en claro que el recurso creado por **POST** no es precisamente una fila en la base de datos, el recurso puede ser una sesión, un pago en una API externa, etc.

- ​     Los verbos **PUT/PATCH** son muy similares ya que ambos se usan para modificar un recurso existente. En la teoría, PUT se diferencia de PATCH, en que el primero indica que vamos a sustituir por completo un recurso, mientras que PATCH habla de actualizar algunos elementos del recurso mismo, sin sustituirlo por completo.

  1.   Un escenario común para el uso de PUT sería una llamada para actualizar la información de un curso, por ejemplo: 

     -  *PUT/cursos/backend-profesional*

       O  también

     - *PATCH/cursos/backend-profesional**				 

​		En la práctica, y particularmente en Rails, ambos verbos se usan para actualizar un recurso, sin importar si lo sustituimos parcial o totalmente.

- ​     Por Último, **DELETE** es el verbo que usamos para eliminar registros, bien pudiera ser para eliminar un recurso individual como en: 
  -  *DELETE/cursos/backend-profesional*

o para eliminar una colección completa

*DELETE/cursos*

##  \3.   ¿Qué es un request y un response en una comunicación HTTP? ¿Qué son los headers? 

Los mensajes HTTP, son los medios por los cuales se intercambian datos entre servidores y clientes. Existen dos tipos de mensajes, Peticiones, que son enviadas por el cliente al servidor para solicitar el inicio de una acción, y Respuestas que es la respuesta del servidos a esa petición o Request.

Un HTTP request se compone de: 

​      ***Método\***: GET, POST, PUT, etc. Indicando que tipo de request es.

​      ***Path\***: La URL que se solicita, donde se encuentra el resource.

​      ***Protocolo\***: contienen HTTP y su versión.

Los HTTP headers son la parte central de los HTTP request y responses son quienes transmiten la información básica acerca del navegador del cliente, de la página solicitada, del servidor, etc. Aquí también se encuentran los datos de las cookies. La mayoría de los Headers son opcionales.

La primera línea es la línea del Request, que contiene su información básica (Método HTTP, URL y versión). Lo demás son headers HTTP.



## \4.   ¿Qué es un queryString? (En el contexto de una url)

​		Como se explicó anteriormente, dentro del protocolo HTTP encontramos diferentes métodos (verbos) con los cuales podemos realizar diferentes tipos de peticiones. El método mas utilizado es el método GET, el cual nos permite obtener un recurso por parte del servidor, ya sea una página web, un archivo txt, un gif etc…

Siempre que nosotros ingresamos a un sitio web desde nuestro navegador se hará a través del método GET. Lo interesante de este método es que podemos enviar la información al servidor de tal forma que seamos más precisos en el recurso que deseamos obtener. La información se enviará a través de la URL, en una sección denominada ***query string\***.

·     Por ejemplo, si realizamos una petición a la ruta

*/users*

Se espera que la respuesta, ya sea una pagina web, un objeto ***JSON*** o ***XML*** tenga relación con los usuarios.

Si el servidor lo permite también podemos enviar información extra 

*/users?order=true*

​		De esta manera realizamos la petición indicando que el servidor nos devuelva la información de los usuarios de forma ordenada. Todo lo que se encuentre después el signo de interrogación lo conoceremos como ***Query string***.

## \5.   ¿Qué es el responseCode? ¿Qué significado tiene los posibles valores devueltos?

​		Response code o código de estado es una parte de la respuesta devuelta por el servidor cuando un cliente llama a una URL. Con la ayuda de un código de estado, el servidor indica al cliente si la solicitud se ha procesado correctamente o si sea producido un error.      

En el siguiente cuadro encontraremos los códigos y sus correspondientes mensajes.

| **Code** | **Message**           |
| -------- | --------------------- |
| 200      | OK                    |
| 301      | Moved Permanently     |
| 302      | Moved Temporarily     |
| 404      | Not found             |
| 500      | Internal Server Error |
| 503      | Service Unavailable   |

## \6.   ¿Cómo se envía la data en un Get y cómo en un POST? 

​		Cuando un usuario rellena un formulario en una pagina web, los datos deben ser enviados de alguna manera. Las dos formas de envío posibles son a través de un Método GET y Método POST.

Por ejemplo: <form action=”http://www.procontacto.com/usuarios/nuevousuario” method= “get”>

 La acción se ejecutará cuando el usuario pulse el botón “enviar” o “submit” será el envío de los datos a la URL especificada usando el método get.   

​      La diferencia entre los métodos GET y POST radica en la forma de enviar los datos a la pagina cuando se pulsa el botón “Enviar”. Mientras que el método GET envía los datos usando la URL, el método POST los envía de forma que no podemos verlos, en un segundo plano u ocultos al usuario.

## \7.   ¿Qué verbo http utiliza el navegador cuando accedemos a una página?

​		Cuando escribes una dirección web en tu navegador y se abre la página que deseas, es porque tu navegador se ha comunicado con el servidor web por HTTP. Dicho de otra manera, el protocolo HTTP es el código o lenguaje en el que el navegador le comunica al servidor qué página quiere visualizar. Una vez ingresado al sitio web se utilizarán o no los distintos verbos que mencionamos en la [pregunta 2](#Pregunta2).

## \8.   Explicar brevemente qué son las estructuras de datos JSON y XML dando ejemplo de estructuras posibles.

​		Tanto JSON como XML son muy ampliamente utilizados en entornos de integración, donde es necesario transmitir datos desde una aplicación a otra, como lo son los Web Services (SOAP) y los servicios REST (JSON)

​		Una vez que hablamos de las diferencias podría comentar que XML es mucho mejor para la comunicación entre servidores y aplicaciones ya que permite mensajes mucho más completos, tipificados y además pueden ser validados con facilidad.

 		Por otro lado, JSON cuenta con un formato más simple y fácil de procesar, por lo que es ideal para dispositivos de bajo nivel de procesamiento, como los teléfonos móviles, los cuales son beneficiados ya que se requieren de menos consumo de datos para descargarlos y un consumo menor de batería al procesarlos, desde luego que los teléfonos modernos ya son capaces de procesar información mucho más rápido pero no podemos confiarnos en todo mundo tendrá uno de esos.

JSON está constituido por dos estructuras:

- Una colección de pares de nombre/valor.     En varios lenguajes esto es conocido como un *objeto*, registro,     estructura, diccionario, tabla hash, lista de claves o un arreglo     asociativo.
- Una lista ordenada de valores. En la     mayoría de los lenguajes, esto se implementa como arreglos, vectores,     listas o secuencias.

​		Estas son estructuras universales; virtualmente todos los lenguajes de programación las soportan de una forma u otra. Es razonable que un formato de intercambio de datos que es independiente del lenguaje de programación se base en estas estructuras.

En JSON, 2 ejemplos de estructuras son las siguientes:

Un *objeto* es un conjunto desordenado de pares nombre/valor. Un objeto comienza con `{`llave de apertura y termine con} llave de cierre. Cada nombre es seguido por: dos puntos y los pares nombre/valor están separados por `,`coma.

![image-20220921001534128](C:\Users\Nico\AppData\Roaming\Typora\typora-user-images\image-20220921001534128.png)

 

Otro ejemplo sería el siguiente:

Un *arreglo* es una colección de valores. Un arreglo comienza con [corchete izquierdo y termina con ]corchete derecho. Los valores se separan por ,coma.

![image-20220921001608159](C:\Users\Nico\AppData\Roaming\Typora\typora-user-images\image-20220921001608159.png)

  

En cuanto a los XML, los elementos de una estructura XML deben seguir una estructura de “árbol” estrictamente jerárquica, los elementos deben estar correctamente anidados, no pueden superponerse entre ellos y solo puede haber un elemento raíz.

De forma gráfica se vería de la siguiente manera.

 

![image-20220921001628740](C:\Users\Nico\AppData\Roaming\Typora\typora-user-images\image-20220921001628740.png)

La estructura de un documento XML se ve de la siguiente manera: 

![image-20220921001641387](C:\Users\Nico\AppData\Roaming\Typora\typora-user-images\image-20220921001641387.png)

## \9.   Explicar brevemente el estándar SOAP

​	Para ser capaces de comunicarse entre sí, un servicio Web y una aplicación cliente deben concordar sobre un protocolo común. **SOAP** es un protocolo estándar de comunicación para intercambiar información en un formato estructurado en un medio ambiente distribuido Cuando una aplicación cliente hace una solicitud a un método Web, un paquete **SOAP** es creado. Este paquete contiene el nombre del método Web invocado y los parámetros pasados al método Web en un formato XML. Esta información es usada para invocar el método Web con los parámetros apropiados. Cuando el paquete **SOAP** llega al servidor Web en el cual reside el servicio Web, el nombre del método Web y sus parámetros son extraídos del paquete **SOAP** y el método Web apropiado es invocado.

## \10. Explicar brevemente el estándar REST Full

## 	¿Qué son los headers en un request? ¿Para qué se utiliza el key Content-type en un header?

​		REST deriva de “**RE**presentational **S**tate **T**ransfer”, que traducido significaría “Transferencia de representación de estado”. Un servicio REST no posee estado, he de aquí la radicación de su nombre, lo que implica que entre dos llamadas cualesquiera, el servicio pierde todos sus datos.

​		Es considerada una técnica de arquitectura de software, es decir, un conjunto de principios y patrones de comunicación que ayudan a crear una forma de pensar y construir las APIs. Este tipo de arquitectura se define por un conjunto de restricciones entre los elementos, componentes, conectores y datos usados.

​		La definición formal de la técnica se describe de la siguiente forma:

- Un modelo cliente-servidor, es una     interfaz uniforme que separa a cliente y servidor. Haciendo que ambas     partes sean completamente independientes, pudiendo ser reemplazadas de     forma transparente para la otra parte.
- Un protocolo sin estado (o stateless),     cada petición HTTP realizada debe contener toda la información necesaria     para poder resolverla, esto permite que ni el cliente ni servidor necesiten     recordar ningún estado previo. Sin embargo, existen algunas excepciones y     existen algunas aplicaciones HTTP que incorporan la memoria caché, para     que así, el cliente pueda ejecutar en un futuro la misma respuesta para     peticiones idénticas. Además, debe ser idempotente, por lo que la misma     petición, con los mismos parámetros, debería devolver el mismo resultado.     Cabe destacar, que el hecho de que sea sin estado implica que no se puede     llamar un servicio REST y suministrarle datos y esperar que “nos recuerde”     en la siguiente petición. El estado lo mantiene el cliente, y es el mismo     quién debe pasar el estado en cada petición. Si se quiere que un servicio     REST recuerde ciertos datos, debo suministrarle la identidad de quién pide     el servicio en cada llamada. Eso puede ser un usuario y una contraseña, un     token o cualquier otro tipo de credenciales
- Cacheable, y donde cada petición debe     indicar si el resultado de esta puede ser o no cacheado. Un sistema     correcto de cacheo, tanto parcial como completo, ayudará en gran medida a     la escalabilidad y rendimiento.
- Las operaciones más importantes     relacionadas con los datos en cualquier sistema REST y la especificación     HTTP son cuatro: POST (crear), GET (leer y consultar), PUT (modificar) y     DELETE (borrar).
- Una interfaz uniforme que represente de     forma única los recursos, por ejemplo, mediante el uso de URIs [2] únicas,     y que permita la manipulación de dichos recursos a través de dichas     representaciones. Además, esta interfaz debe incorporar mensajes autos     descriptivos junto con un uso correcto de los códigos de estado HTML.
- Una técnica basada en el uso de     hipermedios como motor para poder indicar las diferentes acciones. El uso     de estos sirve para explicar la capacidad de una interfaz de desarrollo de     aplicaciones para proporcionar al cliente y al usuario los enlaces     adecuados, y ejecutar acciones concretas sobre los datos.

​	Asimismo, es una extensión del concepto de hipertexto. Ese concepto llevado al desarrollo de páginas web es lo que permite que el usuario pueda navegar por el conjunto de objetos a través de enlaces HTML.

​		**(a)  *¿Qué son los headers en un request?***

​      Los Headers de un request como ya mencionamos en la respuesta de la [pregunta 3](#Pregunta3) son la parte central de los HTTP request y responses son quienes transmiten la información básica acerca del navegador del cliente, de la página solicitada, del servidor, etc. Aquí también se encuentran los datos de las cookies. La mayoría de los Headers son opcionales.

La primera línea es la línea del Request, que contiene su información básica (Método HTTP, URL y versión). Lo demás son headers HTTP.

 

​	***(b)*  *¿Para qué se utiliza el key Content-type en un header?***

El content type, también conocido como media type o MIME type (extensiones de correo de Internet multipropósito), es un recurso que se utiliza en la cabecera HTTP (header) y que le indica al cliente o navegador qué clase de archivo o medio le está enviando el servidor. Cuando el content type se emplea en una solicitud de búsqueda, se le comunica al servidor qué tipo de archivo o medio está buscando y, aunque el servidor no necesariamente se tiene que apegar a la petición, le ayuda a encontrar los recursos correctos para retornarlos en el formato deseado. 

En el caso contrario, cuando los recursos se envían desde el servidor al navegador, el encabezado content type le indica al buscador el tipo de contenido que está recibiendo para priorizar los recursos a usar, mejorando el tiempo de procesamiento, lo que además optimiza la velocidad de carga de un sitio web. Sin embargo, aun cuando la extensión del archivo ya proporciona algún tipo de información, no siempre es suficiente y es esta la razón por la que se recomienda el uso de los content type. 