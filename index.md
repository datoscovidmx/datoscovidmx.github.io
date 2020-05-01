# Monitoreo epidemiológico de COVID-19 en México

![](https://pbs.twimg.com/profile_banners/1251773678636933120/1587470790/1500x500)

# Resumen al 28 de abril de 2020

Para detalles sobre el equipo que trabajó esta implementación y cómo mantendremos actualizado el observatorio: [contexto sobre el observatorio de datos COVID Mx](https://github.com/datoscovidmx/datoscovidmx.github.io/blob/master/README.md)

# ¿Por qué corregir los casos confirmados?

- Los casos confirmados son una muestra estadística que contiene una serie de retrasos importantes entre el número que vemos en el presente y el día que sucedió dicha infección, estos retrasos los comprenden mayormente dos fenómenos:
1. El retraso en el tiempo existente entre la fecha de inicio de síntomas del paciente y la fecha de confirmación oficial del caso.
2. El tiempo que necesita el virus para incubarse en el cuerpo.
 
- Al pasar de las fechas de confirmación a las fechas de inicio de sintomas, es importante tener en cuenta que la cantidad total de casos confirmados tendrá dicho retraso contra la cantidad de casos que realmente han aparecido, ya que existe un retraso entre la aparición y la contabilización del caso en la confirmación. 

- Para tener en cuenta esto, se tiene que reescalar el número estimado de casos de casos corregidos hacia el presente. Dicho re escalamiento fue efectuado con una regresión negativa binomial, que permite, después de transformar las fechas de confirmación a fechas de inicio de sintomas y contar el número de casos por día, obtener una muestra de la cantidad de casos que posiblemente ocurrieron pero que no se confirmaron.

# ¿Por qué monitorear R en el tiempo? Explicación de Rt.

**<img src="https://render.githubusercontent.com/render/math?math=R(t)">  es una medida clave de qué tan rápido está creciendo el virus: es el número promedio de personas infectadas por una persona infecciosa.**
1. Si Rt está por encima de 1.0, el virus se propagará rápidamente.
2. Cuando Rt está por debajo de 1.0, el virus se irá propagando cada vez menos.

- En cualquier epidemia, <img src="https://render.githubusercontent.com/render/math?math=R(t)">  es la medida conocida como la tasa de reproducción efectivo. Es el número de personas que se infectan por persona infectada en el momento <img src="https://render.githubusercontent.com/render/math?math=t">. La versión más conocida de este número es la tasa de reproducción básica <img src="https://render.githubusercontent.com/render/math?math=R_0">  que es la tasa de reproducción al inicio de la pandemia. Sin embargo, esta medida pasa por alto los cambios de comportamiento y política pública y no nos ayuda a evaluar intervenciones como la cuarentena y el distanciamiento social.

- Dicho de otra forma, el valor de <img src="https://render.githubusercontent.com/render/math?math=R(t)">  nos ayuda a:
1. Evaluar que tan efectivas han sido las medidas tomadas para controlar un brote.
2. decidir si debemos aumentar o reducir las restricciones para tratar de equilibrar la parte económica con el problema de salud pública.
 
- Las gráficas muestran una linea punteada por encima de <img src="https://render.githubusercontent.com/render/math?math=R(t)=1">  ya que es el valor objetivo para contener la epidemia. **Para que la epidemia se logre mitigar, las bandas de estimación deben estar en 1 o por debajo de 1, por un lapso de tiempo.**

- A pesar que una tendencia a la baja es un señal positivo de control de la epidemia, mientras el número no se encuentre por debajo de 1 durante un lapso de tiempo suficiente como para que el rastreo epidemiológico de los casos vuelva a ser posible, seguiran existiendo casos diarios y en ese caso no se puede concluir que exista dicho control sobre la epidemia.

## Tabla de contenido

  * [Resumen Nacional](#resumen-nacional)
  * [Distribución geográfica epidemiológica dado el Rt estimado](#distribución-geográfica-epidemiológica-dado-el-rt-estimado)
  * [México en el contexto mundial: ¿Estamos desacelerando?](#méxico-en-el-contexto-mundial-¿estamos-desacelerando?)
  * [Monitoreo para estados con mayor crecimiento esperado](#monitoreo-para-estados-con-mayor-crecimiento-esperado)
    + [Casos confirmados contra casos estimados](#casos-confirmados-contra-casos-estimados)
    + [Evolución de la tasa de reproducción efectiva (Rt)](#evolución-de-la-tasa-de-reproducción-efectiva-rt)
  * [Monitoreo para el resto de los estados](#monitoreo-para-el-resto-de-los-estados)
    + [Casos confirmados contra casos estimados](#casos-confirmados-contra-casos-estimados-1)
    + [Evolución de la tasa de reproducción efectiva (Rt)](#evolución-de-la-tasa-de-reproducción-efectiva-rt-para-el-resto-de-los-estados)
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

<center>Resúmen nacional. </i>(barra clara = intervalo de credibilidad al 90%; barra oscura = intervalo de credibilidad al 50%.</i></center>
<br>

Los estados están ordenados por el número de casos diarios confirmados esperados y codificados por color según el cambio esperado en los casos diarios confirmados.

**La línea punteada indica el valor objetivo de 1 para la tasa efectiva de reproducción que se requiere para el control**

## Distribución geográfica epidemiológica dado el Rt estimado

<iframe is="x-frame-bypass" src='https://flo.uri.sh/visualisation/2194592/embed' frameborder='0' scrolling='no' style='width:100%;height:600px;'></iframe>

## México en el contexto global: ¿qué tan efectivo ha sido para disminuir el crecimiento exponencial?

<iframe is="x-frame-bypass" src='https://htmlpreview.github.io/?https://raw.githubusercontent.com/marianarf/covid19_mexico_analysis/master/plot.html' frameborder='0' scrolling='no' style='width:100%;height:600px;'></iframe>

¿Vamos ganando o  perdiendo la batalla contra COVID-19? ¿Cómo sabemos si las medidas para frenar la epidemia están funcionando? Esta gráfica interactiva usa escalas logarítmicas, de modo que el el crecimiento exponencial puro se ve como una línea recta. El uso de estas escalas también tiende a acentuar el crecimiento o disminución en el comportamiento de la pandemia para mostrar visualmente la evolución de la epidemia sobre el tiempo y poner en evidencia cuándo y dónde es que las medidas aplicadas parecen ayudar a "frenar la línea" (en este caso) de crecimiento exponencial.

## Monitoreo para estados con mayor crecimiento esperado

Dado nuestro análisis, en los siguientes estados se esperan más casos confirmados diarios:

- Baja California
- Zacatecas
- Chihuahua
- Jalisco
- Ciudad de México
- Sinaloa

### Casos confirmados contra casos estimados

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/mexico/regional-summary/high_cases_plot.png)

<center>Casos confirmados. <i>(barras) y casos estimados (banda clara = intervalo de credibilidad al 90%; banda obscura = intervalo de credibilidad al 50%). La confianza en los valores estimados se indica por transparencia: una transparencia alta corresponde a una confianza reducida.</i></center>
<br>
*Es de notar que la estimación, no llega al dia en el que actualizamos el reporte, dado que la estimación depende del retraso anteriormente citado, que es en promedio de alrededor de 10 días*.

### Evolución de la tasa de reproducción efectiva (Rt)

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/mexico/regional-summary/high_cases_rt_plot.png)

<center>Cambios en la tasa de reproducción efectiva (banda clara = intervalo de credibilidad al 90%; banda obscura = intervalo de credibilidad al 50%). La confianza en los valores estimados se indica por transparencia, una transparencia alta corresponde a una confianza reducida.</center>
<br>

## Monitoreo para el resto de los estados

- **Solo se incluyen estados con al menos 10 casos confirmados en un día para este análisis.**

### Casos confirmados contra casos estimados

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/mexico/regional-summary/cases_plot.png)

### Evolución de la tasa de reproducción efectiva (Rt) para el resto de los estados

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/mexico/regional-summary/rt_plot.png)

## Resumen final

| State               | New confirmed cases by infection date | Expected change in daily cases | Effective reproduction no. |
|---------------------|---------------------------------------|--------------------------------|----------------------------|
| AGUASCALIENTES      | 43 (0 -- 134)                         | Unsure                         | 1.9 (0.1 -- 4.1)           |
| BAJA CALIFORNIA     | 76 (0 -- 209)                         | Unsure                         | 1 (0.3 -- 1.9)             |
| BAJA CALIFORNIA SUR | 36 (0 -- 78)                          | Unsure                         | 2.3 (0.1 -- 4.3)           |
| CAMPECHE            | 47 (0 -- 138)                         | Likely increasing              | 3.2 (0 -- 6.8)             |
| CHIAPAS             | 22 (0 -- 42)                          | Likely increasing              | 1.7 (0.5 -- 2.7)           |
| CHIHUAHUA           | 61 (0 -- 192)                         | Unsure                         | 1.7 (0.1 -- 3.6)           |
| CIUDAD DE MEXICO    | 90 (13 -- 175)                        | Decreasing                     | 0.6 (0.4 -- 0.9)           |
| COAHUILA            | 43 (0 -- 125)                         | Unsure                         | 1.8 (0.1 -- 3.8)           |
| DURANGO             | 35 (0 -- 72)                          | Likely increasing              | 3.1 (0.1 -- 6)             |
| GUANAJUATO          | 44 (0 -- 128)                         | Unsure                         | 1.9 (0.1 -- 4)             |
| GUERRERO            | 38 (0 -- 76)                          | Likely increasing              | 1.8 (0.4 -- 3.1)           |
| HIDALGO             | 32 (0 -- 65)                          | Likely increasing              | 1.6 (0.5 -- 2.7)           |
| JALISCO             | 56 (0 -- 183)                         | Unsure                         | 2 (0.1 -- 4.8)             |
| MEXICO              | 55 (5 -- 105)                         | Decreasing                     | 0.6 (0.3 -- 0.9)           |
| MICHOACAN           | 33 (2 -- 66)                          | Likely increasing              | 1.5 (0.5 -- 2.4)           |
| MORELOS             | 37 (2 -- 68)                          | Likely increasing              | 1.5 (0.6 -- 2.3)           |
| NUEVO LEON          | 33 (0 -- 70)                          | Unsure                         | 1.9 (0.2 -- 3.5)           |
| PUEBLA              | 37 (2 -- 70)                          | Unsure                         | 1.2 (0.5 -- 1.9)           |
| QUINTANA ROO        | 29 (0 -- 57)                          | Unsure                         | 1 (0.3 -- 1.5)             |
| SAN LUIS POTOSI     | 27 (0 -- 52)                          | Likely increasing              | 3.3 (0.5 -- 6.2)           |
| SINALOA             | 52 (0 -- 151)                         | Unsure                         | 1 (0.1 -- 1.7)             |
| SONORA              | 40 (0 -- 87)                          | Likely increasing              | 2.2 (0.3 -- 4.3)           |
| TABASCO             | 48 (4 -- 87)                          | Unsure                         | 0.9 (0.4 -- 1.3)           |
| TAMAULIPAS          | 41 (3 -- 79)                          | Likely increasing              | 1.5 (0.5 -- 2.4)           |
| TLAXCALA            | 32 (0 -- 60)                          | Likely increasing              | 1.9 (0.5 -- 3.2)           |
| VERACRUZ            | 50 (0 -- 93)                          | Unsure                         | 1.2 (0.5 -- 1.9)           |
| YUCATAN             | 42 (3 -- 77)                          | Likely increasing              | 1.5 (0.6 -- 2.4)           |
| ZACATECAS           | 68 (0 -- 201)                         | Likely increasing              | 4.3 (0 -- 9.8)             |

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

[@DatosCovid](https://twitter.com/datoscovid)
[Correo](hola@datoscovid.mx)
