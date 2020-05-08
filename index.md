![](https://pbs.twimg.com/profile_banners/1251773678636933120/1587470790/1500x500)

# Resumen al 6 de mayo de 2020

[Equipo de trabajo del Observatorio de Datos COVID MX](https://github.com/datoscovidmx/datoscovidmx.github.io/blob/master/README.md)

# ¿Por qué corregir los casos confirmados?

- Los casos confirmados son una muestra estadística que contiene una serie de retrasos entre el número que vemos en el presente y el día que sucedió dicha infección, por ejemplo:

  1) El retraso en el tiempo existente entre la fecha de inicio de síntomas del paciente y la fecha de confirmación oficial del caso.
  2) El tiempo que necesita el virus para incubarse en el cuerpo después del contagio (período de incubación)

- Por las razones anteriores, se aplica un [método de estimación](#metodología) de la fecha probable de infección o contagio, para poder estimar la cantidad de contagios que estan sucediendo en la actualidad.

# ¿Por qué monitorear R en el tiempo? Explicación de Rt.

- **<img src="https://render.githubusercontent.com/render/math?math=R(t)">  es una medida clave de qué tan rápido está creciendo el virus: es el número promedio de personas infectadas por una persona infecciosa.**
  1. Si Rt está por encima de 1.0, el virus se propagará rápidamente.
  2. Cuando Rt está por debajo de 1.0, el virus se irá propagando cada vez menos.

- En cualquier epidemia, <img src="https://render.githubusercontent.com/render/math?math=R(t)">  es la medida conocida como la tasa de reproducción efectivo. Es el número de personas que se infectan por persona infectada en el momento <img src="https://render.githubusercontent.com/render/math?math=t">. La versión más conocida de este número es la tasa de reproducción básica <img src="https://render.githubusercontent.com/render/math?math=R_0">  que es la tasa de reproducción al inicio de la pandemia. Sin embargo, necesitamos medir Rt de forma continua para poder evaluar el efecto de las intervenciones como la cuarentena y el distanciamiento social y decidir si las restricciones deben mantenerse o relajarse.
  
- Las gráficas muestran una linea punteada por encima de <img src="https://render.githubusercontent.com/render/math?math=R(t)=1">  ya que es el valor objetivo para contener la epidemia. **Para que la epidemia se logre mitigar, las bandas de estimación deben estar en 1 o por debajo de 1, por un lapso de tiempo.**

- A pesar que una tendencia a la baja es un señal positivo de control de la epidemia, mientras el número no se encuentre por debajo de 1 durante un lapso de tiempo suficiente como para que el rastreo epidemiológico de los casos vuelva a ser posible, seguiran existiendo casos diarios y en ese caso no se puede concluir que exista dicho control sobre la epidemia.

## Tabla de contenido

  * [Resumen Nacional](#resumen-nacional)
  * [Distribución geográfica epidemiológica dado el Rt estimado](#distribución-geográfica-epidemiológica-dado-el-rt-estimado)
  * [México en el contexto mundial: ¿Estamos desacelerando?](#méxico-en-el-contexto-mundial-¿estamos-desacelerando?)
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

## Distribución geográfica epidemiológica dado el Rt estimado

<iframe is="x-frame-bypass" src='https://flo.uri.sh/visualisation/2308984/embed' frameborder='0' scrolling='no' style='width:100%;height:600px;'></iframe>
<br>
<center>Notas: El número de casos que se muestran corresponden al estimado bajo y el alto del modelo. El R(t) es el valor promedio de los estimados. Para más información, consultar la tabla</center>

## México en el contexto global: ¿qué tan efectivo ha sido para disminuir el crecimiento exponencial?

<iframe is="x-frame-bypass" src='https://htmlpreview.github.io/?https://raw.githubusercontent.com/marianarf/covid19_mexico_analysis/master/plot.html' frameborder='0' scrolling='no' style='width:100%;height:600px;'></iframe>
<br>
Fuente: Nuevos casos de COVID-19, proporcionados por JHU CSSE
<br>
¿Vamos ganando o  perdiendo la batalla contra COVID-19? ¿Cómo sabemos si las medidas para frenar la epidemia están funcionando? Esta gráfica interactiva usa escalas logarítmicas, de modo que el el crecimiento exponencial puro se ve como una línea recta. El uso de estas escalas también tiende a acentuar el crecimiento o disminución en el comportamiento de la pandemia para mostrar visualmente la evolución de la epidemia sobre el tiempo y poner en evidencia cuándo y dónde es que las medidas aplicadas parecen ayudar a "frenar la línea" (en este caso) de crecimiento exponencial.

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

| Estado              | Nuevos casos confirmados por fecha de síntomas | Cambio esperado en nuevos casos | Número de reproducción efectiva | Tiempo de duplicación / reducción a la mitad (días) |
|---------------------|------------------------------------------------|---------------------------------|---------------------------------|-----------------------------------------------------|
| AGUASCALIENTES      | 13 (4 -- 21)                                   | Incierto                        | 1 (0.5 -- 1.4)                  | -180 (7.4 -- -6.7)                                  |
| BAJA CALIFORNIA     | 138 (105 -- 162)                               | Aumentando                      | 1.5 (1.2 -- 1.7)                | 8.3 (5.6 -- 16)                                     |
| BAJA CALIFORNIA SUR | 9 (2 -- 15)                                    | Incierto                        | 1.1 (0.5 -- 1.6)                | 82 (5.1 -- -5.7)                                    |
| CAMPECHE            | 12 (4 -- 20)                                   | Probablemente aumentando        | 1.5 (0.8 -- 2.2)                | 8.6 (3.4 -- -14)                                    |
| CHIAPAS             | 16 (6 -- 24)                                   | Incierto                        | 1.1 (0.6 -- 1.5)                | 46 (6.3 -- -8.4)                                    |
| CHIHUAHUA           | 42 (26 -- 57)                                  | Probablemente aumentando        | 1.2 (0.9 -- 1.5)                | 17 (7.1 -- -38)                                     |
| CIUDAD DE MEXICO    | 437 (381 -- 483)                               | Aumentando                      | 1.2 (1.1 -- 1.3)                | 21 (13 -- 46)                                       |
| COAHUILA            | 15 (6 -- 24)                                   | Incierto                        | 1 (0.6 -- 1.4)                  | 75 (7 -- -8.4)                                      |
| DURANGO             | 6 (1 -- 11)                                    | Incierto                        | 1.2 (0.4 -- 1.9)                | 42 (3.5 -- -4.3)                                    |
| GUANAJUATO          | 15 (6 -- 24)                                   | Incierto                        | 1.1 (0.6 -- 1.5)                | 74 (6.6 -- -7.7)                                    |
| GUERRERO            | 25 (12 -- 36)                                  | Incierto                        | 1.2 (0.8 -- 1.5)                | 30 (6.9 -- -13)                                     |
| HIDALGO             | 28 (14 -- 39)                                  | Probablemente aumentando        | 1.2 (0.8 -- 1.6)                | 17 (6 -- -20)                                       |
| JALISCO             | 29 (15 -- 41)                                  | Probablemente aumentando        | 1.3 (0.9 -- 1.8)                | 13 (5.3 -- -32)                                     |
| MEXICO              | 288 (245 -- 327)                               | Aumentando                      | 1.2 (1.1 -- 1.3)                | 19 (12 -- 53)                                       |
| MICHOACAN           | 19 (7 -- 28)                                   | Incierto                        | 0.9 (0.6 -- 1.3)                | -23 (14 -- -6.1)                                    |
| MORELOS             | 58 (39 -- 76)                                  | Probablemente aumentando        | 1.3 (1 -- 1.6)                  | 13 (6.5 -- 320)                                     |
| NACIONAL            | 1577 (1478 -- 1673)                            | Aumentando                      | 1.2 (1.1 -- 1.2)                | 22 (17 -- 33)                                       |
| NAYARIT             | 13 (4 -- 21)                                   | Probablemente aumentando        | 1.4 (0.7 -- 2)                  | 10 (3.8 -- -15)                                     |
| NUEVO LEON          | 33 (20 -- 47)                                  | Probablemente aumentando        | 1.3 (0.9 -- 1.7)                | 11 (5.2 -- -170)                                    |
| OAXACA              | 12 (4 -- 20)                                   | Incierto                        | 1.3 (0.7 -- 1.9)                | 13 (4.1 -- -11)                                     |
| PUEBLA              | 45 (27 -- 61)                                  | Incierto                        | 1.1 (0.8 -- 1.4)                | 31 (8.9 -- -19)                                     |
| QUERETARO           | 9 (2 -- 15)                                    | Incierto                        | 1.3 (0.6 -- 2)                  | 12 (3.5 -- -8.4)                                    |
| QUINTANA ROO        | 31 (17 -- 43)                                  | Likely decreasing               | 0.9 (0.6 -- 1.1)                | -18 (32 -- -7)                                      |
| SAN LUIS POTOSI     | 16 (6 -- 25)                                   | Probablemente aumentando        | 1.5 (0.8 -- 2)                  | 9.5 (3.9 -- -22)                                    |
| SINALOA             | 52 (33 -- 69)                                  | Incierto                        | 1.1 (0.8 -- 1.3)                | 36 (9.7 -- -21)                                     |
| SONORA              | 27 (14 -- 39)                                  | Probablemente aumentando        | 1.4 (1 -- 1.9)                  | 9.6 (4.5 -- -59)                                    |
| TABASCO             | 59 (38 -- 77)                                  | Incierto                        | 1 (0.8 -- 1.2)                  | 600 (14 -- -15)                                     |
| TAMAULIPAS          | 17 (6 -- 26)                                   | Incierto                        | 1 (0.6 -- 1.4)                  | -450 (7.7 -- -7.2)                                  |
| TLAXCALA            | 15 (7 -- 25)                                   | Incierto                        | 1.1 (0.6 -- 1.5)                | 220 (7.1 -- -7.4)                                   |
| VERACRUZ            | 58 (40 -- 76)                                  | Probablemente aumentando        | 1.1 (0.9 -- 1.4)                | 44 (11 -- -20)                                      |
| YUCATAN             | 45 (28 -- 60)                                  | Probablemente aumentando        | 1.2 (0.8 -- 1.4)                | 22 (7.9 -- -25)                                     |
| ZACATECAS           | 9 (2 -- 15)                                    | Incierto                        | 1.3 (0.5 -- 2)                  | 13 (3.4 -- -7.3)                                    |

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

### Detalles 

Los detalles sobre la metodología se pueden encontrar en el proyecto original [https://epiforecasts.io/covid/methods.html](https://epiforecasts.io/covid/methods.html).

### Contacto 

[@DatosCovid](https://twitter.com/datoscovid)
[Correo](hola@datoscovid.mx)
