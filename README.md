
************************
****** 1. Introducción ******
************************

Se va a detallar un POC para una solución cuya principal característica es la capacidad de convertir una moneda fiduciaria en un token, y viceversa, de manera fácil y rápida, siguiendo todas las regulaciones y leyes definidas. 
Esta prueba de concepto se elabora con el fin de determinar su factibilidad e impacto, dentro de unos escenarios representativos. Nos centraremos en definir la planificación, sin implementación.

Los componentes claves del proyecto sobre los que desarrollaremos una tecnología, arquitectura, equipo y cultura son:
- Finalidad: crear una app puntera, y posicionarla en el top de mercado en cuanto a producto relacionados .
- Objetivo: hacerlo de forma rápida, reduciendo gastos y obteniendo un resultado pulido, amigable para el usuario y con un rendimiento óptimo.
- Destinatarios: nuestro target serán personas que quieran manejarse en el mundo del blockchain, ya sean principiantes o expertos.
- Calendario: 4 meses de duración.
- Recursos disponibles: disponemos tanto de recursos humanos como materiales suficientes para abordar el proyecto de forma muy competitiva.
- Resultado: cumplir con nuestros objetivos, crear un buen producto, hacer que el equipo se sienta cómodo y se implique.

 
************************
****** 2. Tecnologías ******
************************

Para elegir las tecnologías más acertadas en nuestro proyecto, debemos tener en cuenta dos factores clave, que tipo de proyecto es, y que materias disponemos para crear el proyecto.
En este caso tenemos un proyecto que va a operar con dinero fiduciaria, con lo cual la seguridad es algo a tener muy en cuenta. 
También es un proyecto interno de la empresa, es decir, no dependemos de ningún cliente que nos exponga unos requisitos, esto nos da más libertad a la hora de elegir las tecnologías y optar por las que mejor se adapten a nuestras capacidades, por lo cual es una clara ventaja.

Los riesgos a los que nos enfrentamos frente a la tecnología son:
- Apego a las políticas de seguridad.
- Dependencias que el equipo del proyecto no controla.
- Tecnologías nuevas o poco probadas, y que falte documentación.

Para elegir las tecnologías más adecuadas, vamos a tener en cuenta las ventajas de cada una en las distintas capas del proyecto, teniendo en cuenta el tipo de proyecto, los recursos de los que disponemos y el tiempo. 
Para abaratar costos, sin que interfiera en la calidad del producto final, todas las tecnologías van a ser OpenSource.
 

------------------------
-----> Base de Datos <-----
------------------------

Las bases de datos suelen ser una de las piezas más importantes en cualquier instalación. Esto es debido a su uso como principal repositorio de datos. Estos datos tienen dos características que los hacen vitales para cualquier negocio.
- Sin ellos nuestro negocio no podría funcionar.
- Son datos que deben poder ser accedidos en tiempo real por todos nuestros clientes.

Entre BDD relacionales y no relacionales nos decantamos por una BDD relacional, ya que los datos deben de ser consistentes sin dar posibilidad a error.


***** ---------------> POSTGRESQL  <--------------- *****

En este caso hemos elegido PostgreSQL, debido a que proporciona una copia de seguridad en línea, proporciona tanto tablas temporales como vistas materializadas y el lenguaje de programación es altamente extensible. 
Además, es una base de datos robusta y admite muchas consultas largas y frecuentes. 
La frecuencia en nuestro proyecto es un factor a tener en cuenta, ya que si trabajamos con un sistema que bloquea las tablas temporalmente y debemos mover gran cantidad de datos frecuentemente, el rendimiento no será bueno.

+ Ventajas
- Instalación ilimitada y gratuita: Es un sistema multiplataforma.
- Estabilidad y confiabilidad: Tiene más de 20 años de desarrollo activo y en constante mejora. No se han presentado nunca caídas de la base de datos. Permite que los clientes puedan realizar consultas de solo lectura mientras que los servidores están en modo de recuperación o espera.
- Estándar SQL: Implementa casi todas las funcionalidades del estándar ISO/IEC 9075:2011, así pues, resulta sencillo realizar consultas e incluir scripts de otros Motores de Bases de Datos.

