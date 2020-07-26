# Observatorio de datos de COVID-19 en México.
[@DatosCovid](https://twitter.com/datoscovid)

# Directorio de colaboradores en Github

[Colaboradores de Github](https://github.com/orgs/datoscovidmx/people)

## Nacimiento del Observatorio

Esta iniciativa nace de una colaboración de las principales comunidades de ciencia de datos y desarrollo tecnológico en el país:
- [DataLab Community](https://www.facebook.com/datalabmx/)
- [Data Science Monterrey](https://www.facebook.com/groups/469523539899326/)
- [SoCieDat](https://www.facebook.com/sociedat/)
- [Zapopan Lab](https://www.facebook.com/zapopanlab/)

En un inicio esta colaboración se centró en hacer llegar algunas observaciones técnicas al primer modelo empleado en el gobierno de Jalisco, el cuál contenia algunos detalles metodológicos que nos parecía eran dignos de comentar, a raíz de esto, trabajamos en la implementación de un modelo epidemiológico tipo [SEIR](https://colab.research.google.com/drive/1Sn2bxaEQOsaOKFTKchtz7rjWO1ZAGjR9#scrollTo=dvhCYYvTDqAB) público y accesible, que dicho sea de paso, el gobierno de Jalisco adoptó a través de la Universidad de Guadalajara.

Sin embargo, una vez proporcionado el modelo por nuestra parte, los especialistas de la Universidad de Guadalajara le dieron seguimiento, los términos en los que concretamos la cesión del modelo se encuentran detallados en la siguiente carta:

<blockquote class="twitter-tweet"><p lang="es" dir="ltr">Comparto la carta con la que iniciamos la plática de hoy. Para el público en general y evitar confusiones.<br><br>Saludos. <a href="https://t.co/kbbQkak9LS">pic.twitter.com/kbbQkak9LS</a></p>&mdash; Miguel Núñez (@NunezKant) <a href="https://twitter.com/NunezKant/status/1246326695654756353?ref_src=twsrc%5Etfw">April 4, 2020</a></blockquote> 

Después de ese intercambio, nos pareció que más allá de implementar un modelo de predicción de infectados, necesitabamos implementar una herramienta que le diera seguimiento a la evolución epidemiológica del país, dónde sea observarble el efecto de las políticas públicas como las cuarentenas.

## Seguimiento semanal epidemiológico en México

Por eso hicimos una implementación regional de la metodología utilizada por el [Centro de Modelado Matemático para Enfermedades Infecciosas](https://cmmid.github.io/) descrito en [https://epiforecasts.io/covid/](https://epiforecasts.io/covid/).

La implementación permite identificar los cambios en el **número de reproducción** <img src="https://render.githubusercontent.com/render/math?math=(R_e(t))"> y **casos diarios** durante el brote de COVID-19 a nivel nacional y subnacional, teniendo en cuenta posibles sesgos debido a retrasos en la notificación de los casos confirmados y el subreporte, dicho análisis será actualizado semana a semana con los datos oficiales nacionales.

## Datos

- Los datos utilizados provienen del reporte técnico diario federal de la Secretaría de Salud (InDRE) de México.
- Las gráficas por estado y los datos para generarlas se pueden obtener en [(https://github.com/datoscovidmx/covid-nowcasts-mexico)](https://github.com/datoscovidmx/covid-nowcasts-mexico).
