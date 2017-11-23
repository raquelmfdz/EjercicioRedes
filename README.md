#### Ejercicio Redes (ENUNCIADO)
Realizar utilizando Cisco Packet Tracer el siguiente ejercicio:

Crear cinco redes:
- Crear tres subredes (VLSM), una que soporte 100 host, otra que soporte 30 y por último una para 6 host. Sólo esta última podrá salir fuera. Cada una tendrá cuatro ordenadores conectados.
- 8 ordenadores con DHCP.
- 4 ordenadores con DHCP.
- 4 ordenadores con IP fija, un punto de enlace con 5 ordenadores con DHCP.
- 5 ordenadores con IP fija.

Todas las redes estarán conectadas mediante routers.
Tendremos tres servidores web:
- www.albacete.es : muestra una foto de Albacete.
-	www.wagner.de : muestra una foto de Wagner.
-	www.dilar.com : muestra una toto de Dílar.

Existirá un servidor DNS para resolver los nombres anteriores.  
Todas las redes deben estar etiquetadas.  

En el archivo PDF adjunto se detallan en las tablas las IP’s utilizadas en el ejercicio. ¡ATENCIÓN! En la tabla adjunta en el PDF hay un error en la última subred. La submáscara de la misma es: 255.255.255.248 (ya que al aplicar la fórmula obtenemos 3 bits apagados para el host y 5 encendidos para la red).
***
###### PREBASES

- Conectaremos 2 redes por cada router y luego conectaremos los routers mediante sus puertos seriales.
- Todas las IP’s han sido inventadas a excepción de las propias de cada subred que han seguido el procedimiento del subnetting VLSM.

1º) En el primer apartado del ejercicio, dividimos nuestras redes mediante su propia submáscara, de manera que quedan invisibles entre sí. Como queremos que la última subred sea la que salga, asignaremos una de sus IP's a uno de los puertos del router. En el puerto restante, colocaremos una IP procedente de la otra red a la que queremos conectar nuestra subred.

2º) Para la parte del ejercicio que usa el punto de acceso (o punto de enlace), necesitaremos añadir una tarjeta de red a los ordenadores que vayan a conectarse, conectarlos a nuestro punto de acceso y configurar cada ordenador para que tenga el modo DHCP.

3º) Conectaremos un router por cada 2 redes máximo y lo configuramos para enrutar con sus redes y con el resto de routers existentes.

4º) Para el último apartado necesitaremos un servidor con servicio WEB por cada página y otro con servicio DNS. Configuraremos todos los servidores WEB para que conecten con el servidor DNS. Una vez tengamos estos pasos realizados, configuraremos el resto de ordenadores pertenecientes a cada red para que conecten con el servidor DNS y así podamos acceder desde cualquier ordenador a cualquiera de los dominios web configurados. Los servidores usarán las siguientes IP’s:

- SERVIDOR DNS -> 190.10.10.11
- SERVIDOR WEB - Albacete -> 190.10.10.12
-	SERVIDOR WEB - Wagner -> 190.10.10.13
- SERVIDOR WEB - Dílar -> 190.10.10.14
-	PUERTA DE ENLACE (GATEWAY) -> 190.10.10.1 (Se corresponde con el router que conecta la red donde se encuentran los servidores con el resto de redes).

5º) Habrá que comprobar un par de veces la conectividad entre dos elementos de diferente o misma red debido a que el programa suele dar errores con las primeras comprobaciones. Al comprobar la conexión con los dominios web, hay que darle un poco de tiempo para que cargue las imágenes asignadas a cada dominio.