+ Desventajas
- Es relativamente lento en inserciones y actualizaciones en bases de datos pequeñas.
- Soporte oficial: No cuenta con un soporte en línea o telefónico. PostgreSQL cuenta con foros oficiales donde los usuarios pueden exponer sus dudas que responden otros usuarios de la comunidad y cabe resaltar que la comunidad de usuarios PostgreSQL es una de las más activas en el mercado.

La segunda opción era MySQL, aunque la decisión ha sido difícil, ya que ambas bases de datos tienen características similares, y en la comparativa entre ambas no hay grandes diferencias.
Quizás MySQL este enfocado a proyectos más pequeños, no es tan eficaz en aplicaciones que requieran de una constante modificación de escritura en BDD, y además, aunque este respaldado por Oracle, esto puede suponer un problema si en un futuro deciden privatizarlo.


------------------------
-----> Back  <-----
------------------------

Las tecnologías backend son indispensables en la creación, ejecución y administración de aplicaciones modernas. 
De hecho, seleccionar el backend adecuado puede marcar la diferencia entre el éxito o el fracaso de los proyectos de desarrollo de aplicaciones. 
La tecnología de backend adecuada mejora las operaciones de la aplicación sin problemas al mejorar la velocidad, la escalabilidad y la capacidad de respuesta de la aplicación. 
En este proyecto unos de los factores a tener en cuenta es que habrá varios servicios que admitirán tanto las funciones móviles como el flujo comercial.


***** ---------------> JAVA <--------------- *****

Se ha elegido Java, porque es uno de los lenguajes más puntero, además se adapta perfectamente a las necesidades del proyecto, y todo el equipo tiene soltura con la tecnología.
Podemos destacar lo siguiente:

+ Ventajas:
- Escalable y sencillo: los componentes están fácilmente disponibles, y la sintaxis es fácil de entender.
- Tiene muchas bibliotecas de código abierto
- Es conocido por su estricta seguridad, muy importante para el fin del proyecto.
- Facilidad para hacer pruebas.
- Se adapta perfectamente a Ethereum. Para implementar aplicaciones basadas en Ethereum en el mundo Java se usa la la biblioteca web3j , que es una biblioteca Java muy ligera y reactiva para Java.
- Es compatible con una API de KYC.

+ Desventajas:
- El alto costo de los requisitos de hardware hace que la implementación de backend con tecnología Java sea costosa.

Además, lo acompañaremos de los siguientes Frameworks:
 - Spring Boot, para facilitar su creación (Maven), la inyección de dependencias y el despliegue en el servidor.
 - Spring: acceso a datos (JDBC, Marshalling XML)
 - JPA

Y para la parte de Test Unitarios usaremos:
 - JUnit y Mockito, para hacer pruebas de cobertura.

La finalidad de usar esta tecnología es crear una REST API para que la aplicación móvil conecte con ella y poder usar toda su lógica de negocio.
La segunda opción era Phyton, debido a su adaptabilidad, pero se descartó porque las pruebas son muy exhaustivas a la hora de encontrar errores y porque depende en gran medida de bibliotecas y marcos de trabajo de terceros.

Recomendación IDE: IntellIJ


------------------------
-----> Front <-----
------------------------

En cuanto a las tecnologías frontend, lo primero a tener en cuenta es que es una aplicación móvil, compatible tanto con iOs como con Android. 
Así que tenemos dos opciones, o bien crear dos códigos iguales pero cada uno en su correspondiente lenguaje nativo, o un código que sirva para ambos. E
legimos hacer un desarrollo cuyo código sea adaptable a ambas, incluso en un futuro como aplicación web. 

