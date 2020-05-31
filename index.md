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

| Estado              | Nuevos casos confirmados por fecha de síntomas | Cambio esperado en nuevos casos | Número de reproducción efectiva | Tiempo de duplicación / reducción a la mitad (días) |                  |
|---------------------|------------------------------------------------|---------------------------------|---------------------------------|-----------------------------------------------------|------------------|
| AGUASCALIENTES      | 29 (14 -- 41)                                  | Incierto                        | 1.1 (0.8 -- 1.5)                | 44 (7.9 -- -12)                                     | 44 (7.9 -- -12)  |
| BAJA CALIFORNIA     | 146 (117 -- 178)                               | Incierto                        | 1.1 (0.9 -- 1.2)                | 58 (16 -- -38)                                      | 58 (16 -- -38)   |
| BAJA CALIFORNIA SUR | 12 (4 -- 19)                                   | Incierto                        | 1.1 (0.5 -- 1.5)                | 47 (5.5 -- -7.3)                                    | 47 (5.5 -- -7.3) |
| CAMPECHE            | 24 (11 -- 35)                                  | Probablemente aumentando        | 1.2 (0.8 -- 1.6)                | 15 (5.5 -- -21)                                     | 15 (5.5 -- -21)  |
| CHIAPAS             | 98 (74 -- 121)                                 | Aumentando                      | 1.2 (1 -- 1.5)                  | 16 (8.4 -- 180)                                     | 16 (8.4 -- 180)  |
| CHIHUAHUA           | 58 (37 -- 73)                                  | Probablemente aumentando        | 1.2 (0.9 -- 1.5)                | 17 (7.4 -- -54)                                     | 17 (7.4 -- -54)  |
| CIUDAD DE MEXICO    | 884 (808 -- 958)                               | Probablemente aumentando        | 1.1 (1 -- 1.1)                  | 51 (26 -- 1800)                                     | 51 (26 -- 1800)  |
| COAHUILA            | 42 (24 -- 56)                                  | Aumentando                      | 1.3 (1 -- 1.7)                  | 11 (5.5 -- -170)                                    | 11 (5.5 -- -170) |
| COLIMA              | 9 (2 -- 15)                                    | Incierto                        | 1.4 (0.5 -- 2.1)                | 13 (3.5 -- -7.3)                                    | 13 (3.5 -- -7.3) |
| DURANGO             | 18 (7 -- 27)                                   | Probablemente aumentando        | 1.4 (0.8 -- 2)                  | 9.9 (4 -- -22)                                      | 9.9 (4 -- -22)   |
| GUANAJUATO          | 65 (45 -- 85)                                  | Probablemente aumentando        | 1.2 (0.9 -- 1.4)                | 17 (7.9 -- -99)                                     | 17 (7.9 -- -99)  |
| GUERRERO            | 91 (69 -- 117)                                 | Aumentando                      | 1.4 (1.1 -- 1.6)                | 10 (6.1 -- 27)                                      | 10 (6.1 -- 27)   |
| HIDALGO             | 82 (61 -- 104)                                 | Aumentando                      | 1.2 (1 -- 1.5)                  | 17 (8.1 -- -140)                                    | 17 (8.1 -- -140) |
| JALISCO             | 62 (41 -- 80)                                  | Probablemente aumentando        | 1.2 (0.9 -- 1.4)                | 23 (8.9 -- -40)                                     | 23 (8.9 -- -40)  |
| MEXICO              | 724 (663 -- 795)                               | Aumentando                      | 1.4 (1.2 -- 1.5)                | 10 (8.4 -- 14)                                      | 10 (8.4 -- 14)   |
| MICHOACAN           | 86 (58 -- 107)                                 | Probablemente aumentando        | 1.2 (0.9 -- 1.4)                | 24 (9.5 -- -50)                                     | 24 (9.5 -- -50)  |
| MORELOS             | 30 (15 -- 42)                                  | Incierto                        | 1.1 (0.8 -- 1.5)                | 19 (6.3 -- -20)                                     | 19 (6.3 -- -20)  |
| NAYARIT             | 22 (10 -- 32)                                  | Probablemente aumentando        | 1.3 (0.8 -- 1.7)                | 13 (5.1 -- -20)                                     | 13 (5.1 -- -20)  |
| NUEVO LEON          | 50 (32 -- 66)                                  | Incierto                        | 1.1 (0.9 -- 1.4)                | 66 (10 -- -15)                                      | 66 (10 -- -15)   |
| OAXACA              | 54 (34 -- 72)                                  | Probablemente disminuyendo      | 0.9 (0.7 -- 1.1)                | -17 (94 -- -7.7)                                    | -17 (94 -- -7.7) |
| PUEBLA              | 138 (106 -- 162)                               | Aumentando                      | 1.3 (1.1 -- 1.5)                | 14 (8.1 -- 42)                                      | 14 (8.1 -- 42)   |
| QUERETARO           | 36 (21 -- 49)                                  | Incierto                        | 1 (0.7 -- 1.2)                  | -63 (14 -- -9.7)                                    | -63 (14 -- -9.7) |
| QUINTANA ROO        | 45 (29 -- 61)                                  | Incierto                        | 1.1 (0.8 -- 1.3)                | 39 (9.7 -- -19)                                     | 39 (9.7 -- -19)  |
| SAN LUIS POTOSI     | 43 (27 -- 58)                                  | Probablemente aumentando        | 1.2 (0.9 -- 1.5)                | 17 (7 -- -38)                                       | 17 (7 -- -38)    |
| SINALOA             | 126 (97 -- 149)                                | Aumentando                      | 1.2 (1 -- 1.4)                  | 16 (8.9 -- 75)                                      | 16 (8.9 -- 75)   |
| SONORA              | 91 (65 -- 111)                                 | Probablemente aumentando        | 1.2 (1 -- 1.4)                  | 21 (9.7 -- -88)                                     | 21 (9.7 -- -88)  |
| TABASCO             | 128 (102 -- 159)                               | Probablemente aumentando        | 1.1 (0.9 -- 1.3)                | 39 (13 -- -45)                                      | 39 (13 -- -45)   |
| TAMAULIPAS          | 53 (34 -- 70)                                  | Probablemente aumentando        | 1.2 (0.9 -- 1.5)                | 17 (7.2 -- -42)                                     | 17 (7.2 -- -42)  |
| TLAXCALA            | 59 (39 -- 77)                                  | Aumentando                      | 1.4 (1 -- 1.7)                  | 10 (5.5 -- 59)                                      | 10 (5.5 -- 59)   |
| VERACRUZ            | 195 (160 -- 226)                               | Aumentando                      | 1.3 (1.1 -- 1.4)                | 15 (9.2 -- 36)                                      | 15 (9.2 -- 36)   |
| YUCATAN             | 52 (33 -- 68)                                  | Incierto                        | 1 (0.8 -- 1.2)                  | 160 (12 -- -15)                                     | 160 (12 -- -15)  |
| ZACATECAS           | 9 (2 -- 15)                                    | Incierto                        | 1.3 (0.6 -- 2)                  | 10 (3.4 -- -10)                                     | 10 (3.4 -- -10)  |
| ZACATECAS           | 9 (2 -- 15)                                    | Unsure                          | 1.3 (0.5 -- 2)                  | 13 (3.4 -- -7.3)                                    |                  |                                   |

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
