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

## Limpieza y manipulación de los datos en R

* Install required packages
* tidyverse for data import and wrangling
* lubridate for date functions
* ggplot for visualization
```{r}
library(tidyverse)  #helps wrangle data
library(lubridate)  #helps wrangle date attributes
library(ggplot2)  #helps visualize data
getwd() #displays your working directory
setwd("/Users/carme/Desktop/Datos_Divvy/CSV") #sets your working directory to simplify calls to data ... make sure to use your OWN username instead of mine ;)
```
* Upload Divvy datasets (csv files) here
```{r}
enero <- read_csv("202401-divvy-tripdata.csv")
febrero <- read_csv("202402-divvy-tripdata.csv")
marzo <- read_csv("202403-divvy-tripdata.csv")
abril <- read_csv("202404-divvy-tripdata.csv")
mayo <- read_csv("202405-divvy-tripdata.csv")
junio <- read_csv("202406-divvy-tripdata.csv")
julio <- read_csv("202407-divvy-tripdata.csv")
agosto <- read_csv("202408-divvy-tripdata.csv")
septiembre <- read_csv("202409-divvy-tripdata.csv")
octubre <- read_csv("202410-divvy-tripdata.csv")
noviembre <- read_csv("202411-divvy-tripdata.csv")
diciembre <- read_csv("202412-divvy-tripdata.csv")
```
* Compare column names each of the files
* While the names don't have to be in the same order, they DO need to match perfectly before we can use a command to join them into one file
```{r}
colnames(enero)
colnames(febrero)
colnames(marzo)
colnames(abril)
colnames(mayo)
colnames(junio)
colnames(julio)
colnames(agosto)
colnames(septiembre)
colnames(octubre)
colnames(noviembre)
colnames(diciembre)
```
* Rename columns  to make them consistent with q1_2020 (as this will be the supposed going-forward table design for Divvy)
```{r}

(enero <- rename(enero
                   ,ride_id = trip_id
                   ,rideable_type = bikeid 
                   ,started_at = start_time  
                   ,ended_at = end_time  
                   ,start_station_name = from_station_name 
                   ,start_station_id = from_station_id 
                   ,end_station_name = to_station_name 
                   ,end_station_id = to_station_id 
                   ,member_casual = usertype))

(febrero <- rename(febrero
                   ,ride_id = trip_id
                   ,rideable_type = bikeid 
                   ,started_at = start_time  
                   ,ended_at = end_time  
                   ,start_station_name = from_station_name 
                   ,start_station_id = from_station_id 
                   ,end_station_name = to_station_name 
                   ,end_station_id = to_station_id 
                   ,member_casual = usertype))
(marzo <- rename(marzo
                   ,ride_id = trip_id
                   ,rideable_type = bikeid 
                   ,started_at = start_time  
                   ,ended_at = end_time  
                   ,start_station_name = from_station_name 
                   ,start_station_id = from_station_id 
                   ,end_station_name = to_station_name 
                   ,end_station_id = to_station_id 
                   ,member_casual = usertype))
#etc
...
```
* Inspect the dataframes and look for incongruencies
```{r}

str(enero)
str(febrero)
str(marzo)
...
```
* Convert ride_id and rideable_type to character so that they can stack correctly
```{r}
enero <-  mutate(enero, ride_id = as.character(ride_id)
                   ,rideable_type = as.character(rideable_type)) 
febrero <-  mutate(febrero, ride_id = as.character(ride_id)
                   ,rideable_type = as.character(rideable_type)) 
marzo <-  mutate(marzo, ride_id = as.character(ride_id)
                   ,rideable_type = as.character(rideable_type))
...
```
* Stack individual quarter's data frames into one big data frame
```{r}
all_trips <- bind_rows(enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre)
```
* Inspect the new table that has been created
```{r}
colnames(all_trips)  #List of column names
nrow(all_trips)  #How many rows are in data frame?
dim(all_trips)  #Dimensions of the data frame?
head(all_trips)  #See the first 6 rows of data frame.  Also tail(all_trips)
str(all_trips)  #See list of columns and data types (numeric, character, etc)
summary(all_trips)  #Statistical summary of data. Mainly for numerics
```
* Remove irrelevant columns.
```{r}
all_trips <- all_trips[, !(names(all_trips) %in% c("start_lat", "start_lng", "end_lat", "end_lng"))]
```
* Remove duplicate rows
```{r}
all_trips <- unique(all_trips)
```

There are a few problems we will need to fix:
* The data can only be aggregated at the ride-level, which is too granular. We will want to add some additional columns of data -- such as day_of_month, month, year -- that provide additional opportunities to aggregate the data.
* We will want to add a calculated field for length of ride since the 2020Q1 data did not have the "tripduration" column. We will add "ride_length" to the entire dataframe for consistency.
*There are some rides where tripduration shows up as negative, including several hundred rides where Divvy took bikes out of circulation for Quality Control reasons. We will want to delete these rides.
* Add columns that list the date, month, day, and year of each ride
* This will allow us to aggregate ride data for each month, day, or year ... before completing these operations we could only aggregate at the ride level
```{r}
all_trips$date <- as.Date(all_trips$started_at) #The default format is yyyy-mm-dd
all_trips$month <- format(as.Date(all_trips$date), "%m")
all_trips$day_of_month <- format(as.Date(all_trips$date), "%d")
all_trips$year <- format(as.Date(all_trips$date), "%Y")
all_trips$day_of_week <- format(as.Date(all_trips$date), "%A")
```
* Add a "ride_length" calculation to all_trips (in seconds)
```{r}
all_trips$ride_length <- difftime(all_trips$ended_at,all_trips$started_at)
```

* Inspect the structure of the columns
```{r}
str(all_trips)
```
* Convert "ride_length" from Factor to numeric so we can run calculations on the data
```{r}
is.factor(all_trips$ride_length)
all_trips$ride_length <- as.numeric(as.character(all_trips$ride_length))
is.numeric(all_trips$ride_length)
```
* Remove "bad" data
* The dataframe includes a few hundred entries when bikes were taken out of docks and checked for quality by Divvy or ride_length was negative
* We will create a new version of the dataframe (v2) since data is being removed
```{r}
all_trips_v2 <- all_trips[!(all_trips$start_station_name == "HQ QR" | all_trips$ride_length<0),]
```
