Vamos crear la aplicación con el Framework Flutter, que a partir de un solo código es capaz de compilar una aplicación nativa para cada plataforma. Flutter está basado en Dart.


***** ---------------> Dart <--------------- *****

Es un lenguaje de programación desarrollado por Google, cuyo fin es convertirse en una modernización del clásico JavaScript. Igual que JavaScript se ejecuta directamente sobre el navegador.
Dart está pensado para ofrecer mejores resultados mediante alternativas a algunos problemas de JavaScript. Pretende ser una herramienta sencilla para proyectos más grandes y ofrecer una mejor seguridad. Todo esto encaja perfectamente con las necesidades del proyecto.

+ Ventajas: 
- Detrás de la programación Dart se encuentra el gigante Google, lo que ofrece perspectivas a largo plazo para el desarrollo del lenguaje. 
Debido a su sintaxis, este lenguaje es fácil de aprender para los programadores debido a que los desarrolladores han simplificado muchas características complicadas de otros lenguajes y las han combinado de manera inteligente. 

+ Desventajas:
El lenguaje de programación Dart es relativamente nuevo, lo que implica una comunidad de soporte aún bastante reducida y una disponibilidad de materiales de aprendizaje inferior a JavaScript.


***** ---------------> Flutter<--------------- *****

La estrategia de Flutter, todo es un widget, sigue las bases de la programación orientada a objetos hasta la interfaz de usuario: la interfaz del programa consta de diferentes widgets que pueden estar anidados entre ellos. 
Cada botón y texto mostrado es un widget. Estos cuentan con diferentes propiedades que se pueden modificar.
Los widgets pueden interactuar entre sí y reaccionar a cambios de estado externos mediante sus funciones integradas.
Todos los elementos importantes de la interfaz de usuario incluyen widgets que se corresponden con los diseños de Android y iOS o las aplicaciones web convencionales.
Si se desea, estos widgets se pueden ampliar con funciones adicionales o se pueden crear widgets propios que se pueden combinar fácilmente con los ya existentes.

+ Ventajas:
- Una única base de código para las principales plataformas de destino. Compila en nativo, tanto en Android como en iOS.
- Lenguaje de programación Dart fácil de aprender.
- El paradigma todo es un widget ofrece numerosas posibilidades.
- Ejecución potente de las aplicaciones nativas en los smartphones.
- Bibliotecas amplias con elementos de interfaz gráfica prefabricados.

+ Desventajas:
- El código del programa puede volverse confuso al integrar los widgets.
- En caso de actualizar aspectos del diseño en los sistemas operativos, hay que actualizar los módulos Flutter. Como los módulos se integran en el programa de manera fija, también hay que compilar el programa e instalarlo en los dispositivos.

Pruebas Unitarias: Flutter test
Recomendación de IDE: Visual Studio Code
 

------------------------
-----> Blockchain <-----
------------------------

***** ---------------> Ethereum <--------------- *****

Se ha elegido Ethereum puesto que su web es muy completa, las explicaciones abarcan muchos elementos, hay muchos desarrolladores trabajando en ella y al ser código libres está en continuo crecimiento. Es la segunda moneda detrás del Bitcoin. 
La programacion con Ethereum tiene su base en los Contratos Inteligentes. Un "contrato inteligente" es básicamente un programa que se ejecuta en la blockchain de Ethereum. Tambien son un tipo de cuenta de Ethereum. 
Un gran aspecto de Ethereum es que los contratos inteligentes pueden programarse utilizando lenguajes relativamente fáciles para el programador.
Además no solo sirven como bibliotecas de código abierto, esencialmente son servicios de API abierta que funcionan ininterrumpidamente y no se pueden dar de baja.


***** ---------------> Solidity <--------------- *****

