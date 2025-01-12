# Proyecto-Capstone-data-analysis
## Introducción
Bienvenido al caso práctico del análisis de bicicletas compartidas Cyclistic. En este caso práctico, realizaré muchas tareas del mundo real, típicas de un analista de datos júnior. Trabajaré para una empresa ficticia llamada Cyclistic y conoceré a diferentes personajes y miembros del equipo. Para responder a las preguntas clave de la empresa, seguiré los pasos del proceso de análisis de datos: 
* Preguntar.
* Preparar.
* Procesar.
* Analizar.
* Compartir.
* Actuar.

## Escenario
Soy una analista de datos júnior que trabaja en el equipo de analistas de marketing de Cyclistic, una empresa de bicicletas compartidas de Chicago. La directora de marketing cree que el éxito futuro de la empresa depende de maximizar la cantidad de membresías anuales. Por lo tanto, mi equipo quiere entender qué diferencias existen en el uso de las bicicletas Cyclistic entre los ciclistas ocasionales y los miembros anuales. A través de estos conocimientos, mi equipo diseñará una nueva estrategia de marketing para convertir a los ciclistas ocasionales en miembros anuales. Sin embargo, antes de eso, los ejecutivos de Cyclistic deben aprobar mis recomendaciones; por eso, debo respaldar mi propuesta con una visión convincente de los datos y visualizaciones profesionales de los mismos.

## Personajes y equipos
* **Cyclistic:** Un programa de bicicletas compartidas que incluye 5,800 bicicletas y 600 estaciones. Cyclistic se destaca por ofrecer también bicicletas reclinadas, triciclos manuales y bicicletas de carga que ofrecen un uso más inclusivo de las bicicletas compartidas para las personas con discapacidad y los ciclistas que no pueden utilizar una bicicleta estándar de dos ruedas. La mayoría de los ciclistas eligen las bicicletas tradicionales, alrededor de un 8% de los ciclistas usan las opciones asistidas. Los usuarios de Cyclistic son más propensos a utilizar la bicicleta para recreación, pero alrededor del 30% la utiliza para ir al trabajo cada día.
*	**Lily Moreno:** La directora de marketing y tu gerente. Moreno es responsable del desarrollo de campañas e iniciativas para promover el programa de bicicletas compartidas. Las campañas pueden incluir correo electrónico, redes sociales y otros canales.
*	**Equipo de análisis computacional de datos de marketing de Cyclistic:** Un equipo de analistas de datos que se encargan de recopilar, analizar e informar datos que ayudan a conducir la estrategia de marketing de Cyclistic. Te incorporaste a este equipo hace seis meses y te has dedicado no solo a conocer la misión y las metas de negocios de Cyclistic, sino también a ver cómo puedes ayudar a Cyclistic a lograrlo, desde tu posición de analista de datos júnior.
*	**Equipo ejecutivo de Cyclistic:** El equipo ejecutivo, sumamente detallista, decidirá si aprueba el programa de marketing recomendado.

## Acerca de la empresa
En 2016, Cyclistic lanzó una exitosa oferta de bicicletas compartidas. Desde entonces, el programa creció hasta alcanzar una flota de 5,824 bicicletas georreferenciadas y bloqueadas en una red de 692 estaciones en toda Chicago. Las bicicletas se pueden desbloquear desde una estación y devolverse en cualquier otra estación del sistema en cualquier momento.

Hasta ahora, la estrategia de marketing de Cyclistic se basaba en la construcción de un reconocimiento de marca general y en atraer a amplios segmentos de consumidores. Uno de los enfoques que ayudó a hacer esto posible fue la flexibilidad de sus planes de precios: pases de un solo viaje, pases de un día completo y membresías anuales. A los clientes que compran pases de un solo viaje o pases de un día completo se los llama ciclistas ocasionales. Los clientes que compran membresías anuales se llaman miembros de Cyclistic.

Los analistas financieros de Cyclistic llegaron a la conclusión de que los miembros anuales son mucho más rentables que los ciclistas ocasionales. Aunque la flexibilidad de precios ayuda a Cyclistic a atraer más clientes, Moreno cree que maximizar el número de miembros anuales será clave para el crecimiento futuro. En lugar de crear una campaña de marketing que apunte a todos los clientes nuevos, Moreno cree que hay muchas posibilidades de convertir a los ciclistas ocasionales en miembros. Ella señala que los ciclistas ocasionales ya conocen el programa de Cyclistic y han elegido a Cyclistic para sus necesidades de movilidad.

