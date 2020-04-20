# Seguimiento semanal de COVID-19 en México

## Resumen de seguimiento al 16 de Abril de 2020

### Estados con mayor crecimiento de casos confirmados y fecha estimada de infección

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/2020-04-16/regional-summary/high_cases_plot.png)

### Número de reproducción en Estados con mayor crecimiento de casos

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/2020-04-16/regional-summary/high_cases_rt_plot.png)

### Casos confirmados y fechas estimadas de infección por Estado

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/2020-04-16/regional-summary/cases_plot.png)

### Variación del número de reproducción en el tiempo por Estado

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/2020-04-16/regional-summary/rt_plot.png)

### Último número de reproducción y conteo de casos estimado por fecha de infección

![](https://raw.githubusercontent.com/datoscovidmx/covid-nowcasts-mexico/master/2020-04-16/regional-summary/summary_plot.png)

**Notas**
- Se incluyen estados con al menos 10 casos confirmados en un día.

---
## Métodología

Hicimos una implementación basada en el trabajo experto del centro de modelaje matemático para enfermedades infecciosas, con algunas modificaciones dado el contexto nacional:

### Datos

- Los datos utilizados son los del reporte técnico diario federal de la Secretaría de Salud (InDRE) de México.

### Supuestos

- La fecha de infección fue calculada con base en un periodo de incubación promedio de 5 días.
- Las estimaciones de la tasa efectiva de reproducción son obtenidas por medio de *EpiEstim* ajustando para casos importados y optimizando una ventana móvil, asumiendo un intervalo serial promedio de 4.7 dias (95% CrI: 3.7, 6.0) y una desviación estandar de 2.9 dias (95% CrI: 1.9, 4.9).
- Estados sin un día con mínimo 10 casos nuevos confirmados, no son tomados en cuenta para el análisis.

### Limitaciones

Los resultados presentados aquí son sensibles a los cambios en las prácticas de prueba (testing) para COVID-19 y al nivel de esfuerzo realizado para detectar los casos de COVID-19. 

Si un estado amplía su capacidad de prueba y comienza a informar una mayor proporción de casos, entonces el modelo se ajustará a un valor de número de reproducción más alto, ya que solo comprende los nuevos casos en términos de la infecciosidad de los casos notificados previamente y no como resultado de mejores pruebas. Por otro lado, si un estado reduce su esfuerzo por hacer pruebas (por ejemplo, alcanzar su capacidad máxima de pruebas por día o quedarse sin pruebas), entonces el modelo estimará una caída en el número de reproducción que puede no ser una verdadera reducción. 

**Lo que es importante para que estos resultados sean imparciales, es que relacionado a las pruebas, la metodología para hacer pruebas de COVID-19 sea consistente. Esto significa que si bien un cambio en el esfuerzo por hacer pruebas, inicialmente introducirá un sesgo, esto se reducirá con el tiempo siempre que dicho esfuerzo permanezca constante a partir de ese momento.**

### Detalles 

Los detalles sobre la metodología se pueden encontrar en el proyecto original [https://epiforecasts.io/covid/methods.html](https://epiforecasts.io/covid/methods.html).
