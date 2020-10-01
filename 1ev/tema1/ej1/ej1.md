# Ejercicio 1

1. ¿Quién es considerado el padre de la WWW? ¿En qué año sucedió y dónde?
    
        Tim Berners-Lee, científico de la computación británica.

        Estableció la primera comunicación entre un cliente y un servidor usando el protocolo HTTP en noviembre de 1989.

        La Web se desarrolló entre marzo de 1989 y diciembre de 1990​, con la ayuda del belga Robert Cailliau mientras trabajaban en el CERN en Ginebra, Suiza.


2. ¿Cuál es el principal organismo encargado de la estandarización de las tecnologías de la Web?

        W3C es el organismo internacional encargado de definir los estándares web.


3. Pon 3 ejemplos de URLs.
    
    [www.google.es](www.google.es)

    [www.xataka.com](www.xataka.com)
    
    [www.youtube.com](www.youtube.com)    

   
4. Por defecto un servidor HTTP atiende peticiones en el puerto ...
    
        80
    
5. Por defecto un servidor HTTPS atiende peticiones en el puerto ...
    
        443

    
6. Explica en detalle el proceso que se sigue desde que el usuario introduce una URL en el navegador hasta que la página es mostrada en el navegador.

        Todo comienza cuando se introduce una dirección en la barra de búsqueda del navegador.

        Cuando introducimos una dirección en la barra de búsqueda de un navegador, este dirige su URL a un router, el cual se encarga de buscar la dirección IP correspondiente para esta página web. La información necesaria se la proporciona un servidor DNS, un servidor web especial responsable de la resolución de nombres.

        El puesto intermedio entre Internet y la red local lo constituye el router. Este solicita los datos desde Internet y los distribuye entre los dispositivos de la red (ordenadores, portátiles o tablets).

        Una vez el router ha encontrado la dirección IP de la página solicitada, pide en el servidor web correspondiente los datos necesarios para mostrar la página en el navegador.
        
        
