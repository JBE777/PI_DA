<p align='center'>
<img src ="https://d31uz8lwfmyn8g.cloudfront.net/Assets/logo-henry-white-lg.png">
<p>

<h1 align=center><span style="font-family:Arial Black">PROYECTO INDIVIDUAL Nº2</span></h1>
<h1 align='center'>Telecomunicaciones</h1>
<h4 align=center><span style="font-family:Arial Black"><i>presentado por</i>:</h4>i
<h2 align=center><i>Javier Báez Esqueda</i></h2>
 
<p><img src="Antena.jpg", width="400"></p>
<h4 align=center><span style="font-family:Arial Black"><i>Cohorte</i></span>: DataPT04</h4>

¡Bienvenidos al último proyecto individual de la etapa de labs! En esta ocasión, debo trabajar situándome en el rol de un ***Data Analyst***.

<h2>Objetivo</h2>

> Crear un Dashbord con datos extraidos de una API de telecomunicaciones llamado ENACOM - Ente Nacional de Comunicaciones de Argentina para limpiarlos y analizarlos, con el fin de mostrar
el contenido de los datos en los archivos: **`Internet_Penetracion.csv`** y **`telefonia_fija.csv`** que permitan visualizar la realidad tanto del `Internet` como la `Telefonia fija` de hoy en día; lo cuál permitirá generar la materia prima para buscar evolucionar en estos dos importantes campos de las telecomunicaciones.

<h2>Introducción</h2>

> En este proyecto, mis archivos de trabajo fueron los siguientes: **`Internet_Accesos-por-tecnologia.csv`**, **`Internet_Ingresos.csv`**,**`Internet_Penetracion.csv`** y **`telefonia_fija.csv`**. Una vez, explorados los archivos anteriores se generaron los posteriores:**`Tecnologia.csv`**, **`Ingresos.csv`**, **`Penetracion_internet.csv`** y **`Telefonia_Fija.csv`**. Luego, se crean los siguientes archivos para
trabajar con el *EDA - Análisis exploratorio de datos*: **`Internet.csv`** y **`Telefonia_Fija.csv`**.
Además, con los archivos **`Internet_Penetracion.csv`** y **`telefonia_fija.csv`** creamos el insumo para mostrar la realidad prevaleciente en estos importantes terrenos de las telecomunicaciones como lo son: *`Internet`*  y *`Telefonía fija`*.
Para lo cuál, se renombran los archivos mencionados ya como tablas y dentro de *`PowerBI`* adquirien los nombres: **`Internet`** y **`Telefoniafija`**; con el propósito de diseñar un KPI para cada campo de la comunicacion y muestre que se puede aumentar la cobertura en estas tecnologias.

## Desarrollo ETL
### *`Extracción, transformación y carga de datos`*(Pag. 1)
> Para este desarrollo, se crea el Notebook *PI_2_ETL* y se trabaja con los archivos csv: **`Internet_Accesos-por-tecnologia.csv`**,
**`Internet_Ingresos.csv`**, **`Internet_Penetracion.csv`** y **`telefonia_fija.csv`**. Para abrir los archivos, importamos la libreria necesaria: **`pandas`**.
Abrimos el archivo **`Internet_Accesos-por-tecnologia.csv`** y eliminamos las columnas *`Otros`* y *`Total`* quedando 7 columnas
y 36 registros para salvar como **`Tecnologia.csv`**. Enseguida abrimos el dataset **`Internet_Ingresos.csv`** encontando 4 columnas y 36 registros
salvando como **`Ingresos.csv`**. Luego, abrimos el dataset **`Internet_Penetracion.csv`** con el parametro *`decimal=','`* para componer los datos de la columna
*`Accesos por cada 100 hogares`* que venía con coma y cambiamos a punto decimal. Continuando con este dataset, eliminamos las columnas *`Unnamed: 4`*,*`Unnamed: 5`* y *`Unnamed: 6`*
que vienen vacías y renombramos la columna *`Accesos por cada 100 hogares`* como *`Accesoactual`* quedando 864 registros y 4 columnas para salvar como **`Penetracion_internet.csv`**. Después, abrimos el dataset **`telefonia_fija.csv`** y eliminamos la columna
*`Accesos telefonía fija por cada 100 hab`* para renombrar la columna *`Accesos telefonía fija por cada 100 hogares`* como *`AccesoactualTel`*
generando 4 columnas y `864` registros salvando como **`Telefonia_Fija.csv`**.
En esta parte fusionamos los archivos: **`Ingresos.csv`**, **`Tecnologia.csv`** y **`Penetracion_internet.csv`** que generan
`10` columnas y `864` registros para ser salvado como **`Internet.csv`**. Reservando este último dataset junto con **`Telefonia_Fija.csv`** para el análisis `EDA`. Los siguientes archivos que reservamos para los `KPIs` son **`Penetracion_internet.csv`** con `4`
columnas y `864` registros y **`Telefonia_Fija.csv`** con `4` columnas y `864` registros.

