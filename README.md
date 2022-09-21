# **EJERCICIO 1**

Instalación del ambiente

El presente ejercicio busca realizar la instalación del ambiente para el desarrollo del trabajo práctico. A continuación se listará una serie de aplicaciones a instalar

 - [ ] \1.   **Instalar el IDE Visual Studio Code**: Un IDE (Entorno de desarrollo integrado), es una aplicación que nos brinda facilidades al momento de generar código. Dentro de Pro Contacto utilizamos Visual Studio Code para los proyectos relacionados a aplicaciones web y móviles. El mismo permite trabajar con varios lenguajes tales como: HTML, CSS, C#, Javascript, APEX (NodeJS, Angular, IONIC, React, Typescript, etc).
- [ ]  \2.   I**nstalar GIT y GIT Bash:** Git es una aplicación utilizada para el control de versionado de código. En otras palabras, es una suerte de “disco” en donde se guardarán los distintos files que componen nuestra aplicación (ejemplo: index.html, estilos.css, etc). La gran ventaja de GIT es que al momento de subir una versión nueva de un archivo, genera un “backup” de la versión anterior para poder ser restaurado cuando se desee. Además, el código se encuentra en la “nube”, por lo que puede ser accedido y descargado desde cualquier lugar que tenga acceso a internet.

# **EJERCICIO 2**

Las siguientes preguntas están orientadas a la comprensión del protocolo HTTP. Son agnósticas al lenguaje de programación, la idea es comprender los conceptos del estándar:

## \1.   ¿Qué es un servidor HTTP? 


​<details><summary>		**Respuesta:**</summary>

​		Definición de servidor HTTP: Un servidor HTTP ( Hypertext Transfer Protocol) o servidor web es un servidor que utiliza el protocolo de transferencia de hipertexto o HTTP para comunicarse con las computadoras cliente, generalmente a través de un navegador de internet. HTTP es el protocolo principal utilizado en los sitios web y los servidores HTTP ocupan la mayoría de los servidores de internet. Otros tipos de servidores se utilizan para usos mas específicos, como un servidor de archivos que utiliza el protocolo de transferencia de archivos FTP en lugar de HTTP.

​      El uso de un servidor HTTP se ve más comúnmente cuando se navega por internet hacia un sitio web, aunque muchas redes internas también utilizan servidores HTTP. En el proceso típico de navegación desde una computadora cliente. El localizador de recursos universal URL se coloca en la barra de direcciones de un navegador. Casi siempre comienza con la definición de que protocolo se utilizara para realzar la solicitud que suele ser el protocolo HTTP. La mayoría de los navegadores utilizan este protocolo de forma predeterminada, incluso cuando no se ingresa específicamente en la barra de direcciones.    

​      Además de proporcionar Páginas web, los servidores HTTP también pueden recibir datos de clientes que utilizan HTTP. Esto es bueno para situaciones en las que se necesita información del servidor HTTP, como completar un formulario, realizar una encuesta o cargar un archivo.

​      El servidor HTTP mas popular en Internet es el *Servidor HTTP Apache*. Apache se considera software de código abierto, lo que significa que el código fuente principal que lo creo es gratuito y los usuarios pueden cambiarlo y mejorarlo. Además de ser gratuito, también tiene la ventaja de utilizar secuencias de comandos. Estos significan que se pueden ejecutar scripts separados del software del servidor principal, lo que permite que una página web sea dinámica y cambie el contenido rápidamente sin interferir con el rendimiento general de la página web. 
</details>

## \2.   ¿Qué son los verbos HTTP? Mencionar los más conocidos


​<details><summary>		**Respuesta:**</summary>

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
</details>
  
##  \3.   ¿Qué es un request y un response en una comunicación HTTP? ¿Qué son los headers? 

​<details><summary>		**Respuesta:**</summary>
Los mensajes HTTP, son los medios por los cuales se intercambian datos entre servidores y clientes. Existen dos tipos de mensajes, Peticiones, que son enviadas por el cliente al servidor para solicitar el inicio de una acción, y Respuestas que es la respuesta del servidos a esa petición o Request.

Un HTTP request se compone de: 

​      ***Método\***: GET, POST, PUT, etc. Indicando que tipo de request es.

​      ***Path\***: La URL que se solicita, donde se encuentra el resource.

​      ***Protocolo\***: contienen HTTP y su versión.

