# Tomcat

#### Raúl Morales Ruiz

---

## Introducción

El objetivo de este manual es instalar Tomcat y configurarlo correctamente.

## Requisitos

- Tener instalado [Java](https://www.java.com/es/).

## Conceptos

A continuación se definen unos conceptos básicos sobre Tomcat.

### Qué es Tomcat

Tomcat es un contenedor de servlets que se utiliza en la Referencia oficial de la implementación para Java Servlet y JavaServer Pages (JSP). Las especificaciones Java Servlet y JavaServer Pages son desarrolladas por Sun Microsystems cuyas especificaciones vienen dadas por la JCP (Java Community Process).

Apache Tomcat es desarrollado en un entorno abierto y participatorio, bajo la licencia de Apache Software License.

### Estructura de directorios

- bin - arranque, cierre, y otros scripts y ejecutables.
- common - clases comunes que pueden utilizar Catalina y las aplicaciones web.
- conf - ficheros XML y los correspondientes DTD para la configuración de Tomcat.
- logs - logs de Catalina y de las aplicaciones.
- server - clases utilizadas solamente por Catalina.
- shared - clases compartidas por todas las aplicaciones web.
- webapps - directorio que contiene las aplicaciones web.
- work - almacenamiento temporal de ficheros y directorios.

### Ficheros de configuración

Los ficheros de configuración se encuentran en la carpeta conf.

Breve descripción de cada uno:

- server.xml: fichero principal de configuración.
- web.xml: fichero en formato estándar para aplicaciones web con servlets, que
  contiene la configuración global a todas las aplicaciones.
- tomcat-users.xml: lista de usuarios y contraseñas para autentificar.
- catalina.policy: políticas de seguridad para la ejecución del servidor.
  Además se pueden cambiar ciertos aspectos de la configuración a través de la aplicación de
  administración

## Instalación

- En primer lugar, debemos actualizar los paquetes:

        sudo apt update

- Instalaremos los paquetes principales, correspondientes al núcleo de Tomcat y a las aplicaciones administrativas:

        sudo apt install -y tomcat9 tomcat9-admin

Adicionalmente puedes instalar el paquete tomcat9-docs para disponer de la aplicación de documentación integrada de Tomcat 9, y el paquete tomcat9-examples si quieres tener algunos ejemplos de aplicaciones básicas funcionando en Tomcat 9.

- Comprobamos que Tomcat se ha instalado correctamente

        systemctl status tomcat9

## Configuración

Vamos a configurar Tomcat 9 en Ubuntu 20.04 LTS antes de hacer ninguna prueba, ya que para trabajar con las aplicaciones administrativas no basta la configuración por defecto.

### Puerto de conexión

Por defecto, Tomcat 9 espera conexiones en el puerto 8080. El problema que podría surgir de esta configuración es que exista previamente otra aplicación utilizando dicho puerto, como un proxy, o que simplemente quieras usar un puerto distinto.

Podemos cambiar el puerto de escucha editando el archivo server.xml:

> sudo nano /etc/tomcat9/server.xml

Buscaremos la siguiente directiva Connector:

        ...
        <Connector port="8080" protocol="HTTP/1.1"
                connectionTimeout="20000"
                redirectPort="8443" />
        ...

### Gestión de usuarios

Algunas aplicaciones de Tomcat 9, como las aplicaciones administrativas, requieren el acceso autenticado de usuarios con cierto nivel de privilegios o roles.

Podemos crear los usuarios que consideremos con contraseña y con uno o ambos roles, en este caso será un solo usuario con ambos roles, para lo que editaremos el archivo tomcat-users.xml:

> sudo nano /etc/tomcat9/tomcat-users.xml

Antes del cierre del bloque tomcat-users añadiremos una definición de usuario con contraseña y los roles necesarios:

        ...
                <user username="usuario" password="XXXXXXXX" roles="admin-gui,manager-gui"/>
        </tomcat-users>

### Acceder a Tomcat 9

Como tendrás ganas de verlo en acción, vamos a acceder a Tomcat 9 en Ubuntu 20.04 LTS, desde un navegador, para lo que indicaremos la dirección IP o nombre de la máquina y el puerto de conexión, que en la configuración estándar es el 8080.

> http://localhost:8088

### Acceder a la documentación

Si decidiste instalarla, en la ruta /docs/, se puede visitar la documentación integrada de Tomcat 9:

> http://localhost:8088/docs

Habrás observado que para acceder a esta aplicación no se nos ha solicitado ningún tipo de autenticación, ni hemos tenido que permitir explícitamente acceso desde red.

### Administración de Tomcat 9

Sin embargo, si intentamos acceder al Gestor de Aplicaiones Web, aplicación /manager/html, sí que se nos solicita autenticación:

> http://localhost:8088/manager/html

Introduciremos el nombre y la contraseña del usuario que creamos con el rol manager-gui para poder acceder, y se mostrará el «Gestor de Aplicaciones Web de Tomcat», donde podrás desplegar, replegar, iniciar o detener aplicaciones web servidas desde Tomcat 9:

### Desplegar aplicaciones

Si dispones de un arhivo .war correspondiente a una aplicación que quieras desplegar en Tomcat 9 sobre Ubuntu 20.04, entra en el Gestor de Aplicaciones Web de Tomcat y desplázate hasta la sección «Desplegar«, concretamente al recuadro «Archivo WAR a desplegar«. Utilizando el botón «Seleccionar archivo» podrás buscar el archivo .war en el sistema de archivos.

Cuando el archivo esté seleccionado, pulsa el botón «Desplegar«. La aplicación será desplegada y se recargará el Gestor de Aplicaciones, mostrando el resultado de la operación y, si todo ha ido bien, la nueva aplicación aparecerá en la lista de aplicaciones, junto a sus controles de gestión.

Para probar la nueva aplicación bastará con seguir el enlace que aparece en la misma lista de aplicaciones, que será el enlace que facilitaremos a nuestros usuarios.
