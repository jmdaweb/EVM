Note: this readme file is in spanish. Most code contained in this repository is still in portuguese. However, this situation may change in the future.

## Introducción

Este repositorio contiene el código fuente del juego Entre a vida e a morte (Entre la vida y la muerte), un audiojuego on-line cuyo objetivo es matar animales y jugadores, obtener experiencia para subir niveles, y sobrevivir. Este juego deriva de otros muchos, cuyos nombres no se citarán en este documento. Tras intensas polémicas, su código fuente se ha puesto a disposición del público bajo la GNU General Public License, versión 2, cuyo texto en inglés se puede leer en el archivo copying.txt, en la raíz de este repositorio.

## Primeros pasos

### Construcción del juego

Para compilar este juego necesitas instalar el software gratuito [Blastbay Game Toolkit](https://www.blastbay.com/bgt.php). En este repositorio encontrarás una copia del instalador de la versión 1.3. Una vez lo tengas instalado, sigue estos sencillos pasos:

1. Entra a la carpeta client.
2. Pulsa la tecla aplicaciones sobre el archivo client.bgt.
3. Pulsa enter sobre la opción "Compyle script (release).
4. Acepta el mensaje indicando que todo ha salido bien, y accede a la carpeta server.
5. Repite los pasos 2 y 3 con el fichero server.bgt.
6. Regresa a la carpeta client.
7. Pulsa aplicaciones sobre el archivo PackCreator.bgt, y pulsa enter sobre la opción "Run script".
8. ¡Todo listo! Ejecuta el archivo server.exe para activar el servidor, y el archivo client.exe para jugar. No olvides crear un usuario llamado igual que el valor de la constante ADMIN_NAME que encontrarás en el archivo config.bgt. Por defecto, si no lo has cambiado, es "admin".

### Modificación de variables

Jugar solo está muy bien. EVM ofrece un gran abanico de posibilidades, mapas para explorar y enemigos con los que luchar. Sin embargo, a veces podemos querer jugar en compañía de alguien que no esté en nuestra misma red. En estas situaciones, el servidor queda accesible desde Internet y cualquiera podría atacarlo. Las precauciones que te ofrecemos no son infalibles, pero sí tremendamente eficaces. Lo mejor de todo es que para aplicarlas sólo debes editar el archivo config.bgt con el bloc de notas.
La sintaxis de cada línea de este archivo es muy simple: `const tipo variable=valor;`
De aquí sólo nos interesan los valores, situados a la derecha. A continuación te explicamos qué hace cada variable:

* GAME_NAME: el nombre del juego. Si quieres crear tu propio juego basado en este código, puedes cambiar este valor. Recuerda respetar los términos de la GNU General Public License si lo haces.
* minversion: versión del juego.
* version: tipo de versión.
* EXECUTABLE_NAME: el nombre del fichero ejecutable del cliente. Cuando compiles el archivo client.bgt, renombra client.exe para que corresponda con el valor de esta variable.
* INSTALLER_NAME: nombre del archivo de instalación del juego.
* DOWNLOAD_URL: dirección desde la que se puede descargar el instalador del juego.
* UPDATE_URL: dirección donde se encuentra un archivo de texto plano con la versión más reciente.
* SOUND_STORAGE: nombre del archivo que almacena los sonidos cifrados.
* SOUND_ENCRYPTION_KEY: clave con la que se cifran los sonidos. Cámbiala para evitar que alguien con malas intenciones pueda quitártelos.
* COMPUTER_ID_KEY: clave con la que se cifra el identificador de la máquina. Cámbiala para evitar que los usuarios que banees puedan saltarse el bloqueo.
* serveraddress: dirección del servidor al que se conectarán los clientes.
* port: el puerto en el que escuchará el servidor. Importante, este valor no va entre comillas.
* prefsdir: ruta en la que se almacenan los ajustes del juego en modo instalable.
* PREFSFILE: nombre del archivo donde se almacenan los ajustes del cliente.
* PREFS_ENCRYPTION_KEY: clave para cifrar las preferencias. Cámbiala para que tus usuarios no puedan modificar los ajustes de una forma no permitida.
* NETWORK_ENCRYPTION_KEY: clave para cifrar y asegurar las comunicaciones en la red. Por favor, te recomendamos que la cambies, esta es una de las más importantes.
* PASSWORD_ENCRYPTION_KEY: contraseña para cifrar las claves de tus usuarios en el servidor. Muy recomendable cambiarla.
* IP_LOCALE_API_KEY: clave para utilizar la API de IpInfoDB. Debes registrarte en este servicio y escribir la tuya entre las comillas para poder geolocalizar las direcciones IP de tus usuarios. Esta función es opcional.
* IP_LOCALE_PHP_URL: dirección web del script PHP que hará las consultas al servicio IpInfoDB. Este script se incluye en la raíz del repositorio.
* portable: indica si el juego es portable o no. Admite los valores false o true, que deberán ir sin comillas y en minúscula.
* ADMIN_NAME: Nombre del administrador principal de tu juego. Debe cambiarse antes de iniciar el servidor por primera vez y nunca, bajo ningún concepto debe eliminarse ni modificarse luego.

Cuando acabes de editar este archivo y guardes los cambios, vuelve a compilar tanto el cliente como el servidor.

## Añadir a alguien como administrador

Tal vez quieras otorgar comandos de administración a alguien para que te ayude con tu juego. Para ello solo tienes que añadir un archivo con el nombre admintudo.usr dentro del directorio que contiene al personaje que deseas convertir en administrador. Los jugadores se encuentran bajo el directorio players.


## Tareas pendientes

Falta mucho por hacer en este juego, incluso en este mismo documento. Si te animas a abrir una pull request, aquí tienes sugerencias de tareas que puedes hacer:

* Redactar la documentación del usuario final. Los manuales de Desafío Mortal han sido eliminados.
* Indentar el código, de tal forma que sea más navegable y legible.
* Optimizar el código.
* Explicar qué archivos deben distribuirse a los usuarios y cuáles no.
* Dar más detalles sobre cómo montar la infraestructura web que da soporte a descargas, actualizaciones y geolocalización de ip.
* Hacer pruebas y buscar errores derivados de la supresión de componentes.
* Explicar qué archivos deben modificarse para dar permiso a un usuario en un comando concreto.
* Explicar qué archivos deben modificarse para cambiar el mensaje del día, las novedades y las reglas.
* Redactar un manual de creación de mapas.
* Explicar qué archivo del cliente debe modificarse para evitar palabras ofensivas en los chats.
* Añadir un instalador, ya sea InnoSetup o NSIS.
* Dar soporte al formato PortableApps.com para la versión portable.
