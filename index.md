- [Seguimiento semanal de COVID-19 en México](#seguimiento-semanal-de-covid-19-en-méxico)
- [Resumen al 16 de Abril de 2020](#resumen-al-16-de-abril-de-2020)
 - [Estados con estimación de casos nuevos diarios más alta](#estados-con-estimación-de-casos-nuevos-diarios-más-alta)
  - [Casos confirmados vs Casos Estimados](#casos-confirmados-vs-casos-estimados)
  - [Variación de la tasa efectiva de reproducción](#variación-de-la-tasa-efectiva-de-reproducción)
 - [Estimaciones para el resto de los estados](#estimaciones-para-el-resto-de-los-estados)
  - [Casos confirmados vs casos Estimados](#casos-confirmados-vs-casos-estimados-1)
  - [Variación de la tasa efectiva de reproducción](#variación-de-la-tasa-efectiva-de-reproducción-1)
 - [Resúmen Nacional](#resúmen-nacional)
 - [Metodología](#metodología)
  - [Datos](#datos)
  - [Supuestos](#supuestos)
  - [Limitaciones](#limitaciones)
  - [Detalles](#detalles)

# Seguimiento semanal de COVID-19 en México
# Resumen al 16 de abril de 2020

Para detalles sobre el equipo que trabajó esta implementación, y como la mantendrémos actualizada: [Contexto sobre el observatorio de datos COVID Mx](https://github.com/datoscovidmx/datoscovidmx.github.io/blob/master/README.md)

## Estados con estimación de casos nuevos diarios más alta

- Ciudad de México
- Estado de México
- Baja California
- Baja California Sur
- Puebla
- Sinaloa

### Casos confirmados vs casos estimados

Los casos estimados se obtienen apartir de corregir los datos confirmados teniendo en cuenta el retraso entre la confirmación del caso y la fecha de inicio de sintomas más el periodo de incubación del virus.

Las áreas sombreadas representan mejor la evolución epidemiológica de las entidades que los casos confirmados diarios o acumulados, podemos entender esta gráfica como una corrección al conteo. 

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/2020-04-16/regional-summary/high_cases_plot.png)

<center>Casos confirmados (barras) y casos estimados (banda clara = intervalo de credibilidad al 90%; banda obscura = intervalo de credibilidad al 50%).</center>
<br>
<br>
*Es de notar que la estimación, no llega al dia en el que actualizamos el reporte, dado que la estimación depende del retraso anteriormente citado, que es en promedio de alrededor de 10 días*.

### Variación de la tasa efectiva de reproducción 

La tasa efectiva de reproducción (R) es un número que mide el potencial de transmisibilidad que tiene una enfermedad infecciosa en una población con individuos suceptibles y no suceptibles (decesos o personas ya contagiadas). En palabras simples, es el promedio de personas infectadas por cada infectado.

Este tasa depende de diversos factores entre ellos:
- **El promedio de contacto entre los individuos de la población**.
- La capacidad infecciosa del virus (que facilidad tiene para migrar entre huesped y huesped).
- El periodo en el que una persona es infecciosa mientras está infectada.

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/2020-04-16/regional-summary/high_cases_rt_plot.png)

<center>Cambios en la tasa de reproducción efectiva (banda clara = intervalo de credibilidad al 90%; banda obscura = intervalo de credibilidad al 50%).</center>
<br>
<br>
Esta gráfica es de especial interés, ya que el cambio de R en el tiempo responde a intervenciones / politicas públicas (ej. cuarentena, distanciamiento social) o la falta de dichas intervenciones (caso omiso de las medidas de salubridad).

El distanciamiento social disminuye el valor de R en el tiempo, mientras que el caso omiso lo eleva. Las gráficas muestran una linea punteada sobre *R = 1* ya que es el valor objetivo para contener la epidemia, es decir, para que la epidemia se logre mitigar, ambas bandas de la estimación (claras y obscuras) deben encontrarse sobre 1 o por debajo de 1.

Observar una tendencia a la baja es un signo positivo en relación al control de la epidemia, sin embargo mientras el número no se encuentre por debajo de 1, seguiran existiendo casos diarios y no se puede concluir que existe un control sobre la epidemia.

## Estimaciones para el resto de los estados

- Solo se incluyen estados con al menos 10 casos confirmados en un día para este análisis.

### Casos confirmados vs casos estimados

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/2020-04-16/regional-summary/cases_plot.png)

### Variación de la tasa efectiva de reproducción 

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/2020-04-16/regional-summary/rt_plot.png)

## Resúmen nacional

Este resúmen muestra la tasa efectiva de reproducción actual para cada estado además del estimado de casos nuevos diarios.

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/2020-04-16/regional-summary/summary_plot.png)

<center>Resúmen Nacional. (barra clara = intervalo de credibilidad al 90%; barra oscura = intervalo de credibilidad al 50%.</center>
<br>
<br>
Los estados están ordenados por el número de casos diarios confirmados esperados y codificados por color según el cambio esperado en los casos diarios confirmados. 

**La línea punteada indica el valor objetivo de 1 para la tasa efectiva de reproducción que se requiere para el control**

## Mapa
<iframe src='https://flo.uri.sh/visualisation/2051179/embed' frameborder='0' scrolling='no' style='width:100%;height:600px;'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/2051179/?utm_source=embed&utm_campaign=visualisation/2051179' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>
<br>
<br>
---
## Métodología

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