- [Fuente](https://www.ionos.es/digitalguide/paginas-web/desarrollo-web/que-pasa-cuando-se-abre-una-pagina-web/) 
    
    
7. ¿Es posible conectar a un servidor web con una aplicación que no sea un navegador Web?

        Sí. Por ejemplo, utilizando Curl y Wget.
        Son herramientas de línea de comandos que pueden acceder a archivos desde FTP, HTTP y HTTPS.


8. Un mensaje HTTP se compone de ... y …

        - La primera línea (describe la petición o su estado).
        - Los encabezados. (indica la petición o describe el cuerpo)
        - El cuerpo (lleva los datos asociados con la petición)



9. ¿Cuáles son los 4 métodos básicos HTTP y que función tienen

        - GET.          Solicita una representación de un recurso específico
        - POST.         Envía una entidad a un recurso en específico
        - PUT.          Reemplaza representaciones actuales del recurso.
        - DELETE.       Borra un recurso en específico


10. ¿Qué indican los siguientes códigos de respuesta HTTP?

        - 200 -> OK.                    La solicitud ha tenido éxito
        - 404 -> Not Found.             Recurso no encontrado
        - 503 -> Service Unavailable.   El servidor no está listo para manejar la petición


11. Explica en que consiste la arquitectura web de 3 capas.

        La arquitectura de tres capas es un diseño reciente que introduce una capa intermedia en el proceso.
        
        Cada capa es un proceso separado y bien definido corriendo en plataformas separadas.
        
        En la arquitectura tradicional de tres capas se instala una interfaz de usuario en la computadora del usuario final (el cliente).
        
        La arquitectura basada en Web transforma la interfaz de búsqueda existente (el explorador de Web), en la interfaz del usuario final.

        Capa 1: Cliente de aplicación: Navegador Web
        Capa 2: Servidor de Aplicaciones: Apache, Servidor Tomcat con servlet’s
        Capa 3: Servidor de Datos: base de datos, servidor SMTP…



12. ¿Qué significan las siglas PHP, ASP, JSP?. Donde se utilizan estas tecnologías.

- PHP. Hypertext Pre-Processor.
                
        Su uso está ligado al uso de gestores de contenido (CMS) para la modificación de páginas web dinámicas
        
- ASP. Active Server Pages

        Se utiliza para crear páginas web dinámicas (Microsoft).

- JSP. Java Server Pages

        Se utiliza para crear páginas web dinámicas (Sun Microsystem).

- ASP vs JSP

        La tecnología JSP usa Java como lenguaje de Script mientras que ASP usa VBScript o Jscript


13. ¿Qué diferencia existe entre una página web estática y una dinámica? ¿Qué tecnologías se utilizan en cada caso?

        Una Web estática (HTML, CSS) muestra una información permanente, donde el navegante se limita a obtener dicha información, sin poder interactuar con la página web visitada.

        Una web dinámica (ASP, JSP, PHP) es aquella que contiene aplicaciones dentro de la propia web, otorgando mayor interactividad con el navegante.

        Una página web estática se puede almacenar fácilmente, mientras que una dinámica no es así.


14. Si somos un proveedor de hosting y atendemos a cada vez más clientes, ¿qué tipos de escalabilidad podemos usar? Según tú, cuál de ellas sería más adecuada y por qué.

- Escalabilidad vertical.

        Significa una migración de todo el sistema a un nuevo hardware que es mas potente y eficaz que el actual.


- Escalabilidad horizontal.
        
        Consiste en potenciar el rendimiento del sistema desde un aspecto de mejora global.
        
        Se basa en la modularidad de su funcionalidad. Por ello suele estar conformado por una agrupación de equipos que dan soporte a la funcionalidad completa.

- Mejor?

        Pienso que la escabilidad horizontal es mejor, porque es más flexible a la hora de implementar las mejoras.


15. ¿Qué es un servidor dedicado?

        Es un equipo informático físico que destina todos sus recursos a proporcionar información y atender las peticiones de otro ordenador (cliente) que ha contratado sus servicios.


16. ¿Qué es un servidor compartido?

        Servidor en el que se alojan varios sitios web en el mismo equipo, de forma que los recursos de hardware son compartidos por los diferentes clientes, que disponen de un panel de control independiente.


17. ¿Qué es un VPS?

        Es una partición virtual dentro de un servidor físico que le asigna recursos exclusivos a cada partición.

        Es una solución más segura y estable que el hosting compartido donde no se obtiene espacio de servidor dedicado. Sin embargo, es de menor escala y más barato que alquilar un servidor completo


18. ¿Qué es un cloud?

        Se trata de un servicio que mediante el uso de software de virtualización nos permite disponer de un servidor completo para nuestro uso exclusivo.


19. Busca información acerca de qué se entiende por:

- IaaS

        Infraestructuras como servicio. Las empresas contratan la infraestructura de hardware a un tercero a cambio de una cuota o alquiler.

- PaaS

        Plataformas como servicios. En estas plataformas se pueden lanzar aplicaciones como bases de datos, middleware, herramientas de desarrollo, servicios de inteligencia empresarial, etc.

- SaaS

        Software como infraestructura, aloja el software de la empresa, así como sus datos, en servidores externos a la misma, y paga una cuota por su utilización.


20. Nombra 5 proveedores de cloud.

        Microsoft.
        Amazon.
        IBM.
        Salesforce.
        SAP.



21. ¿Cuál es considerado el servidor web más utilizado en el mundo?

        Apache es el servidor más utilizado actualmente.


22. Utiliza la herramienta curl para hacer peticiones HTTP desde el terminal.

- curl www.google.es
        
        Se obtiene el cuerpo de respuesta 

- curl --request GET www.google.es

        "--request" GET y "-X" GET sirven para especificar el tipo de método HTTP utilizado.

        Se obtiene el cuerpo de respuesta


- curl -X GET www.google.es

        "--request" GET y "-X" GET sirven para especificar el tipo de método HTTP utilizado.

        Se obtiene el cuerpo de respuesta


- curl -X GET -I www.google.es

        Se obtienen sólo las cabeceras, y no el cuerpo de respuesta


- curl -X GET -i www.google.es

        Se obtienen las cabeceras y el cuerpo de respuesta