Los HTTP headers son la parte central de los HTTP request y responses son quienes transmiten la información básica acerca del navegador del cliente, de la página solicitada, del servidor, etc. Aquí también se encuentran los datos de las cookies. La mayoría de los Headers son opcionales.

La primera línea es la línea del Request, que contiene su información básica (Método HTTP, URL y versión). Lo demás son headers HTTP.

</details>

## \4.   ¿Qué es un queryString? (En el contexto de una url)
​<details><summary>		**Respuesta:**</summary>
​		Como se explicó anteriormente, dentro del protocolo HTTP encontramos diferentes métodos (verbos) con los cuales podemos realizar diferentes tipos de peticiones. El método mas utilizado es el método GET, el cual nos permite obtener un recurso por parte del servidor, ya sea una página web, un archivo txt, un gif etc…

Siempre que nosotros ingresamos a un sitio web desde nuestro navegador se hará a través del método GET. Lo interesante de este método es que podemos enviar la información al servidor de tal forma que seamos más precisos en el recurso que deseamos obtener. La información se enviará a través de la URL, en una sección denominada ***query string\***.

·     Por ejemplo, si realizamos una petición a la ruta

*/users*

Se espera que la respuesta, ya sea una pagina web, un objeto ***JSON*** o ***XML*** tenga relación con los usuarios.

Si el servidor lo permite también podemos enviar información extra 

*/users?order=true*

​		De esta manera realizamos la petición indicando que el servidor nos devuelva la información de los usuarios de forma ordenada. Todo lo que se encuentre después el signo de interrogación lo conoceremos como ***Query string***.

</details>

## \5.   ¿Qué es el responseCode? ¿Qué significado tiene los posibles valores devueltos?
​<details><summary>		**Respuesta:**</summary>
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
</details>

## \6.   ¿Cómo se envía la data en un Get y cómo en un POST? 
  
​<details><summary>		**Respuesta:**</summary>
​		Cuando un usuario rellena un formulario en una pagina web, los datos deben ser enviados de alguna manera. Las dos formas de envío posibles son a través de un Método GET y Método POST.

Por ejemplo: <form action=”http://www.procontacto.com/usuarios/nuevousuario” method= “get”>

 La acción se ejecutará cuando el usuario pulse el botón “enviar” o “submit” será el envío de los datos a la URL especificada usando el método get.   

​      La diferencia entre los métodos GET y POST radica en la forma de enviar los datos a la pagina cuando se pulsa el botón “Enviar”. Mientras que el método GET envía los datos usando la URL, el método POST los envía de forma que no podemos verlos, en un segundo plano u ocultos al usuario.


  </details>
  
## \7.  ¿Qué verbo http utiliza el navegador cuando accedemos a una página?
  
​<details><summary>		**Respuesta:**</summary>
  
​		Cuando escribes una dirección web en tu navegador y se abre la página que deseas, es porque tu navegador se ha comunicado con el servidor web por HTTP. Dicho de otra manera, el protocolo HTTP es el código o lenguaje en el que el navegador le comunica al servidor qué página quiere visualizar. Una vez ingresado al sitio web se utilizarán o no los distintos verbos que mencionamos en la [pregunta 2](#Pregunta2).
  
 </details>
  
## \8.   Explicar brevemente qué son las estructuras de datos JSON y XML dando ejemplo de estructuras posibles.
  
​<details><summary>		**Respuesta:**</summary>
  
​		Tanto JSON como XML son muy ampliamente utilizados en entornos de integración, donde es necesario transmitir datos desde una aplicación a otra, como lo son los Web Services (SOAP) y los servicios REST (JSON)

​		Una vez que hablamos de las diferencias podría comentar que XML es mucho mejor para la comunicación entre servidores y aplicaciones ya que permite mensajes mucho más completos, tipificados y además pueden ser validados con facilidad.

 		Por otro lado, JSON cuenta con un formato más simple y fácil de procesar, por lo que es ideal para dispositivos de bajo nivel de procesamiento, como los teléfonos móviles, los cuales son beneficiados ya que se requieren de menos consumo de datos para descargarlos y un consumo menor de batería al procesarlos, desde luego que los teléfonos modernos ya son capaces de procesar información mucho más rápido pero no podemos confiarnos en todo mundo tendrá uno de esos.

JSON está constituido por dos estructuras:

- Una colección de pares de nombre/valor.     En varios lenguajes esto es conocido como un *objeto*, registro,     estructura, diccionario, tabla hash, lista de claves o un arreglo     asociativo.
- Una lista ordenada de valores. En la     mayoría de los lenguajes, esto se implementa como arreglos, vectores,     listas o secuencias.

​		Estas son estructuras universales; virtualmente todos los lenguajes de programación las soportan de una forma u otra. Es razonable que un formato de intercambio de datos que es independiente del lenguaje de programación se base en estas estructuras.

En JSON, 2 ejemplos de estructuras son las siguientes:

Un *objeto* es un conjunto desordenado de pares nombre/valor. Un objeto comienza con `{`llave de apertura y termine con} llave de cierre. Cada nombre es seguido por: dos puntos y los pares nombre/valor están separados por `,`coma.