Moreno estableció una meta clara: Diseñar estrategias de marketing orientadas a convertir a los ciclistas ocasionales en miembros anuales. Sin embargo, para hacer eso, el equipo de analistas de marketing necesita entender mejor cómo difieren los miembros anuales y los ciclistas ocasionales, por qué los ciclistas ocasionales comprarían una membresía y cómo los medios digitales podrían afectar sus tácticas de marketing. Moreno y su equipo están interesados en analizar los datos históricos de viajes en bicicleta de Cyclistic para identificar tendencias.

## Tarea empresarial
Moreno me asignó esta pregunta: ¿En qué se diferencian los socios anuales y los ciclistas ocasionales con respecto al uso de las bicicletas de Cyclistic?
Debo hallar diferencias clave entre ambos grupos de ususarios, que puedan ayudar a averiguar como hacer que los ciclistas ocasionales prefieran hacerse miembros, y como los medios digitales podrían afectar a las tácticas de marketing de Cyclistic.

## Fuentes de datos

Los datos utilizados en este proyecto fueron proporcionados por [Motivate International Inc.](https://divvy-tripdata.s3.amazonaws.com/index.html) bajo una [licencia pública](https://divvybikes.com/data-license-agreement). Estos datos han sido adaptados para el caso práctico de Cyclistic, una empresa ficticia.
Los datos históricos de viajes en bicicleta cubren los últimos 12 meses, y fueron descargados en formato CSV desde el sitio oficial proporcionado, con cada archivo representando un mes. Los conjuntos de datos incluyen información detallada sobre los viajes, como la hora de inicio y fin, la duración, el tipo de bicicleta utilizada (clásica o eléctrica) y el tipo de usuario (miembro o usuario ocasional).

* Los datos son públicos y están disponibles bajo una licencia específica. Se ha respetado esta licencia y no se ha utilizado ninguna información de identificación personal en el análisis.

* Los datos están organizados en formato CSV, con columnas que incluyen identificadores de viaje, tiempos de inicio y fin, estaciones de origen y destino, tipo de bicicleta y tipo de usuario.

* Los datos son considerados confiables ya que provienen de una fuente oficial ampliamente reconocida. Además, se verificó la consistencia de las fechas y duraciones de los viajes, asegurando que los datos representan adecuadamente el comportamiento de los usuarios de bicicletas compartidas.

## Limpieza y manipulación de los datos

**En Excel:**
* Elimino filas duplicadas y columnas irrelevantes como *start_lat, start_lng, end_lat y end_lng*.
* Agrego dos nuevas columnas, una para el tiempo de duración del viaje llamada *ride_length*, otra para el día de la semana con números del 1 al 7 llamada *day_of_week*.
* Elimino todas las filas donde la duración de la columna *ride_length* dure menos de un minuto o más de 24h, me ayudo ordenando la columna en orden ascendente.
* Compruebo que todas las columnas estén en el formato adecuado, para *ride_length* elijo el formato de hora 37:30:55, que me permite contar diferencia de tiempo en horas pero también en días. Para el resto de columnas uso formato general, y numérico para columnas numéricas.
* Compruebo que las columnas importantes no contengan celdas vacías.
* Hago los mismo para las doce hojas correspondientes a cada mes del año.

  
**En R:**
* Desfragmento la columna *started_at* y *ended_at*, cuyo formato era dd/mm/yyyy hh:mm:ss, y saco a raíz de ella las columnas para el mes del año, otra para el día del mes y otra para el año.

```{r}
# Cargar un paquete
library(ggplot2)
```

* Ensamblo todas las hojas en una sola vista.
* Renombro las columnas de la siguiente manera:
  - ride_id = trip_id
  - rideable_type = bikeid 
  - started_at = start_time, month, day_of_week, ride_length, year, day_of_month
  - ended_at = end_time, month, day_of_week, ride_length, year, day_of_month
  - start_station_name = from_station_name 
  - start_station_id = from_station_id 
  - end_station_name = to_station_name 
  - end_station_id = to_station_id 
  - member_casual = usertype