Se ha elegido Solidity, comparándolo con Vyper puesto que es más rápido para poner en marcha, ya que tiene más soporte y más documentación. 
Vyper es más auditable, pero tiene menos documentación. Además porque Solidity está influenciado por JavaScript, que es un lenguaje que conocen todos los desarrollados, además que la escritura de contratos está orientada a objetos, otro lenguaje que también conoce todo el equipo.

Ethereum ya tiene unos contratos accesibles y transparentes ósea que la app podría usar alguno de estos contratos, pero también podría surgir la necesidad de crear contratos personalizados o adaptados. 
Como desarrollador de dapps, deberás escribir contratos inteligentes solo si deseas agregar una funcionalidad personalizada a la blockchain de Ethereum.

Además, lo acompañaremos del Framework:
 - Truffle Suite Un entorno de desarrollo y de pruebas, un proceso de creación y otras herramientas.
	o Truffle Teams
	o Truffle
	o Ganache, es una herramienta para la simulación y testeo de Blockchain.
	o Drizzle, es una colección de «librerías front-end» que hacen que el desarrollo de front-ends para «Dapps» sea más fácil y predecible.

Recomendación de IDE: Remix.


------------------------
-----> Pruebas <-----
------------------------


Dado a la delicadeza de los servicios que se van a implementar en la App donde los movimientos de dinero va a ser la función principal, no nos podemos permitir ningún error, por eso las pruebas son una parte crucial del proyecto.
 - Integración: FLUTTER DRIVE. Proporciona herramientas para crear aplicaciones instrumentadas e impulsar esas aplicaciones desde una suite de tests.
 - Regresión: tenemos que tener presente que cualquier cambio en el código de una aplicación, por pequeño e inofensivo que parezca, puede tener consecuencias inesperadas. 
   Prueban que los test unitarios y funcionales siguen funcionando a lo largo del tiempo (se pueden lanzar tanto de forma manual como en sistemas de Integración Continua). 
 - Rendimiento (carga y estrés): LOADVIEW. Prueban la eficiencia del código.
 - Memoria: los dispositivos móviles vienen con memoria limitada, este tipo de prueba se realiza para probar el uso de memoria optimizado por una aplicación.
 - Instalación: asegurar que la instalación se pueda realizar en todas las versiones de sistema operativo requeridos y en caso de tratarse de la actualización, que este pueda realizarse exitosamente y sin alterar los datos y configuraciones del usuario. También se incluye la desistalación.
 - Interrupción: que aseguren un manejo de interrupciones correcto tales como llamadas entrantes, alarmas y notificaciones de otras aplicaciones.
 - Conexión a red: capacidad de soportar cambios frecuentes entre redes Wi-Fi, datos móviles y periodos intermitentes de desconexión.
 - Usabilidad: Evitar pantallas muy cargadas o con pobres métodos de. Así mismo es conveniente asegurar el apego a estándares como por ejemplo Material Design.
 
Para todas las pruebas anteriores se ha decicidio usar la herramienta de APPTIM, ya que permite a los desarrolladores y evaluadores de dispositivos móviles probar fácilmente sus aplicaciones y analizar su rendimiento para evitar que se activen problemas críticos. 
• Pruebas de aplicaciones nativas
• Informes de rendimiento y errores
• Integración JIRA


------------------------
-----> Control de Versiones <-----
------------------------

GIT, con metodología Git Flow.


************************
****** 3. Arquitectura ******
************************

La arquitectura de software es un método que se utiliza de base para el diseño de las diferentes funcionalidades. De esta forma proporcionamos agilidad en el desarrollo además de obtener una performance óptima. 

***** ---------------> DDD, Domain-Driven Design  <--------------- *****

DDD es un concepto que propone que la estructura y lenguaje en el código del software (nombres de clases, métodos y variables) debería reflejar el dominio de negocio.
 Por ejemplo, en un software de eventos debería haber clases para el concepto de evento, recinto, tipos de entrada métodos como crear evento, cambiar fecha de evento, cancelar o posponer entre otros. 
