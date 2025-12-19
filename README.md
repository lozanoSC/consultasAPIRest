# consultasAPIRest
Este proyecto contiene código que:
- utiliza un cliente http sencillo, concretamente httpClient de java. Viene incluido en JDK desde versión 11 y por tanto se puede usar desde Kotlin si kotlin esta usando un JDK 11 o superior. El cliente se usa para obtener datos Json de un api rest pública
- los datos obtenidos se deserializan a objetos que pertenecen a dataclass que reflejan la estructuran del json. concretamente obtenemos una lista de usuarios. Para poder hacer esto tendremos que configurar build.gradle.kts
- sobre lista podemos hacer consultas, en este caso simplemente se barrre la lista y se imprimen campos de usuarios

## conceptos de repaso
Seguramente ya los viste a fondo en otro módulo, repasamos lo mínimo para situarnos en nuestro proyecto

**servidor web**
Es el software que recibe peticiones HTTP y envía respuestas. Se encarga de escuchar en un puerto y gestionar las solicitudes entrantes.
Ejemplo: Apache o Nginx.

**servicio web**
Es una aplicación que ofrece funcionalidades a través de la red, ejecutándose normalmente sobre un servidor web. Puede devolver datos, ejecutar lógica o acceder a bases de datos.
Ejemplo: un servicio que permite consultar alumnos almacenados en una base de datos.

**API REST**
Es un conjunto de reglas y estructura que define cómo un servicio web expone sus recursos usando HTTP, siguiendo principios REST (recursos, métodos HTTP, URLs claras).

En el lenguaje común aunque no sea preciso, se utiliza también el término API REST como servicio web. Por ejemplo, "Hice una API REST", sería más correcto decir, "hice un servicio web API REST", o mejor aún ,  "hice un servicio web  que cumple estructura según normas API REST". Así que a efectos prácticos, aunque no sea del todo correcto, usamos API REST como sínonimo de servicio web API REST.



**recurso y endpoint**

Un recurso, de forma simplificada, se refiere a un dato al que podemos acceder a través del API REST, o visto de otra forma, un dato que el API REST expone al exterior

Es la URL concreta que identifica un recurso o una operación dentro de una API REST.
Ejemplo: /api/alumnos/5 es el endpoint que representa al alumno con id 5.

**método HTTP**

Indica qué acción se quiere realizar sobre un recurso dentro de una API REST. Los métodos son funciones que pertencen al standard del protocolo http.
Ejemplo: GET para obtener datos, POST para añadir un dato.



**cliente API REST**

Es la aplicación que consume una API REST, enviando peticiones HTTP y procesando las respuestas.
Ejemplo: un navegador, o en nuestro caso una app kotlin de consola que hace petición GET.





## Configuración del proyecto
- crea un proyecto con build Gradle
- configura build.gradle.kts para poder deserializar(convertir) el String Json a clases Kotlin
    -  en plugins:  *kotlin("plugin.serialization") version "1.9.22"*
    -  en dependencias:  *implementation("org.jetbrains.kotlinx:kotlinx-serialization-json:1.6.3")*

![imagenkts](imagenkts.png)
no olvides recargar la configuración del kts. Mientras visualicemos el icono de load es que quedan cargas pendientes

## Generar las clases Kotlin receptoras de la deserialización.
Se pueden escribir a mano cuando el Json es sencillo, o bien,  usar herramientas automáticas utilizando uno de los  plugins de IntelliJ para tal fin,  usando una IA, etc. 
## SE PIDE
Que de forma análoga al código ejemplo:
- eligas una api rest. Puedes utilizar la del ejemplo pero estaría bien que investigues y uses otra si tienes tiempo. 
- obtengas datos json desde kotlin
- los deserialices desde kotlin
- y ejecutes sobre ellos tres o cuatro consultas interesantes. Procura que no sean tan simples como la del ejemplo y que usen ordenar, agrupar, mapear, etc.

