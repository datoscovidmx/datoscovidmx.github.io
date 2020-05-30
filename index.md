![](https://pbs.twimg.com/profile_banners/1251773678636933120/1587470790/1500x500)

# Resumen al 28 de mayo de 2020

[Equipo de trabajo del Observatorio de Datos COVID MX](https://github.com/datoscovidmx/datoscovidmx.github.io/blob/master/README.md)

# ¿Por qué corregir los casos confirmados?

- Los casos confirmados son una muestra estadística que contiene una serie de retrasos entre el número que vemos en el presente y el día que sucedió dicha infección, por ejemplo:

  1) El retraso en el tiempo existente entre la fecha de inicio de síntomas del paciente y la fecha de confirmación oficial del caso.
  2) El tiempo que necesita el virus para incubarse en el cuerpo después del contagio (período de incubación)

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

<iframe is="x-frame-bypass" src='https://flo.uri.sh/visualisation/2607410/embed' frameborder='0' scrolling='no' style='width:100%;height:600px;'></iframe>
<br>
<center>*El número de casos que se muestran en el mapa corresponden a los estimados bajos y el altos del modelo, respectivamente. R(t) representa el valor promedio de los estimados. Para más información, consultar la tabla de resultados.</center>.

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
| AGUASCALIENTES      | 29 (16 -- 41)                                  | Unsure                          | 1.1 (0.8 -- 1.5)                | 48 (7.9 -- -11)                                     |
| BAJA CALIFORNIA     | 146 (118 -- 178)                               | Unsure                          | 1.1 (0.9 -- 1.2)                | 55 (16 -- -38)                                      |
| BAJA CALIFORNIA SUR | 12 (3 -- 20)                                   | Unsure                          | 1.1 (0.6 -- 1.6)                | 38 (5.2 -- -7.3)                                    |
| CAMPECHE            | 24 (11 -- 34)                                  | Likely increasing               | 1.2 (0.8 -- 1.6)                | 15 (5.5 -- -22)                                     |
| CHIAPAS             | 98 (72 -- 122)                                 | Increasing                      | 1.2 (1 -- 1.5)                  | 16 (8.4 -- 450)                                     |
| CHIHUAHUA           | 57 (39 -- 75)                                  | Likely increasing               | 1.2 (0.9 -- 1.5)                | 18 (7.6 -- -52)                                     |
| CIUDAD DE MEXICO    | 881 (816 -- 955)                               | Likely increasing               | 1.1 (1 -- 1.1)                  | 52 (27 -- 990)                                      |
| COAHUILA            | 42 (27 -- 58)                                  | Increasing                      | 1.3 (1 -- 1.7)                  | 12 (5.6 -- -120)                                    |
| COLIMA              | 9 (2 -- 15)                                    | Unsure                          | 1.4 (0.6 -- 2.1)                | 14 (3.4 -- -6.9)                                    |
| DURANGO             | 18 (7 -- 27)                                   | Likely increasing               | 1.4 (0.8 -- 2)                  | 10 (4 -- -18)                                       |
| GUANAJUATO          | 65 (44 -- 84)                                  | Likely increasing               | 1.2 (0.9 -- 1.4)                | 17 (7.8 -- -93)                                     |
| GUERRERO            | 91 (69 -- 116)                                 | Increasing                      | 1.4 (1.1 -- 1.6)                | 10 (6.2 -- 26)                                      |
| HIDALGO             | 82 (60 -- 104)                                 | Increasing                      | 1.2 (1 -- 1.5)                  | 18 (8.2 -- -130)                                    |
| JALISCO             | 63 (42 -- 81)                                  | Likely increasing               | 1.2 (0.9 -- 1.4)                | 23 (8.8 -- -39)                                     |
| MEXICO              | 722 (649 -- 785)                               | Increasing                      | 1.4 (1.2 -- 1.5)                | 10 (8.4 -- 14)                                      |
| MICHOACAN           | 86 (60 -- 107)                                 | Likely increasing               | 1.2 (0.9 -- 1.4)                | 24 (9.7 -- -53)                                     |
| MORELOS             | 31 (18 -- 44)                                  | Unsure                          | 1.1 (0.8 -- 1.5)                | 18 (6.2 -- -21)                                     |
| NACIONAL            | 3532 (3353 -- 3665)                            | Increasing                      | 1.2 (1.1 -- 1.2)                | 21 (18 -- 27)                                       |
| NAYARIT             | 22 (10 -- 32)                                  | Likely increasing               | 1.3 (0.8 -- 1.7)                | 13 (5 -- -21)                                       |
| NUEVO LEON          | 50 (29 -- 64)                                  | Unsure                          | 1.1 (0.8 -- 1.4)                | 72 (11 -- -15)                                      |
| OAXACA              | 54 (35 -- 71)                                  | Likely decreasing               | 0.9 (0.7 -- 1.1)                | -17 (130 -- -7.8)                                   |
| PUEBLA              | 136 (107 -- 162)                               | Increasing                      | 1.3 (1.1 -- 1.5)                | 14 (8.3 -- 44)                                      |
| QUERETARO           | 36 (19 -- 48)                                  | Unsure                          | 1 (0.7 -- 1.2)                  | -60 (14 -- -9.6)                                    |
| QUINTANA ROO        | 45 (29 -- 61)                                  | Unsure                          | 1.1 (0.8 -- 1.3)                | 39 (9.7 -- -19)                                     |
| SAN LUIS POTOSI     | 43 (25 -- 59)                                  | Likely increasing               | 1.2 (0.9 -- 1.5)                | 16 (6.8 -- -40)                                     |
| SINALOA             | 127 (99 -- 152)                                | Increasing                      | 1.2 (1 -- 1.4)                  | 16 (8.8 -- 67)                                      |
| SONORA              | 92 (70 -- 117)                                 | Likely increasing               | 1.2 (1 -- 1.4)                  | 21 (9.4 -- -98)                                     |
| TABASCO             | 59 (38 -- 77)                                  | Unsure                          | 1 (0.8 -- 1.2)                  | 600 (14 -- -15)                                     |
| TAMAULIPAS          | 17 (6 -- 26)                                   | Unsure                          | 1 (0.6 -- 1.4)                  | -450 (7.7 -- -7.2)                                  |
| TLAXCALA            | 15 (7 -- 25)                                   | Unsure                          | 1.1 (0.6 -- 1.5)                | 220 (7.1 -- -7.4)                                   |
| VERACRUZ            | 58 (40 -- 76)                                  | Likely increasing               | 1.1 (0.9 -- 1.4)                | 44 (11 -- -20)                                      |
| YUCATAN             | 45 (28 -- 60)                                  | Likely increasing               | 1.2 (0.8 -- 1.4)                | 22 (7.9 -- -25)                                     |
| ZACATECAS           | 9 (2 -- 15)                                    | Unsure                          | 1.3 (0.5 -- 2)                  | 13 (3.4 -- -7.3)                                    |

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