DDD intenta evitar la existencia de modelos anémicos con poca lógica de negocio o conceptos exclusivamente técnicos. DDD define dos tipos de patrones, los estratégicos que hacen referencia a aspectos de negocio y los patrones tácticos más relacionados con detalles de implementación.

Una arquitectura hexagonal con diseño DDD sería comprensible para todos los miembros del equipo, independientemente de su rol.
La arquitectura hexagonal aísla e independiza al modelo de dominio de los elementos externos con el objetivo de que, aunque los elementos externos cambien estos no afecten al modelo y de que se puedan hacer cambios en el dominio los elementos externos requieran los menores cambios necesarios.
Una gran ventaja de la arquitectura hexagonal es que los puertos y adaptadores no hace falta implementarlos al mismo tiempo que el dominio, el dominio solo ha de definir la interfaz que necesita y con posterioridad es posible realizar la implementación del adaptador en concreto que realice la persistencia. 
Esto permite retrasar la toma decisiones hasta tener más conocimiento de la solución más adecuada.
Todo ello aderezado con técnicas de código limpio, TDD, BDD, etc… Si aplicamos todo esto de forma adecuada, como he dicho al principio, el proyecto “crece fuerte”, y no solo fuerte, también seguro, robusto, y escalable .
Cuando una aplicación comienza a ser compleja debemos mantener la máxima de alta cohesión y bajo acoplamiento. Así que, para ello, lo que hacemos es agrupar conceptos dentro del modelo de dominio.
 

************************
****** 4. Equipo ******
************************

Se ha definido el equipo teniendo en cuenta que hay que tener especial cuidado con la parte de Seguridad y con la parte legal del dinero fiduciario. 

- 1 Jefe de Proyecto / Product Owner / Scrum Master: (30% de disponibilidad durante todo el proyecto). Se encargará de dirigir los Dailys y de verificar en todo momento el avance del proyecto.
- 1 Analista / Especialista en Blockchain. En un primer momento, se centrará en la parte de análisis, y luego apoyará en la parte de desarrollo relacionada con Blockhain y Ethereum/Solidity.
- 1 Desarrollador senior Fullstack. Su rol será de líder de equipo, y que tenga amplios conocimientos en Java, para que sea el referente en este lenguaje. Se apoyará en los desarrolladores que manejan Flutter para ampliar sus conocimientos.
- 2 Desarrolladores Fullstack. Sobre todo que tengan conocimientos avanzados en Flutter, aparte de Java.
- 1 Desarrollador Fullstack Junior. Que tenga nociones básicas de Java y JavaScript.
- 1 QA: Entrará a partir de la segunda quincena de desarrollo, y tendrá una dedicación del 50%.
- 1 Diseñador UIX. El primer mes tendrá una dedicación del 100%, el resto del proyecto tendrá una disponibilidad del 20% por si surgieran cambios o disyuntivas.

 
************************
****** 5. Cultura ******
************************

 - Se usarán metodologías ágiles en este caso Scrum, donde se incluyen:
	o Dailys diarias para hablar sobre el avance del proyecto, y comentar si hay problemas. Serán los propios desarolladores los que se dividan las tareas, teniendo como referentes al líder y al analista en caso de duda.
	o Sprint. De dos semanas de duración, con sus correspondientes initial planning, reviews y retrospective.
 - Control de Desarrollo y reparto de Tareas: Jira.
 - Uso de buenas prácticas.
 - Todos los viernes se hará un desayuno online para crear vínculo entre el equipo.
 - Revisión salarial al finalizar el proyecto, si todo sale perfecto. Será para todos el equipo, para que se sientan valorados y recompensar su esfuerzo y trabajo.
 - En condiciones de equidad de conocimientos, intentar tener equipos formados por personas diversas, ya que todos somos iguales pero diferentes, y eso hace que cada uno tenga su punto de vista y al final sume.



