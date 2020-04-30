# Monitoreo epidemiológico de COVID-19 en México

![](https://pbs.twimg.com/profile_banners/1251773678636933120/1587470790/1500x500)

# Resumen al 28 de abril de 2020

Para detalles sobre el equipo que trabajó esta implementación, y como la mantendrémos actualizada: [Contexto sobre el observatorio de datos COVID Mx](https://github.com/datoscovidmx/datoscovidmx.github.io/blob/master/README.md)

# ¿Por qué corregir los casos confirmados?

- Los casos confirmados son una muestra estadística que contiene una serie de retrasos importantes entre el número que vemos en el presente y el día que sucedió dicha infección, estos retrasos los comprenden mayormente dos fenómenos:

 1. El retraso en el tiempo existente entre la fecha de inicio de síntomas del paciente y la fecha de confirmación oficial del caso
 2. El tiempo que necesita el virus para incubarse en el cuerpo
 
- Al pasar de las fechas de confirmación a las fechas de inicio de sintomas, es importante tener en cuenta que la cantidad total de casos confirmados tendrá dicho retraso contra la cantidad de casos que realmente han aparecido, ya que existe un retraso entre la aparición y la contabilización del caso en la confirmación. 

- Para tener en cuenta esto, se tiene que reescalar el número estimado de casos de casos corregidos hacia el presente. Dicho re escalamiento fue efectuado con una regresión negativa binomial, que permite, después de transformar las fechas de confirmación a fechas de inicio de sintomas y contar el número de casos por día, obtener una muestra de la cantidad de casos que posiblemente ocurrieron pero que no se confirmaron.

# ¿Por qué monitorear R en el tiempo?

- En cualquier epidemia, <img src="https://render.githubusercontent.com/render/math?math=R(t)"> es la medida conocida como la tasa de reproducción efectivo. Es el número de personas que se infectan por persona infectada en el momento <img src="https://render.githubusercontent.com/render/math?math=t">. La versión más conocida de este número es la tasa de reproducción básica: <img src="https://render.githubusercontent.com/render/math?math=R_0"> es decir, al inicio de la epidemia, sin embargo esta medida pasa por alto los cambios de comportamiento y las restricciones, es decir, no nos ayuda a evular una intervención (en forma de política pública) en este caso, la cuarentena y el distanciamiento social.

- En palabras simples el valor de <img src="https://render.githubusercontent.com/render/math?math=R(t)">  nos ayuda a: 
 1. Evaluar que tan efectivas han sido las medidas tomadas para controlar un brote 
 2. Como resultado, nos ayuda a comprender si debemos aumentar o reducir las restricciones para tratar de equilibrar la parte económica con el problema de salud pública.
 
- Las gráficas muestran una linea punteada sobre <img src="https://render.githubusercontent.com/render/math?math=R(t)=1">  ya que es el valor objetivo para contener la epidemia, es decir, para que la epidemia se logre mitigar, ambas bandas de la estimación (claras y obscuras) deben encontrarse sobre 1 o por debajo de 1, por un lapso de tiempo.

- Observar una tendencia a la baja es un signo positivo en relación al control de la epidemia, sin embargo mientras el número no se encuentre por debajo de 1 por el lapso de tiempo suficiente como para que el rastreo epidemiológico de los casos vuelva a ser posible, seguiran existiendo casos diarios y no se puede concluir que existe dicho control sobre la epidemia.


## Tabla de contenido

  * [Resumen Nacional](#resumen-nacional)
  * [Distribución geográfica epidemiológica dado el Rt estimado](#distribuci-n-geogr-fica-epidemiol-gica-dado-el-rt-estimado)
  * [México en el contexto mundial: ¿Estamos desacelerando?](#m-xico-en-el-contexto-mundial---estamos-desacelerando-)
  * [Monitoreo para estados con mayor crecimiento esperado](#monitoreo-para-estados-con-mayor-crecimiento-esperado)
    + [Casos confirmados contra casos estimados](#casos-confirmados-contra-casos-estimados)
    + [Evolución de la tasa de reproducción efectiva (Rt)](#evoluci-n-de-la-tasa-de-reproducci-n-efectiva--rt-)
  * [Monitoreo para el resto de los estados](#monitoreo-para-el-resto-de-los-estados)
    + [Casos confirmados contra casos estimados](#casos-confirmados-contra-casos-estimados-1)
    + [Evolución de la tasa de reproducción efectiva (Rt)](#evoluci-n-de-la-tasa-de-reproducci-n-efectiva--rt--1)
  * [Resumen final](#resumen-final)
  * [Metodología](#metodolog-a)
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

## Distribución geográfica epidemiológica dado el Rt estimado

<iframe is="x-frame-bypass" src='https://flo.uri.sh/visualisation/2167566/embed' frameborder='0' scrolling='no' style='width:100%;height:600px;'></iframe>

## México en el contexto mundial: ¿Estamos desacelerando?

<iframe is="x-frame-bypass" src='https://htmlpreview.github.io/?https://raw.githubusercontent.com/marianarf/covid19_mexico_analysis/master/log_plot.html' frameborder='0' scrolling='no' style='width:100%;height:600px;'></iframe>

¿Vamos ganando o  perdiendo la batalla contra COVID-19? ¿Cómo sabemos si las medidas para frenar la epidemia están funcionando? Esta gráfica interactiva usa escalas logarítmicas, de modo que el el crecimiento exponencial puro se ve como una línea recta. El uso de estas escalas también tiende a acentuar el crecimiento o disminución en el comportamiento de la pandemia para mostrar visualmente la evolución de la epidemia sobre el tiempo y poner en evidencia cuándo y dónde es que las medidas aplicadas parecen ayudar a "frenar la línea" (en este caso) de crecimiento exponencial.

## Monitoreo para estados con mayor crecimiento esperado

Dado nuestro análisis, en los siguientes estados se esperan más casos confirmados diarios:

- Aguascalientes
- Chihuahua
- Ciudad de México
- Jalisco
- Querétaro
- Zacatecas

### Casos confirmados contra casos estimados

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/mexico/regional-summary/high_cases_plot.png)

<center>Casos confirmados (barras) y casos estimados (banda clara = intervalo de credibilidad al 90%; banda obscura = intervalo de credibilidad al 50%).</center>
<br>

*Es de notar que la estimación, no llega al dia en el que actualizamos el reporte, dado que la estimación depende del retraso anteriormente citado, que es en promedio de alrededor de 10 días*.

### Evolución de la tasa de reproducción efectiva (Rt)

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/mexico/regional-summary/high_cases_rt_plot.png)

<center>Cambios en la tasa de reproducción efectiva (banda clara = intervalo de credibilidad al 90%; banda obscura = intervalo de credibilidad al 50%).</center>
<br>

## Monitoreo para el resto de los estados

- Solo se incluyen estados con al menos 10 casos confirmados en un día para este análisis.

### Casos confirmados contra casos estimados

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/mexico/regional-summary/cases_plot.png)

### Evolución de la tasa de reproducción efectiva (Rt)

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/mexico/regional-summary/rt_plot.png)

## Resumen final

| State                           | New confirmed cases by infection date | Expected change in daily cases | Effective reproduction no. |
|---------------------------------|---------------------------------------|--------------------------------|----------------------------|
| AGUASCALIENTES                  | 73 (0 -- 207)                         | Unsure                         | 2.3 (0 -- 4.8)             |
| BAJA CALIFORNIA                 | 48 (2 -- 93)                          | Likely decreasing              | 0.8 (0.4 -- 1.2)           |
| BAJA CALIFORNIA SUR             | 51 (0 -- 135)                         | Unsure                         | 2.6 (0.1 -- 5.5)           |
| CAMPECHE                        | 59 (0 -- 173)                         | Likely increasing              | 3.7 (0.1 -- 8.7)           |
| CHIAPAS                         | 65 (0 -- 159)                         | Likely increasing              | 2.6 (0.4 -- 4.9)           |
| CHIHUAHUA                       | 77 (0 -- 223)                         | Unsure                         | 1.9 (0.1 -- 4.1)           |
| CIUDAD DE MEXICO                | 113 (37 -- 189)                       | Decreasing                     | 0.7 (0.5 -- 0.9)           |
| COAHUILA                        | 31 (1 -- 59)                          | Likely increasing              | 1.7 (0.6 -- 2.6)           |
| COAHUILA DE ZARAGOZA            | 58 (0 -- 165)                         | Unsure                         | 2.1 (0.2 -- 4.1)           |
| DURANGO                         | 31 (0 -- 64)                          | Likely increasing              | 2.8 (0.1 -- 5.3)           |
| GUANAJUATO                      | 59 (0 -- 167)                         | Unsure                         | 2.1 (0.3 -- 4)             |
| GUERRERO                        | 38 (0 -- 77)                          | Likely increasing              | 1.8 (0.4 -- 2.9)           |
| HIDALGO                         | 33 (0 -- 65)                          | Likely increasing              | 1.6 (0.4 -- 2.5)           |
| JALISCO                         | 99 (0 -- 250)                         | Likely increasing              | 3 (0.2 -- 6.2)             |
| MEXICO                          | 67 (5 -- 129)                         | Likely decreasing              | 0.6 (0.3 -- 1)             |
| MICHOACAN                       | 27 (0 -- 52)                          | Likely increasing              | 1.7 (0.5 -- 2.8)           |
| MICHOACAN DE OCAMPO             | 41 (0 -- 76)                          | Unsure                         | 1.5 (0.4 -- 2.4)           |
| MORELOS                         | 55 (1 -- 109)                         | Likely increasing              | 1.8 (0.5 -- 2.9)           |
| NUEVO LEON                      | 58 (0 -- 182)                         | Unsure                         | 2.2 (0.1 -- 4.7)           |
| OAXACA                          | 41 (0 -- 109)                         | Likely increasing              | 2.5 (0.2 -- 5)             |
| PUEBLA                          | 46 (0 -- 88)                          | Unsure                         | 1.3 (0.5 -- 2.2)           |
| QUERETARO                       | 79 (0 -- 229)                         | Likely increasing              | 4.1 (0.1 -- 8.9)           |
| QUINTANA ROO                    | 52 (0 -- 104)                         | Unsure                         | 1.1 (0.4 -- 1.8)           |
| SINALOA                         | 79 (3 -- 154)                         | Unsure                         | 1.2 (0.4 -- 1.9)           |
| SONORA                          | 28 (0 -- 54)                          | Likely increasing              | 1.8 (0.5 -- 3.1)           |
| TABASCO                         | 68 (4 -- 127)                         | Unsure                         | 1 (0.4 -- 1.5)             |
| TAMAULIPAS                      | 37 (2 -- 70)                          | Likely increasing              | 1.4 (0.6 -- 2.2)           |
| TLAXCALA                        | 47 (0 -- 103)                         | Likely increasing              | 2.3 (0.3 -- 4.2)           |
| VERACRUZ DE IGNACIO DE LA LLAVE | 48 (4 -- 92)                          | Unsure                         | 1.3 (0.6 -- 1.9)           |
| YUCATAN                         | 48 (2 -- 91)                          | Likely increasing              | 1.6 (0.6 -- 2.5)           |
| ZACATECAS                       | 66 (0 -- 188)                         | Likely increasing              | 3.6 (0.1 -- 7.9)           |

## Metodología

Hicimos una implementación basada en el trabajo experto del [centro de modelado matemático para enfermedades infecciosas](https://cmmid.github.io/), con algunas modificaciones dado el contexto nacional:

### Datos

- Los datos utilizados provienen del reporte técnico diario federal de la Secretaría de Salud (InDRE) de México.
- Las gráficas por estado y los datos para generarlas se pueden obtener en: [https://github.com/datoscovidmx/covid-nowcasts-mexico](https://github.com/datoscovidmx/covid-nowcasts-mexico).

### Supuestos

- La fecha de infección fue calculada con base en un periodo de incubación promedio de 5 días.
- Las estimaciones de la tasa efectiva de reproducción son obtenidas por medio de *EpiEstim* ajustando para casos importados y optimizando una ventana móvil, asumiendo un intervalo serial promedio de 4.7 dias (95% CrI: 3.7, 6.0) y una desviación estandar de 2.9 dias (95% CrI: 1.9, 4.9).

### Limitaciones

Los resultados presentados aquí son sensibles a los cambios en las prácticas de prueba (testing) para COVID-19 y al nivel de esfuerzo realizado para detectar los casos de COVID-19. 

Si un estado amplía su capacidad de prueba y comienza a informar una mayor proporción de casos, entonces el modelo se ajustará a un valor de número de reproducción más alto, ya que solo comprende los nuevos casos en términos de la infecciosidad de los casos notificados previamente y no como resultado de mejores pruebas. Por otro lado, si un estado reduce su esfuerzo por hacer pruebas (por ejemplo, alcanzar su capacidad máxima de pruebas por día o quedarse sin pruebas), entonces el modelo estimará una caída en el número de reproducción que puede no ser una verdadera reducción. 

**Lo que es importante para que estos resultados sean imparciales, es que relacionado a las pruebas, la metodología para hacer pruebas de COVID-19 sea consistente. Esto significa que si bien un cambio en el esfuerzo por hacer pruebas, inicialmente introducirá un sesgo, esto se reducirá con el tiempo siempre que dicho esfuerzo permanezca constante a partir de ese momento.**

### Detalles 

Los detalles sobre la metodología se pueden encontrar en el proyecto original [https://epiforecasts.io/covid/methods.html](https://epiforecasts.io/covid/methods.html).

### Contacto 

![@DatosCovid](https://twitter.com/datoscovid)
![Correo](hola@datoscovid.mx)