![pregunta 8-1  ](https://user-images.githubusercontent.com/114038310/191408578-c9961bfd-5e0f-4103-ad08-8103ec9400d0.png)

 

Otro ejemplo sería el siguiente:

Un *arreglo* es una colección de valores. Un arreglo comienza con [corchete izquierdo y termina con ]corchete derecho. Los valores se separan por ,coma.


![pregunta 8-2  ](https://user-images.githubusercontent.com/114038310/191408796-e3994ac8-ff06-4951-a4d5-62b3b52e2490.png)

  

En cuanto a los XML, los elementos de una estructura XML deben seguir una estructura de “árbol” estrictamente jerárquica, los elementos deben estar correctamente anidados, no pueden superponerse entre ellos y solo puede haber un elemento raíz.

De forma gráfica se vería de la siguiente manera.

 
![pregunta 8-3  ](https://user-images.githubusercontent.com/114038310/191408818-ef48bf67-d964-42b1-ab26-13d4edd28ef0.png)


La estructura de un documento XML se ve de la siguiente manera: 
  
![pregunta 8-4  ](https://user-images.githubusercontent.com/114038310/191408839-a933420b-13ed-4683-8a89-ac32c2bd364e.png)

 </details>
  
## \9.   Explicar brevemente el estándar SOAP
  
​<details><summary>		**Respuesta:**</summary>
​	Para ser capaces de comunicarse entre sí, un servicio Web y una aplicación cliente deben concordar sobre un protocolo común. **SOAP** es un protocolo estándar de comunicación para intercambiar información en un formato estructurado en un medio ambiente distribuido Cuando una aplicación cliente hace una solicitud a un método Web, un paquete **SOAP** es creado. Este paquete contiene el nombre del método Web invocado y los parámetros pasados al método Web en un formato XML. Esta información es usada para invocar el método Web con los parámetros apropiados. Cuando el paquete **SOAP** llega al servidor Web en el cual reside el servicio Web, el nombre del método Web y sus parámetros son extraídos del paquete **SOAP** y el método Web apropiado es invocado.
</details>
  
## \10. Explicar brevemente el estándar REST Full
  
​<details><summary>		**Respuesta:**</summary>
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
  </details>
  
  # **EJERCICIO 3**
  
  Recomendamos previamente entender los conceptos de la sintaxis “json” antes de arrancar con los ejercicios.

Descargar el POSTMAN (aplicación para realizar request como cliente), adjuntando un screen de resolución para cada ítem:

 

1. Realizar un     request GET a la URL: https://procontacto-reclutamiento-default-rtdb.firebaseio.com/contacts.json
  
  ![imagen](https://user-images.githubusercontent.com/114038310/191409958-04914b95-98ff-45d9-a977-fadefb85bffc.png)

2. Realizar un     request POST a la URL anterior, y con body:

{

"name":"Tu nombre",

"email":tunombre.tuapellido@procontacto.com.mx

}

Tip: (Marcar la opción “raw” como body)

![imagen](https://user-images.githubusercontent.com/114038310/191411315-488ee8d0-cd60-49c4-9fcc-b3e2efd298de.png)

  
  
  
1. Realizar     nuevamente un request GET a la URL: https://procontacto-reclutamiento-default-rtdb.firebaseio.com/contacts.json

  ![imagen](https://user-images.githubusercontent.com/114038310/191411594-855cf29e-e95d-434e-a2cf-5f8cba937bae.png)

  
¿Qué diferencias se observan entre las llamadas el punto 1 y 3?
  La diferencia que se observan es que al realizar el POST de la nueva Informacion esta se actualiza en la URL en cuestion que luego al realizar otro GET sobre la URL se obtiene la informacion actualizada.
  
  # **EJERCICIO 4**
  
  Solicitar usuario de Trailhead a vicente.cuenca@procontacto.com.mx

Cambiar el idioma de Trailhead a inglés.

Realizar los siguientes módulos de Trailhead:

 

https://trailhead.salesforce.com/users/norozco3/trailmixes/introduccion

 

Se recomienda usar el mismo Playground para todos los módulos solicitados. Excepto que se solicite crear uno nuevo en el enunciado del Módulo.

Para revisar la resolución de los módulos, compartir la URL del perfil público de Trailhead en una liga dentro del Readme.
  
  La URL del Perfil Público es la siguiente: **https://trailblazer.me/id/mtarrio**
  
  # **EJERCICIO 5**
  
  Explicar que son conceptualmente, qué datos almacenan en forma estándar y cómo se relacionan el resto (algunos no se relacionan entre sí) cada uno de los siguientes objetos de Salesforce:

 

**\1.    Lead**

  <details><summary>Definición</summary>


- El lead es un **cliente potencial que demostró interés en un producto o servicio** ofrecido por la marca por medio de la interacción con contenidos y otros materiales. Además de ser una oportunidad de negocio, **el lead es un recurso valioso** en cualquier estrategia de marketing, pudiendo convertirse tanto en un cliente como en un promotor de la empresa.

  En general, un lead es un individuo que está dentro del alcance o  influencia de la empresa. Y es así porque se trata de una persona que  brinda su **información de contacto** a cambio de algo que le puedes ofrecer, pasando entonces a formar parte de la **base de datos** sobre la cual pueden actuar los equipos de Marketing y Ventas de la empresa. 

  </details>

**\2.    Account**

<details><summary>Definición</summary>


- Los negocios buenos están construidos sobre excelentes relaciones con los clientes. La construcción de esas relaciones lleva tiempo y  cuidados, y también requiere información. Tiene que saber quiénes son  sus clientes, dónde encontrarlos y cómo hacer contacto con ellos, y  también cómo satisfacerlos.

  En Salesforce, almacena la información sobre sus clientes  mediante cuentas y contactos. Las cuentas son compañías con las que hace negocios y los contactos son las personas que trabajan para dichas  compañías.

  Las cuentas y los contactos están relacionados con muchos otros  objetos estándar, lo que los convierte en algunos de los objetos más  importantes de Salesforce. Comprender cómo usar las cuentas y los  contactos es fundamental para aprovechar al máximo Salesforce.

  Si hace negocios con una sola persona, como un único contratista o un consumidor individual, use un tipo de cuenta especial llamado cuenta personal. Las cuentas personales son parecidas a las cuentas de  negocio, pero como están pensadas para registrar información sobre una  persona en particular, las cuentas personales no tienen sus propios  contactos.
  </details>

**\3.    Contact**

  <details><summary>Definición</summary>


- Utilice **contactos** para almacenar información acerca de personas con las que hace negocios. Los **contactos** se asocian habitualmente con una cuenta, pero también se pueden asociar con otros registros como oportunidades.
  </details>

**\4.    Opportunity**

<details><summary>Definición</summary>


- Las oportunidades son **acuerdos en curso** Los registros de oportunidad realizan un seguimiento de detalles acerca de acuerdos, incluyendo para qué cuentas son, quiénes son las personas  implicadas y las cantidades de las ventas potenciales.
  </details>

**\5.    Product**

<details><summary>Definición</summary>


- Productos son los **elementos y servicios que distribuye a clientes**. Cada producto puede existir en múltiples listas de precios con precios diferentes.
  </details>

**\6.    PriceBook**

<details><summary>Definición</summary>


- Las listas de precios realizan un seguimiento de los precios de los productos y servicios que su empresa ofrece a los clientes.
  </details>

**\7.    Quote**

<details><summary>Definición</summary>


- Presupuestos en Salesforce **representa los precios propuestos de los servicios y productos de su compañía**. Puede crear un presupuesto desde una oportunidad y sus productos. Cada  oportunidad puede tener varios presupuestos asociados y cualquiera de  ellos se puede sincronizar con la oportunidad.
  </details>

**\8.    Asset**

<details><summary>Definición</summary>


- Un activo en Salesforce **representa un producto específico adquirido o instalado**. Por ejemplo, si vende robots, puede crear un producto Robot en  Salesforce, y luego crear múltiples activos representando los robots que vendió.
  </details>

**\9.    Case**

<details><summary>Definición</summary>


- Un caso es una  pregunta, un comentario o un problema de un cliente. Los agentes del  servicio de atención al cliente pueden revisar casos para ver cómo  pueden ofrecer un mejor servicio.
  </details>

**\10.   Article**

<details><summary>Definición</summary>


- Su base de **Salesforce** Knowledge se crea desde artículos de conocimientos, que son documentos  de información. Los artículos pueden incluir información sobre procesos, como cómo restablecer su producto a sus valores predeterminados o  preguntas más frecuentes como cuánto almacenamiento admite su producto.

  </details>

- *Los campos enumerarlos a través de una lista de texto en el Readme y las relaciones a través de un diagrama UML simple realizado con Drawio.*

  * Ejemplo de diagrama*

  * Drawio: https://app.diagrams.net/*

 

- *Que una cuenta tiene muchos contactos se representa de la siguiente manera:*

 

![img](file:///C:/Users/Nico/AppData/Local/Temp/msohtmlclip1/01/clip_image002.gif)

 

- *Completar el resto de las relaciones agregando el resto de los objetos enumerados.*

  

- *Exportar el diagrama de Drawio, subirlo al repositorio y agregarlo dentro del readme con la etiqueta para [linkear imágenes](https://stackoverflow.com/questions/14494747/how-to-add-images-to-readme-md-on-github).*

  

- *Se puede usar el schema builder de salesforce para entender las relaciones.*
  
  A continuación el diagrama exportado en formato JPG.

 ![Ejercicio 5](https://user-images.githubusercontent.com/114038310/191416969-e2ff572b-458f-4b35-973c-5cb7dfbfcd96.jpg)
  
 # **EJERCICIO 6**

Responder las siguientes preguntas brevemente sobre:

Soluciones de Salesforce

A.    ¿Qué es Salesforce?

<details><summary>Respuesta</summary>

- Salesforce es una **plataforma CRM diseñada para reunir, en una única solución, todos los procesos relacionados con nuestros clientes**. ¿Y dónde se almacena dicha información? En la nube. 

  Así, esta herramienta proporciona a  todos los departamentos de tu organización, incluyendo los de marketing, ventas, atención al cliente o comercio electrónico, una **visión unificada y actualizada de todo lo que ocurre con los clientes gracias a esta plataforma integrada**. 

  </details>

B.    ¿Qué es Sales Cloud?

<details><summary>Respuesta</summary>

- Salesforce Sales Cloud es una **plataforma de ventas que da seguimiento al proceso de ventas, desde perfilar  prospectos, hacer el contacto inicial hasta el final de la compra**.

  </details>

C.    ¿Qué es Service Cloud?

- Salesforce Service Cloud es la **aplicación para atención al cliente número uno del mercado**. Implantada directamente en la plataforma de Salesforce CRM, lo que nos permite tener una visión 360 de nuestros cliente

  </details>

D.    ¿Qué es Health Cloud?

<details><summary>Respuesta</summary>

- Health Cloud es una **plataforma especialmente diseñada para la gestión clínica de pacientes por medio de tecnologías on-cloud**, la cual ofrece: una comunicación más personalizado entre pacientes, miembros, proveedores y prestadores de servicios de salud, y un mejor ajuste a los procesos, servicios y datos médicos según el perfil de cuidado de cada paciente

  </details>

E.    ¿Qué es Marketing Cloud?

<details><summary>Respuesta</summary>

- Esta es una plataforma de marketing que contiene múltiples  herramientas diseñadas **para gestionar de manera eficiente la interacción de la marca con sus clientes (y potenciales) a través de diferentes  canales**. 

  La tecnología detrás de la herramienta permite hacer una gestión del  marketing mucho más eficiente y efectiva. Los equipos tienen a su  disposición una solución que les permite crear experiencias multicanal,  que permiten **contactar con el cliente en el momento adecuado por el canal adecuado** (email, SMS, notificación push, social, ads, etc.) y de esta forma **aumentar la captación de clientes y las ventas**. Planificar, monitorizar, analizar y tomar decisiones en tiempo real es más fácil que nunca con Marketing Cloud

  </details>

**Funcionalidades de Salesforce**

A.    ¿Qué es un RecordType?

<details><summary>Respuesta</summary>

- ¿Qué son los Record Types en Salesforce? Los Record Types en Salesforce **nos permiten definir diferentes Business Process, Pages Layouts y Picklist Values en un determinado objeto**. Así mismo, los Record Types nos ayudan a mostrar distintos tipos de información según el perfil del usuario

  </details>

B.    ¿Qué es un ReportType?

<details><summary>Respuesta</summary>

- Los **reportes** le proporcionan el acceso a sus datos de **Salesforce**. Puede explorar sus datos de **Salesforce** en combinaciones casi infinitas, mostrarlos en formatos fáciles de  comprende y compartir las perspectivas resultantes con otros.

  </details>

C.    ¿Qué es un Page Layout?

<details><summary>Respuesta</summary>

- Los formatos de página **controlan el formato y la organización de botones, campos, S-Control,  Visualforce, vínculos personalizados y listas relacionadas en páginas de registros de objetos**. También ayudan a determinar los campos que son visibles, de sólo lectura y obligatorios

  </details>

D.    ¿Qué es un Compact Layout?

<details><summary>Respuesta</summary>

- **Los formatos compactos controlan qué campos aparecen en el encabezado**. Para cada objeto, puede asignar hasta 10 campos, incluyendo el campo Nombre, para mostrar en ese área.

  </details>

E.    ¿Qué es un Perfil?

<details><summary>Respuesta</summary>

- ​	Los perfiles **definen cómo acceden los usuarios a objetos y datos y qué pueden hacer en la aplicación**. Cuando cree usuarios, asigne un perfil a cada uno. Para ver los  perfiles en su organización, en Configuración, ingrese Perfiles en el  cuadro Búsqueda rápida y, a continuación, seleccione Perfiles.

  </details>

F.    ¿Qué es un Rol?

<details><summary>Respuesta</summary>

- **Los roles controlan el nivel de visibilidad que un usuario tiene sobre los datos de su organización**. Usuarios en cualquier función dada pueden ver, editar, e informar sobre todos los datos para funciones por debajo de ellos en la jerarquía de  roles.

  </details>

G.    ¿Qué es un Validation Rule?

<details><summary>Respuesta</summary>

- ​	Las reglas de validación **verifican que los datos que un usuario introduce en un registro cumplen con las  normas que especifica antes de que el usuario guarde el registro**.  Una regla de validación puede contener una fórmula o expresión que  evalúa los datos en uno o más campos y ofrece un valor “Verdadero” o  “Falso”.

  </details>

H.  ¿Qué diferencia hay entre una relación **Master Detail** y **Lookup**?

<details><summary>Respuesta</summary>

- Relación **Master**-**Detail**: este tipo de relación te permite tener una fuerte conexión entre  objetos, siendo uno de estos llamado el objeto Maestro (También  considerado como el objeto padre) y el otro el objeto Detalle (También  considerado como el objeto hijo) mientras que los **filtros** de búsqueda son configuraciones del administrador restringen los  valores válidos y los resultados de los campos del cuadro de diálogo de  búsqueda, relaciones principal-detalle y relaciones jerárquicas

  </details>

I.     ¿Qué es un Sandbox?

<details><summary>Respuesta</summary>

- ​	Un Sandbox **es una copia de su organización en un entorno aislado que puede usar para distintos fines, como pruebas y capacitación**. Los sandbox están completamente aislados de su organización de producción de Salesforce.

  </details>

J.     ¿Qué es un ChangeSet?

<details><summary>Respuesta</summary>

- ​	Un conjunto de cambios es una **manera de enviar información sobre personalizaciones desde una organización a otra**. Por ejemplo, podríamos crear y probar un nuevo objeto personalizado en  una organización de sandbox y luego enviarlo a la organización de  producción mediante un conjunto de cambios.

  </details>

K.    ¿Para qué sirve el import Wizard de Salesforce?

<details><summary>Respuesta</summary>

- ​	**Posee una  interfaz unificada que permite importar datos de muchos de los objetos  estándares de Salesforce, como prospectos, cuentas o contactos; así como de objetos personalizados**.

  </details>

L.    ¿Para qué sirve la funcionalidad Web to Lead?

<details><summary>Respuesta</summary>

- ​	En el ámbito del inbound marketing, **uno de los recursos más útiles y sencillos para generar leads de calidad** es la herramienta Web to Lead de Salesforce, una solución cuyo uso no  requiere conocimientos de código de programación ni nociones técnicas  específicas.

  </details>

M.   ¿Para qué sirve la funcionalidad Web to Case?

<details><summary>Respuesta</summary>

- ​	Esta funcion sirve para Recopilar las solicitudes de servicio de atención al cliente directamente del sitio *web* de su empresa y generar automáticamente casos nuevos con Caso *Web*.

  </details>

N.    ¿Para qué sirve la funcionalidad Omnichannel?

<details><summary>Respuesta</summary>

- ​	Salesforce además ofrece una funcionalidad llamada justamente **Omni-Channel**, la cual una vez habilitada se puede configurar de forma que permite que un agente, bajo una misma pantalla, pueda recibir casos que hayan  entrado a la plataforma a través de un correo electrónico, o bien un  chat, etc., canales que se pueden dar de alta en Service Channels bajo  esta herramienta. Se puede optar por un enrutamiento por colas de las  que formen parte los agentes o bien según los skills o habilidades que  tenga un agente en particular, o incluso puede enrutar un tercero  siempre que se integre usando APIs.

  </details>

O.    ¿Para qué sirve la funcionalidad Chatter?

<details><summary>Respuesta</summary>

- ​	Chatter es una **red social empresarial de Salesforce**. Diseñada para permitir y mejorar el uso compartido y la colaboración,  se puede utilizar para compartir información, proponer ideas, conectar  equipos y proporcionar comentarios.

  </details>

**Conceptos generales**

A.    ¿Qué significa SaaS?

<details><summary>Respuesta</summary>

- ​	SaaS: ¿Qué es Software as a Service? SaaS, o Software as a Service, **es una forma de poner.** **a disposición softwares y soluciones de tecnología por medio de la internet, como un servicio**. Con este modelo, tu empresa no necesita instalar, mantener y actualizar hardwares y softwares.

  </details>

B.    ¿Salesforce es Saas?

<details><summary>Respuesta</summary>

- ​	Si , Salesforce es SaaS.

  </details>

C.    ¿Qué significa que una solución sea Cloud?

<details><summary>Respuesta</summary>

- De una manera simple, la computación en la nube (cloud computing) **es una tecnología que permite acceso remoto a softwares, almacenamiento de archivos y procesamiento de datos por medio de Internet**, siendo así, una alternativa a la ejecución en una computadora personal o servidor local.

  </details>

D.    ¿Qué significa que una solución sea On-Premise?

<details><summary>Respuesta</summary>

- ​	CRM Local, también conocido como CRM On-Premise, **es el tipo de CRM que es alojado en un servidor físico en la empresa y exige manutención de un equipo de TI propio**. En ese caso, es necesario instalar el software de CRM en el servidor o en una computadoa que sea utilizada como tal.

  </details>

E.    ¿Qué es un pipeline de ventas?

<details><summary>Respuesta</summary>

- Es el término utilizado para describir el **conjunto o secuencia de acciones que un vendedor lleva a cabo para trasladar a un prospecto potencial a  un ser un cliente**.

  Esta metodología es comúnmente utilizada por aquellos líderes que confían en los procesos y estrategias de venta de su empresa para hacer avanzar al lead en su propio proceso de compra.

  Los informes de pipeline de ventas permiten a los líderes de ventas y  vendedores conocer el estado de cada transacción y comprender si la  distribución de sus ofertas es la más adecuada para cumplir con todos  los objetivos de ventas de la organización.

  </details>

F.    ¿Qué es un funnel de ventas?

<details><summary>Respuesta</summary>

- El funnel de ventas se centra en el **conjunto de acciones tomadas por  los vendedores y comunica de forma muy visual las tasas de conversión de los clientes potenciales** a través de las etapas del proceso.

  El funnel de ventas es conocido como **“embudo”** por su forma, es amplio en  la parte superior a medida que se ingresan los prospectos y luego se  vuelve cada vez más estrecho a medida que se eliminan y descalifican  prospectos o deciden no comprar.

  </details>

G.    ¿Qué significa Customer Experience?

<details><summary>Respuesta</summary>

- ​	Customer Experience (CX), o Experiencia del Cliente (en español) es como se llama al **conjunto de percepciones e impresiones que un consumidor posee sobre una  determinada empresa tras interactuar con ella, ya sea online o en vivo**.

  </details>

H.    ¿Qué significa omnicanalidad?

<details><summary>Respuesta</summary>

- OmniCanal **es una  función flexible y personalizable, y puede configurarla mediante  declaración, lo que significa que no es necesario escribir código**.  Utilice OmniCanal para gestionar la prioridad de elementos de trabajo,  lo que hace posible enrutar elementos de trabajo importantes a agentes  rápidamente.

  </details>

I.     ¿Qué significa que un negocio sea B2B?¿Qué significa que un negocio sea B2C?¿Qué es un KPI?

<details><summary>Respuesta</summary>

- ​	Negocio a negocio hace referencia a las **transacciones comerciales entre empresas**, es decir, a aquellas que típicamente se establecen entre fabricantes y/o un fabricante con su distribuidor, o entre un  distribuidor y un minorista.

- También conocido como Business-to-consumer por eso sus siglas B2C, se refiere a la **actividad comercial entre un negocio y un consumidor individual**. Mientras esto aplica a cualquier tipo de negocio de venta directa al consumidor, se ha asociado con la venta en línea, también conocido como e-commerce.

- Un KPI, conocido también como **indicador clave o medidor de  desempeño o indicador clave de rendimiento**, es una medida del nivel del  rendimiento de un proceso. El valor del indicador está directamente  relacionado con un objetivo fijado previamente y normalmente se expresa  en valores porcentuales.

  </details>

J.     ¿Qué es una API y en qué se diferencia de una Rest API?

<details><summary>Respuesta</summary>

- ​	**La interfaz de programación de aplicaciones**, conocida también por  la sigla API, en inglés, application programming interface,  es un **conjunto de subrutinas, funciones y procedimientos** que ofrece cierta  biblioteca para ser utilizada por otro software como una capa de abstracción.

  </details>

K.    ¿Qué es un Proceso Batch?

<details><summary>Respuesta</summary>

- ​	Se conoce como **sistema por lotes, o modo batch**, a la **ejecución de  un programa sin el control o supervisión directa del usuario** . Este tipo de programas se caracterizan porque su ejecución no  precisa ningún tipo de interacción con el usuario.

  </details>

L.    ¿Qué es Kanban?

<details><summary>Respuesta</summary>

- ​	Kanban, cuyo significado es letrero o tarjeta en japonés,  es un **sistema de información que controla de modo armónico la fabricación de  los productos necesarios en la cantidad y tiempo** necesarios en cada uno  de los procesos que tienen lugar tanto en el interior de la fábrica,  como entre distintas empresas.

  </details>

M.   ¿Qué es un ERP? 

<details><summary>Respuesta</summary>

- ​	ERP son las siglas en inglés de "**planificación de recursos empresariales**", pero ¿qué significa ERP? La manera más simple de definir el ERP es pensar en **todos los procesos de negocio centrales necesarios para operar una empresa**: finanzas, RR. HH., fabricación, cadena de suministro, servicios, compras, y otros. En su nivel más básico, el **ERP ayuda a gestionar de forma eficiente todos estos procesos en un sistema integrado**. A menudo es el sistema de registro de la organización.

  </details>

N.    ¿Salesforce es un ERP?

<details><summary>Respuesta</summary>

- **Salesforce** Billing complementa las plataformas de planificación de recursos de negocio (**ERP**) mediante la conversión de los datos de la gestión de procesos desde el prospecto hasta el pedido de **Salesforce** CPQ en datos de transacciones.

  </details>


 # **EJERCICIO 7**
 
Solicitar a ariel.tarsitano@procontacto.com.mx el archivo CSV de importación para realizar este ejercicio.

Instalar la herramienta dataloader para mac o windows.

Importar el archivo obtenido del playground utilizado para resolver el ejercicio 4 y agregar los siguientes screenshots a github. 

1.	Paso a paso del proceso para mostrar cómo fue realizado.
2.	Un listado que solo muestre las cuentasimportadas, que la lista muestre una columna por cada columna del CSV. Si no se alcanza ver por el ancho de la pantalla, tomar varios screenshots.