## Desarrollo EDA
### *`Exploración y análisis de datos`*(Pag. 2)
> Para este desarrollo, se crea el Notebook *PI_2_EDA* y se trabaja con los `archivos csv`: **`Internet.csv`** y **`Telefonia_Fija.csv`**. Para abrir los archivos, 
importamos la libreria necesarias: **`pandas`**, **`matplotlib.pyplot`**, **`seaborn`** y **`wordcloud`**. Primeramente, abrimos el dataset: **`Internet.csv`**, en el cual,
eliminamos las columnas: *`ADSL`*, *`Cablemodem`*, *`Wireless`* y *`Ingresos (miles de pesos)`* para reducir el dataset:
**`Internet.csv`** a `6` columnas y `864` registros. Este archivo lo fusionamos con el dataset: **`Telefonia_Fija.csv`** con `4` columnas y `864` registros y queda como archivo: **`df`**
con `792` registros y `7` columnas. Con esté último dataset, podemos trabajar en nuestro *`EDA`*, donde `no encontramos datos nulos` y `eliminamos posibles duplicados`.
Para empezar, tenemos `Internet` y `Telefonía fija` para trabajar con `7` columnas y `792` registros. Para el, `Internet`se contemplan las columnas: `Accesoactual` y `Fibra óptica` en dos ambitos `Trimestre` y `Provincia`, que nos arrojan los siguientes resultados en la parte de **`Accesoactual`**:
Los outliers son 36 valores desde `105.98` a `124.06` y distribuidos desde el año `2014` al `2022`. Representando una fracción de `36/792` con un porcentaje de `4.55 %`.
Dónde las provincias con mayor covertura en `Acceso actual a internet` son: *`Capital Federal`* y *`La Pampa`*. Ahora en la facción de **`Fibra óptica`**, obtenemos los correspondientes resultados:
Los outliers son `22` valores en todos los trimestres, siendo respectivamente `637`, `761`, `852` y `941` para `Trimestre 1`, `Trimestre 2`, `Trimestre 3` y `Trimestre 4`.
Cayendo todos los valores en el año `2019` con una fracción de `88/792` y porcentaje de `11.11 %`.
Siendo las medianas, valores idénticos en todas las provincias y trimestres respectivamente `164`, `151`, `163` y `150`
para `Trimestre 1`, `Trimestre 2`, `Trimestre 3` y `Trimestre 4`. En la parte de `Acceso a Telefonía fija`, se contempla la columna: `AccesoactualTel` en dos ambitos `Trimestre` y `Provincia`, que nos arrojan los siguientes resultados en la parte de **`AccesoactualTel`**:
Los outliers de la columna `AccesoactualTel`, fluctúan desde `10.727` hasta `13.828` que representan una fracción de `32/792` entre los años `2014 a 2022` y se plasma como un porcentaje de `4.04 %`.
En este análisis sobresale la provincia de *`Capital Federal`*, seguida por *`Buenos Aires`*. Generando una nube de palabras de la columna: `Provincia`, siendo las palabras que más se repiten: *`Aires, Capital, Buenos Aires y Capital Federal`*.

### Conclusiones:
> La mayor cobertura de `acceso a internet` recae en las provincias de `Capital Federal` y `La Pampa` con el primero y segundo lugar respectivamente.
Con `36 valores outliers`, que basado en el `total de registros de 792` nos arrojan un porcentaje de `4.55 %` para cubrir los años desde `2014 hasta 2022`. En el segmento de `fibra óptica` está muy `parejo en lo que respecta a las provincias`, con `88 valores outliers` que basados en la cantidad de registros nos
resultan en un porcentaje de `11.11 %` fincado solamente en el `año 2019`. Siendo las `medianas idénticas` en todas las `provincias` en sus respectivos `trimestres`. La cobertura de `acceso a la telefonía fija` se ve beneficiada en primer lugar por la provincia de `Capital Federal` y en segundo lugar `Buenos Aires`.
Siendo `32 valores outliers`, y según el total de registros nos arrojan un porcentaje de `4.04 %` fluctuando entre los años `2014 al 2022`. En ninguno de los casos, se eliminaron los `outliers` porque se consideran importantes para este estudio y la interaccion con los datos en general. Mientras se puede constatar por la nube de palabras, que las provincias mas importantes, a resaltar son: `Capital Federal` y `Buenos Aires`.

### Resumen:

Se explora detalladamente los datos de los datasets: **`Penetracion_internet.csv`** y **`Telefonia_Fija.csv`**, para elijir cada uno de los KPIs. Éstos, permiten mostrar una síntesis de la información producto del análisis, que clarifican la presentación de los datos.
Aspectos inherentes a la visualización, se resaltan para conseguir la coherencia de los gráficos según las variables a mostrar. 
Mientras el primer KPI, se propone aumentar en un 2% el acceso al servicio a internet para el próximo trimestre por cada 100 hogares y por provincia. Atendiendo a los cálculos pertinentes, se hicieron los respectivos ajustes a las columnas aludidas para poder revelar las tendencias en ese sentido. Desarollando la misma operación para el segundo KPI en el campo de la telefonía fija que permita entregar el producto calculado y poder atender todas las instancias propuestas.
    
### Link GitHub:
https://github.com/JBE777/PI_DA

<h4 align='right'><i>Pag. 3</i></h4>   
