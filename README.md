# La tuberculosis y el por qué de su tasa de mortalidad: Una comparativa entre países y sus factores de riesgo

## Justificación

- La tuberculosis es una enfermedad que en 2020 causó la muerte de 1.5 millones de personas en todo el mundo [1]. 
- La tuberculosis es una enfermedad que se da en todas las regiones del mundo [1].
- El saber por qué la gente muere de Tuberculosis permite determinar qué causas pueden ser prevenibles y cuáles no, así permitiendo crear una oportunidad de acción para las causas en las que sí se podría hacer algo al respecto y preservar la vida humana.
- La investigación se considera pertinente, ya que se espera construir una base para que en futuras investigaciones, se analice la enfermedad desde una perspectiva multifactorial, específica de cada región. Lo anterior, buscando que se den soluciones apropiadas para la situación de la población. 
- Es importante conocer el porqué una enfermedad encontrada hace más de un siglo tiene una tasa de mortalidad alta (~15% [1]) en tiempos donde la vacuna ya ha sido creada y efectiva.

## Pregunta de Investigación

¿Cómo se relaciona la situación socioeconómica, geográfica y la tasa de vacunación con la tasa de mortalidad de la Tuberculosis en diferentes países?


## Objetivo General

Determinar la relación entre factores geográficos, socioeconómicos y la tasa de vacunación con la tasa de mortalidad de Tuberculosis entre los países estudiados.

## Objetivos Específicos

1. Identificar la muestra poblacional a estudiar: se van a comparar varios continentes mediante una selección de países por continente.
2. Establecer y analizar la correlación entre los distintos factores externos entre los países estudiados y la tasa de mortalidad por la tuberculosis:
  2.1 Comparar países dentro del mismo continente, determinar las variables más pertinentes y analizar el porqué.
  2.2 Comparar las diferentes variables más pertinentes por continentes entre sí y determinar si hay patrones regionales y cuál puede ser la explicación.
  
  
## Tipo de Investigación

Nuestra investigación va a ser de carácter **cuantitativo**, dado que vamos a usar bases de datos con observaciones numéricas de variables relacionadas a cada país, y vamos a usar herramientas estadísticas e informáticas como el clustering para analizarlas. Tenemos un enfoque **transversal** porque no analizamos los países en periodos de tiempo, si no mediante observaciones particulares, es **descriptiva** porque queremos describir las variables que se relacionan con la tasa de mortalidad de la tuberculosis, más no buscamos determinar causa y efecto, y finalmente **inductiva** porque partimos de observaciones particulares de cada país para obtener tendencias generales que nos permitan saber qué afecta la tasa de mortalidad de la tuberculosis a nivel de países.

## Hipótesis de Investigación

- Los países con bajo desarrollo económico, educativo y baja tasa de vacunación tendrán mayor tasa de mortalidad frente a la tuberculosis. El factor del clima tiene una relación significativa con la tasa de mortalidad, sin embargo, no estamos seguros de la dirección de esta relación. 

- Hipótesis de tipo **correlacional** y **no direccional** dado que sólo hablamos de una relación entre variables, sin suponer una relación causal.

## Matriz de Datos

<table>
  <tr>
    <td colspan="5" style="text-align: center"><b>Matriz de Datos</b></td>
  </tr>
  <tr>
    <td><b>Variable</b></td>
    <td><b>Descripción</b></td>
    <td><b>Tipo de Variable</b></td>
    <td><b>Tipo de Relación</b></td>
    <td><b>Fuente de los Datos</b></td>
  </tr>
  
  <tr>
    <td>Población</td>
    <td>Población total de un país</td>
    <td>Cuantitativa Discreta</td>
    <td>Independiente</td>
    <td>https://data.oecd.org/pop/population.htm</td>
  </tr>
  <tr>
    <td>PIB per capita</td>
    <td>El Producto Interno Bruto dividido entre la población por país en cuestión</td>
    <td>Cuantitativa Continua</td>
    <td>Independiente</td>
    <td>https://data.worldbank.org/indicator/NY.GDP.PCAP.CD</td>
  </tr>
  <tr>
    <td>Población que culminó educación terciaria</td>
    <td>Porcentaje de población que culminó estudios terciarios por país</td>
    <td>Cuantitativa Continua</td>
    <td>Independiente</td>
    <td>https://data.oecd.org/eduatt/population-with-tertiary-education.htm</td>
  </tr>
  <tr>
    <td>Tasa de vacunación</td>
    <td>Porcentaje de vacunación por país</td>
    <td>Cuantitativa Continua</td>
    <td>Independiente</td>
    <td>https://ourworldindata.org/vaccination</td>
  </tr>
  <tr>
    <td>Latitud central</td>
    <td>La latitud central por país, calculada con |lat_{min}-lat_{max}|/2</td>
    <td>Cuantitativa Continua</td>
    <td>Independiente</td>
    <td>https://developers.google.com/public-data/docs/canonical/countries_csv</td>
  </tr>
  <tr>
    <td>Longitud central</td>
    <td>La longitud central por país, calculada con |lon_{min}-lon_{max}|/2</td>
    <td>Cuantitativa Continua</td>
    <td>Independiente</td>
    <td>https://developers.google.com/public-data/docs/canonical/countries_csv</td>
  </tr>
  <tr>
    <td>Tasa de mortalidad por Tuberculosis</td>
    <td>Cantidad de muertes por tuberculosis dividido entre la población por país</td>
    <td>Cuantitativa Continua</td>
    <td>Dependiente</td>
    <td>https://ourworldindata.org/vaccination </td>
  </tr>
</table>

## Metodología de Tratamiento de Datos

Dado que vamos a analizar todos los países del mundo de los que tengamos las variables propuestas anteriormente, vamos a usar una técnica de clustering sencilla llamada K-means para separar los países junto con sus observaciones y así generar un número de grupos de países similares mucho menor que el número de países estudiados, que algebraicamente se representa como países con poca distancia entre sí. Este tipo de análisis es posible si tomamos cada variable como una dimensión y cada país como un punto u observación en un espacio multidimensional. Finalmente, podemos analizar cada cluster resultante. El proceso lo vamos a realizar haciendo uso del lenguaje de programación Python y una popular librería llamada scikit-learn.

Por otro lado se hallará el coeficiente de correlación para cuantificar la intensidad de la relación lineal entre las variables, este funciona comparando la distancia de cada dato puntual respecto a la media de la variable y utiliza esta comparación para decirnos hasta qué punto la relación entre las variables se ajusta a una línea imaginaria trazada entre los datos. Se puede hacer este análisis en herramientas como Excel o como lenguajes de programación e.g. Python.

Por último, se utilizaran tablas dinámicas para la organización y filtración de la información, ya que es una herramienta avanzada para resumir y analizar una gran cantidad de datos para luego, ver comparaciones, patrones y tendencias entre ellos. 

![Logo de Python](python-logo.png) <br>
![Logo de skicit-learn](scikit-learn-logo.png) <br>

## Referencias
[1] "Tuberculosis", World Health Organization. [Online]. Available: https://www.who.int/es/news-room/fact-sheets/detail/tuberculosis. [Accessed: 26-Feb-2022].

## Integrantes
- Jose Luis Acevedo Porras
- David Alejandro Cortés Pinto
- Miguel Ángel Galeano Rodríguez
- María Juanita Mora Olaya
- Brayan Stiven Peña Velásquez
- María José Rey Sánchez
- Anamaría Suárez Martínez
