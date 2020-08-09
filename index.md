![](https://pbs.twimg.com/profile_banners/1251773678636933120/1587470790/1500x500)

# Resumen al 23 de julio de 2020

[Equipo de trabajo del Observatorio de Datos COVID MX](https://github.com/datoscovidmx/datoscovidmx.github.io/blob/master/README.md)

# ¿Por qué corregir los casos confirmados?

- Existe una serie de retrasos entre la fecha de confirmación y el día que sucedió dicha infección, por ejemplo:
  
  1) El tiempo entre el contagio y la posible manifestación de síntomas (período de incubación)
  2) El tiempo entre la fecha de inicio de síntomas y la fecha de confirmación oficial del caso.

- Por las razones anteriores, se aplica un [método de estimación](#metodología) de la fecha probable de infección o contagio, para poder estimar la cantidad de contagios que estan sucediendo en la actualidad.

# ¿Por qué monitorear R en el tiempo? Explicación de Rt.

- **<img src="https://render.githubusercontent.com/render/math?math=R_t"> es una medida clave de qué tan rápido está creciendo el virus: es el número promedio de personas infectadas por una persona infecciosa.**
  1. Si Rt está por encima de 1.0, el virus se propagará rápidamente.
  2. Cuando Rt está por debajo de 1.0, el virus se irá propagando cada vez menos.  
  
- En cualquier epidemia, <img src="https://render.githubusercontent.com/render/math?math=R_t">  es la medida conocida como la tasa de reproducción efectivo. Es el número de personas que se infectan por persona infectada en el momento <img src="https://render.githubusercontent.com/render/math?math=t">. La versión más conocida de este número es la tasa de reproducción básica <img src="https://render.githubusercontent.com/render/math?math=R_0">  que es la tasa de reproducción al inicio de la pandemia. Sin embargo, necesitamos medir Rt de forma continua para poder evaluar el efecto de las intervenciones como la cuarentena y el distanciamiento social y decidir si las restricciones deben mantenerse o relajarse.  
  
- Las gráficas muestran una linea punteada por encima de <img src="https://render.githubusercontent.com/render/math?math=R(t)=1">  ya que es el valor objetivo para contener la epidemia. **Para que la epidemia se logre mitigar, las bandas de estimación deben estar en 1 o por debajo de 1, por un lapso de tiempo.**  
  
- A pesar que una tendencia a la baja es un señal positivo de control de la epidemia, mientras el número no se encuentre por debajo de 1 durante un lapso de tiempo suficiente como para que el rastreo epidemiológico de los casos vuelva a ser posible, seguiran existiendo casos diarios y en ese caso no se puede concluir que exista dicho control sobre la epidemia.  
  
## Tabla de contenido

  * [Resumen Nacional](#resumen-nacional)
  * [Monitoreo para estados con mayor número de casos](#monitoreo-para-estados-con-mayor-numero-de-casos)
  * [Monitoreo para el resto de los estados](#monitoreo-para-el-resto-de-los-estados)
  * [Resumen final](#resumen-final)
  * [Metodología](#metodología)
    + [Datos](#datos)
    + [Supuestos](#supuestos)
    + [Limitaciones](#limitaciones)
    + [Detalles](#detalles)
    + [Contacto](#contacto)
 
## Resumen Nacional

Este resúmen muestra la tasa efectiva de reproducción mas actualizada para cada estado además del estimado de casos nuevos diarios.

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/mexico/regional-summary/summary_plot.png)

<center>Resúmen nacional. (barra clara = intervalo de credibilidad al 90%; barra oscura = intervalo de credibilidad al 50%.</center>
<br>

Los estados están ordenados por el número de casos diarios confirmados esperados y codificados por color según el cambio esperado en los casos diarios confirmados.

**La línea punteada indica el valor objetivo de 1 para la tasa efectiva de reproducción que se requiere para el control**

## Monitoreo para estados con mayor número de casos

### Casos confirmados, estimados por fecha de contagio y pronóstico de 7 días

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/mexico/regional-summary/high_cases_plot.png)

<center>Las barras son los casos confirmados a la fecha, la banda gris son las estimaciones de casos por fecha de contagio, la banda naranja es el pronóstico de contagios. Las bandas claras son un intervalo de credibilidad al 90% y las oscuras son el intervalo de credibilidad al 50%.</center>
<br>
*Es de notar que la estimación, no llega al dia en el que actualizamos el reporte, dado que la estimación depende del retraso anteriormente citado, que es en promedio de alrededor de 10 días. Por la misma razón, el pronóstico de contagios incluye días en el presente*.

### Evolución de la tasa de reproducción efectiva (Rt)

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/mexico/regional-summary/high_cases_rt_plot.png)

<center>Cambios en la tasa de reproducción efectiva (banda clara = intervalo de credibilidad al 90%; banda obscura = intervalo de credibilidad al 50%). La confianza en los valores estimados se indica por transparencia, una transparencia alta corresponde a una confianza reducida.</center>
<br>

## Monitoreo para el resto de los estados

- **Solo se incluyen estados con al menos 10 casos confirmados en un día para este análisis.**

### Casos confirmados, estimados por fecha de contagio y pronóstico de 7 días

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/mexico/regional-summary/cases_plot.png)

### Evolución de la tasa de reproducción efectiva (Rt) para el resto de los estados

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/mexico/regional-summary/rt_plot.png)

## Resumen final

| Estado              | Nuevos casos confirmados por fecha de síntomas   | Cambio esperado en nuevos casos   | Número de reproducción efectiva   | Tiempo de duplicación / reducción a la mitad (días)   |
|:--------------------|:-------------------------------------------------|:----------------------------------|:----------------------------------|:------------------------------------------------------|
| AGUASCALIENTES      | 66 (47 -- 83)                                    | Incierto                          | 1 (0.9 -- 1.2)                    | 100 (12 -- -16)                                       |
| BAJA CALIFORNIA     | 165 (139 -- 187)                                 | Probablemente aumentando          | 1.1 (1 -- 1.2)                    | 29 (13 -- -88)                                        |
| BAJA CALIFORNIA SUR | 105 (85 -- 121)                                  | Incierto                          | 1.1 (0.9 -- 1.2)                  | 67 (14 -- -24)                                        |
| CAMPECHE            | 85 (65 -- 100)                                   | Incierto                          | 1 (0.9 -- 1.2)                    | 320 (15 -- -17)                                       |
| CHIAPAS             | 33 (21 -- 43)                                    | Incierto                          | 0.9 (0.7 -- 1.2)                  | -79 (11 -- -9)                                        |
| CHIHUAHUA           | 69 (53 -- 81)                                    | Incierto                          | 1 (0.8 -- 1.1)                    | -100 (18 -- -14)                                      |
| CIUDAD DE MÉXICO    | 893 (804 -- 973)                                 | Aumentando                        | 1.1 (1 -- 1.2)                    | 25 (16 -- 57)                                         |
| COAHUILA            | 331 (284 -- 371)                                 | Aumentando                        | 1.2 (1.1 -- 1.3)                  | 15 (9.8 -- 28)                                        |
| COLIMA              | 40 (27 -- 51)                                    | Incierto                          | 1 (0.8 -- 1.2)                    | 140 (10 -- -12)                                       |
| DURANGO             | 74 (57 -- 88)                                    | Incierto                          | 1 (0.9 -- 1.2)                    | 70 (13 -- -20)                                        |
| GUANAJUATO          | 395 (351 -- 440)                                 | Incierto                          | 1 (0.9 -- 1.1)                    | -980 (33 -- -32)                                      |
| GUERRERO            | 168 (144 -- 191)                                 | Probablemente disminuyendo        | 0.9 (0.8 -- 1)                    | -33 (83 -- -14)                                       |
| HIDALGO             | 110 (88 -- 125)                                  | Probablemente aumentando          | 1.1 (1 -- 1.3)                    | 20 (9.4 -- -180)                                      |
| JALISCO             | 230 (196 -- 265)                                 | Probablemente aumentando          | 1.1 (1 -- 1.2)                    | 30 (14 -- -150)                                       |
| MÉXICO              | 586 (524 -- 650)                                 | Incierto                          | 1 (0.9 -- 1.1)                    | 71 (25 -- -86)                                        |
| MICHOACÁN           | 140 (119 -- 159)                                 | Probablemente aumentando          | 1.1 (1 -- 1.2)                    | 29 (12 -- -72)                                        |
| MORELOS             | 40 (29 -- 52)                                    | Incierto                          | 1.1 (0.9 -- 1.3)                  | 27 (8 -- -19)                                         |
| NAYARIT             | 61 (44 -- 74)                                    | Incierto                          | 1 (0.9 -- 1.2)                    | 78 (12 -- -17)                                        |
| NUEVO LEÓN          | 389 (346 -- 443)                                 | Aumentando                        | 1.1 (1 -- 1.2)                    | 30 (16 -- 410)                                        |
| OAXACA              | 162 (139 -- 183)                                 | Incierto                          | 1 (0.9 -- 1.2)                    | 54 (16 -- -38)                                        |
| PUEBLA              | 383 (327 -- 434)                                 | Aumentando                        | 1.2 (1.1 -- 1.3)                  | 17 (10 -- 44)                                         |
| QUERETARO           | 63 (47 -- 76)                                    | Incierto                          | 1.1 (0.9 -- 1.2)                  | 41 (11 -- -22)                                        |
| QUINTANA ROO        | 126 (102 -- 150)                                 | Incierto                          | 1 (0.8 -- 1.1)                    | -67 (27 -- -15)                                       |
| SAN LUIS POTOSÍ     | 217 (193 -- 243)                                 | Aumentando                        | 1.1 (1 -- 1.2)                    | 23 (12 -- 250)                                        |
| SINALOA             | 158 (131 -- 180)                                 | Incierto                          | 1 (0.9 -- 1.1)                    | -110 (29 -- -19)                                      |
| SONORA              | 359 (323 -- 397)                                 | Incierto                          | 1 (0.9 -- 1.1)                    | 62 (21 -- -66)                                        |
| TABASCO             | 375 (333 -- 420)                                 | Incierto                          | 1 (0.9 -- 1.1)                    | 160 (27 -- -41)                                       |
| TAMAULIPAS          | 351 (311 -- 389)                                 | Aumentando                        | 1.1 (1 -- 1.2)                    | 19 (12 -- 50)                                         |
| TLAXCALA            | 68 (53 -- 83)                                    | Incierto                          | 1 (0.9 -- 1.2)                    | 38 (11 -- -24)                                        |
| VERACRUZ            | 395 (354 -- 433)                                 | Probablemente aumentando          | 1.1 (1 -- 1.1)                    | 34 (17 -- -640)                                       |
| YUCATÁN             | 166 (145 -- 189)                                 | Incierto                          | 1 (0.9 -- 1.2)                    | 94 (19 -- -29)                                        |
| ZACATECAS           | 69 (53 -- 82)                                    | Probablemente aumentando          | 1.1 (0.9 -- 1.3)                  | 24 (9 -- -37)                                         |

## Metodología

Hicimos una implementación basada en el trabajo experto del [centro de modelado matemático para enfermedades infecciosas](https://cmmid.github.io/), con algunas modificaciones dado el contexto nacional:

Al pasar de las fechas de confirmación a las fechas de inicio de sintomas, es importante tener en cuenta que la cantidad total de casos confirmados tendrá dicho retraso contra la cantidad de casos que realmente han aparecido, ya que existe un retraso entre la aparición y la contabilización del caso en la confirmación.

Para la estimación de los casos por fecha de contagio se tiene que reescalar el número estimado de casos de casos confirmados hacia el presente. Dicho re escalamiento fue efectuado con una regresión negativa binomial, que permite, después de transformar las fechas de confirmación a fechas de inicio de sintomas y contar el número de casos por día, obtener una muestra de la cantidad de casos que posiblemente ocurrieron pero que no se confirmaron.

### Datos

- A partir del 6 de Mayo, los datos utilizados provienen del portal de SINAVE del Gobierno Federal [https://covid19.sinave.gob.mx/](https://covid19.sinave.gob.mx/)

- Las gráficas por estado y los datos para generarlas se pueden obtener en: [https://github.com/datoscovidmx/covid-nowcasts-mexico](https://github.com/datoscovidmx/covid-nowcasts-mexico).

### Supuestos

- La fecha de infección fue calculada con base en un periodo de incubación promedio de 5 días.
- Las estimaciones de la tasa efectiva de reproducción son obtenidas por medio de *EpiEstim* ajustando para casos importados y optimizando una ventana móvil, asumiendo un intervalo serial promedio de 4.7 dias (95% CrI: 3.7, 6.0) y una desviación estandar de 2.9 dias (95% CrI: 1.9, 4.9).

### Limitaciones

Los resultados presentados aquí son sensibles a los cambios en las prácticas de prueba (testing) para COVID-19 y al nivel de esfuerzo realizado para detectar los casos de COVID-19. 

Si un estado amplía su capacidad de prueba y comienza a informar una mayor proporción de casos, entonces el modelo se ajustará a un valor de número de reproducción más alto, ya que solo comprende los nuevos casos en términos de la infecciosidad de los casos notificados previamente y no como resultado de mejores pruebas. Por otro lado, si un estado reduce su esfuerzo por hacer pruebas (por ejemplo, alcanzar su capacidad máxima de pruebas por día o quedarse sin pruebas), entonces el modelo estimará una caída en el número de reproducción que puede no ser una verdadera reducción. 

**Lo que es importante para que estos resultados sean imparciales, es que relacionado a las pruebas, la metodología para hacer pruebas de COVID-19 sea consistente. Esto significa que si bien un cambio en el esfuerzo por hacer pruebas, inicialmente introducirá un sesgo, esto se reducirá con el tiempo siempre que dicho esfuerzo permanezca constante a partir de ese momento.**

### Mapa de casos

<!-- Load d3.js -->
<script src="https://d3js.org/d3.v4.min.js"></script>
<script src="https://d3js.org/d3-scale-chromatic.v1.min.js"></script>
<script src="https://d3js.org/d3-geo-projection.v2.min.js"></script>

<!-- Font -->
<link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap" rel="stylesheet">

<style>
.tooltip {
  position: absolute;
  padding: 7px;
  font-size: 0.9em;
  font-family: 'Open Sans', sans-serif;
  pointer-events: none;
  background: #fff;

  -moz-box-shadow:    3px 3px 10px 0px rgba(0, 0, 0, 0.25);
  -webkit-box-shadow: 3px 3px 10px 0px rgba(0, 0, 0, 0.25);
  box-shadow:         3px 3px 10px 0px rgba(0, 0, 0, 0.25);
}

.tooltip p {
  margin: 0;
  padding: 0;
}

#legend text {
  font-size: 0.9em;
  color: #333;
  font-weight: 400;
}

#map {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>

<!-- Create an element where the map will take place -->
<svg id="map" width="600" height="400"></svg>

<script>
// The svg
var svg = d3.select("svg"),
    width = +svg.attr("width"),
    height = +svg.attr("height");

// Map and projection
var projection = d3.geoMercator()
    .center([-100, 22])
    .translate([ width/1.7, height/1.7])
    .scale([ width/.5 ]);

// Data and color scale
var data = d3.map();
var colorScale = d3.scaleOrdinal().range(["#98FB98", "#CDFF82", "#FFFF9E", "#F05C3C", "#DF2B04"]).domain(["Disminuyendo", "Probablemente disminuyendo", "Incierto", "Probablemente aumentando", "Aumentando"])

tooltip = d3.select("body").append("div")
  .attr("class", "tooltip")
  .style("opacity", 0);

// Load external data and boot
d3.queue()
  .defer(d3.json, "https://datoscovidmx.s3-us-west-2.amazonaws.com/casos_mexico.geojson")
  .await(ready);

function numberWithCommas(x) {
    return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
}

var legendText = ["10%"];
var legendColors = ["#fff7bc"];

function ready(error, cases) {

  // Draw the map
  svg.append("g")
     .selectAll("path")
     .data(cases.features)
     .enter()
     .append("path")
     // draw each country
     .attr("d", d3.geoPath()
                  .projection(projection)
     )
     // set the color of each country
     .attr("fill", function (d) {
       console.log(d.properties)
       return colorScale(d.properties.cambio);
     })
     .style("stroke", "transparent")
     .attr("class", function(d){ return "State" } )
     .style("opacity", .6)
     .on("mouseover", function(d) {
      tooltip.transition()
      .duration(250)
      .style("opacity", 1);
      tooltip.html(
      "<p><strong>" + d.properties.estado + ": " + numberWithCommas(d.properties.cases) + " casos" + "</strong></p>")
      .style("left", (d3.event.pageX + 15) + "px")
      .style("top", (d3.event.pageY - 28) + "px");
    })
    .on("mouseout", function(d) {
      tooltip.transition()
      .duration(250)
      .style("opacity", 0);
    });

  var legend = svg.append("g")
    .attr("id", "legend");

  // Handmade legend
  legend.append("circle").attr("cx", 10).attr("cy", 200).attr("r", 6).style("fill", "#98FB98").style("opacity", .6)
  legend.append("circle").attr("cx", 10).attr("cy", 230).attr("r", 6).style("fill", "#CDFF82").style("opacity", .6)
  legend.append("circle").attr("cx", 10).attr("cy", 260).attr("r", 6).style("fill", "#FFFF9E").style("opacity", .6)
  legend.append("circle").attr("cx", 10).attr("cy", 290).attr("r", 6).style("fill", "#F05C3C").style("opacity", .6)
  legend.append("circle").attr("cx", 10).attr("cy", 320).attr("r", 6).style("fill", "#DF2B04").style("opacity", .6)
  legend.append("text").attr("x", 30).attr("y", 200).text("Disminuyendo").style("font-size", "15px").attr("alignment-baseline","middle")
  legend.append("text").attr("x", 30).attr("y", 230).text("Probablemente disminuyendo").style("font-size", "15px").attr("alignment-baseline","middle")
  legend.append("text").attr("x", 30).attr("y", 260).text("Incierto").style("font-size", "15px").attr("alignment-baseline","middle")
  legend.append("text").attr("x", 30).attr("y", 290).text("Probablemente aumentando").style("font-size", "15px").attr("alignment-baseline","middle")
  legend.append("text").attr("x", 30).attr("y", 320).text("Aumentando").style("font-size", "15px").attr("alignment-baseline","middle")
    }
</script>

### Detalles 

Los detalles sobre la metodología se pueden encontrar en el proyecto original [https://epiforecasts.io/covid/methods.html](https://epiforecasts.io/covid/methods.html).

### Contacto 

[@DatosCovid](https://twitter.com/datoscovid)
[Correo](hola@datoscovid.mx)
