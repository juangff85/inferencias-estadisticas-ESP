# Detección de Sesgos
> Diagoras, llamado el ateo, estando en Samotracia, uno de sus amigos le mostró varias pinturas de personas que habían soportado tormentas muy peligrosas; “Mira”, dijo, “tú que niegas la providencia, cuántos han sido salvados por sus oraciones a los dioses”. “Sí”, dijo Diágoras, “veo a los que se salvaron, pero ¿dónde están pintados los que naufragaron?”
> — Tusculanae Disputationes, Cicerón, 45 a. C.

El sesgo puede introducirse a lo largo de todo el proceso de investigación. Es útil prevenirlo o detectarlo. Algunos investigadores recomiendan adoptar una actitud escéptica ante cualquier afirmación que leas en la literatura científica. Por ejemplo, la filósofa de la ciencia Deborah Mayo (2018) escribe: “Ante la noticia estadística del día, tu primera pregunta debería ser: ¿los resultados se deben al informe selectivo, al cherry picking, o a alguno de los muchos trucos similares?”. Puede que no te hagas muy popular si esa es la primera pregunta que haces a un ponente en el próximo congreso científico al que asistas, pero al mismo tiempo sería ingenuo ignorar el hecho de que los investigadores introducen, de forma más o menos intencionada, sesgos en sus afirmaciones.

En el extremo más extremo de las prácticas que introducen sesgo en la investigación científica está la mala conducta en la investigación: inventar datos o resultados, o cambiar u omitir datos o resultados de tal manera que la investigación no esté representada con precisión en el registro de investigación. Por ejemplo, [Andrew Wakefield](https://es.wikipedia.org/wiki/Andrew_Wakefield) fue autor de un artículo fraudulento en 1998 que afirmaba un vínculo entre la vacuna contra el sarampión, las paperas y la rubéola (MMR) y el autismo. Fue retractado en 2010, pero solo después de que causara daño a la confianza en las vacunas entre algunas partes de la población general.

Otro ejemplo de la psicología se refería a un estudio de [James Vicary](https://es.wikipedia.org/wiki/James_Vicary) sobre el priming subliminal. Afirmó haber encontrado que al proyectar rápidamente 'EAT POPCORN' y 'DRINK COCA-COLA' de forma subliminal durante una película en un cine, las ventas de palomitas y Coca-Cola habían aumentado en un 57,5% y un 18,1%, respectivamente. Sin embargo, más tarde se descubrió que Vicary muy probablemente cometió fraude científico, ya que no había evidencia de que el estudio se hubiera realizado alguna vez [(Rogers, 1992-1993)](.

El sitio web Retraction Watch mantiene [una base de datos](https://retractiondatabase.org/RetractionSearch.aspx?) que rastrea las razones por las que los artículos científicos son retractados, incluyendo la fabricación de datos. Se desconoce con qué frecuencia ocurre la fabricación de datos en la práctica, pero como se discutió en el capítulo sobre integridad de la investigación, deberíamos esperar que al menos un pequeño porcentaje de científicos haya fabricado, falsificado o modificado datos o resultados al menos una vez.

**Figura 12.1:** Escena de The Dropout sobre la empresa Theranos, que afirmó falsamente tener dispositivos capaces de realizar análisis de sangre con cantidades muy pequeñas de sangre. En la escena, dos denunciantes confrontan a sus jefes cuando se les presiona para eliminar puntos de datos que no muestran los resultados deseados.

![Figura 12.1](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-1.gif)

Otra categoría diferente de errores son los errores de reporte estadístico, que van desde informar grados de libertad incorrectos hasta reportar p = 0.056 como p < 0.05 (Nuijten et al., 2015). Aunque debemos hacer todo lo posible por prevenir errores, todo el mundo los comete, y a medida que compartir datos y código se vuelve más común, será más fácil detectar errores en el trabajo de otros investigadores. Como escribe Dorothy Bishop (2018): “A medida que la ciencia abierta se convierta cada vez más en la norma, descubriremos que todos somos falibles. La reputación de los científicos dependerá no de si hay errores en su investigación, sino de cómo respondan cuando esos errores sean señalados”.

[Statcheck](http://statcheck.io/) es un software que extrae automáticamente estadísticas de artículos y recalcula sus valores p, siempre que las estadísticas se informen siguiendo las directrices de la American Psychological Association (APA). Comprueba si las estadísticas informadas son internamente consistentes: dados el estadístico de prueba y los grados de libertad, ¿es correcto el valor p informado? Si lo es, es menos probable que hayas cometido un error (aunque no evita errores coherentes). Si no lo es, deberías comprobar si toda la información de tu prueba estadística es correcta. Statcheck no es perfecto y puede cometer errores de Tipo 1, señalando algo como error cuando en realidad no lo es, pero es una herramienta fácil de usar para comprobar tus artículos antes de enviarlos a publicación, y trabajos metacientíficos iniciales sugieren que puede reducir errores de reporte estadístico (Nuijten & Wicherts, 2023).

Algunas inconsistencias en los datos son más difíciles de detectar automáticamente, pero pueden identificarse manualmente. Por ejemplo, Brown y Heathers (2017) muestran que muchos artículos informan medias que no son posibles dados el tamaño de la muestra (lo que se conoce como la prueba GRIM). Por ejemplo, Matti Heino observó en una entrada de blog que tres de las medias informadas en la tabla de un estudio clásico de Festinger y Carlsmith son matemáticamente imposibles. Con 20 observaciones por condición y una escala de −5 a 5, todas las medias deberían terminar en un múltiplo de 1/20, es decir, 0,05. Las tres medias que terminan en X.X8 o X.X2 no son consistentes con el tamaño muestral y la escala informados. Por supuesto, tales inconsistencias pueden deberse a que no se informó de que faltaban datos para algunas preguntas, pero la prueba GRIM también se ha utilizado para descubrir mala conducta científica.

**Figura 12.2:** Captura de pantalla de la tabla que informa los resultados principales del estudio de Festinger y Carlsmith (1959).

![Figura 12.2](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-2.png)

## Sesgo de publicación

El sesgo de publicación es uno de los mayores desafíos a los que se enfrenta la ciencia. El sesgo de publicación es la práctica de enviar y publicar selectivamente investigación científica, a menudo en función de si los resultados son “estadísticamente significativos” o no. La literatura científica está dominada por estos resultados estadísticamente significativos. En 1959, Sterling (1959) contó cuántas pruebas de hipótesis en cuatro revistas de psicología producían resultados significativos y encontró que 286 de 294 artículos examinados (es decir, el 97 %) rechazaban la hipótesis nula con un resultado estadísticamente significativo. Una replicación de Bozarth y Roberts (1972) obtuvo una estimación del 94 %.
Al mismo tiempo, sabemos que muchos estudios que realizan los investigadores no producen resultados significativos. Cuando los científicos solo tienen acceso a resultados significativos, pero no a todos los resultados, carecen de una visión completa de la evidencia sobre una hipótesis (Smart, 1964). En casos extremos, el informe selectivo puede conducir a una situación en la que haya cientos de resultados estadísticamente significativos en la literatura publicada, pero ningún efecto real, porque existen aún más estudios no significativos que no se comparten. Esto se conoce como el problema del cajón de archivo (file-drawer problem), cuando los resultados no significativos quedan ocultos en cajones (o hoy en día en carpetas del ordenador) y no están disponibles para la comunidad científica.
Este sesgo probablemente afecte sobre todo a la prueba principal de hipótesis que un investigador informa, ya que tener una historia interesante que contar a menudo depende del resultado de esa prueba. El sesgo es menos probable en artículos que no tienen una hipótesis principal que deba ser significativa para sostener la narrativa del manuscrito, por ejemplo cuando los investigadores simplemente describen tamaños del efecto en una gran tabla de correlaciones de múltiples pruebas realizadas. Todo científico debería trabajar para resolver el sesgo de publicación, porque es extremadamente difícil aprender qué es probablemente verdadero mientras los científicos no compartan todos sus resultados. Greenwald (1975) incluso considera que informar selectivamente solo resultados significativos constituye una violación ética.

**Figura 12.3:** Captura de las frases finales de Greenwald (1975).

![Figura 12.3](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-3.png)

El sesgo de publicación solo puede solucionarse haciendo disponibles todos los resultados de investigación a otros científicos, independientemente del valor p de la prueba principal de hipótesis. Los **Registered Reports** son una forma de combatir el sesgo de publicación, ya que este tipo de artículo científico se revisa basándose en la introducción, el método y el plan de análisis estadístico antes de recoger los datos (Chambers & Tzavella, 2022; Nosek & Lakens, 2014). Tras la revisión por expertos, el artículo puede recibir una “aceptación en principio”, lo que significa que, siempre que se siga el plan de investigación, el artículo se publicará independientemente de los resultados. Esto debería facilitar la publicación de resultados nulos.

Por ejemplo, un análisis de los primeros Registered Reports publicados en psicología reveló que 31 de 71 (44 %) observaron resultados positivos, en comparación con 146 de 152 (96 %) artículos científicos estándar comparables publicados en el mismo periodo (Scheel et al., 2021).

**Figura 12.4:** Tasas de resultados positivos para informes estándar y Registered Reports.

![Figura 12.4](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-4.png)

En el pasado, los Registered Reports no existían y los científicos no compartían todos los resultados (Franco et al., 2014; Greenwald, 1975; Sterling, 1959). Como consecuencia, debemos intentar detectar hasta qué punto el sesgo de publicación afecta a nuestra capacidad para evaluar correctamente la literatura.

Los metaanálisis deberían examinar cuidadosamente el impacto del sesgo de publicación sobre la estimación del tamaño del efecto metaanalítico, aunque solo un 57 % de los metaanálisis publicados en Psychological Bulletin entre 1990 y 2017 informan haber evaluado el sesgo de publicación (Polanin et al., 2020). En metaanálisis más recientes en investigación educativa, el 82 % utilizó pruebas de detección de sesgo, pero los métodos empleados estaban a menudo lejos del estado del arte (Ropovik et al., 2021).

Se han desarrollado varias técnicas para detectar el sesgo de publicación, y este sigue siendo un campo de investigación muy activo. Todas las técnicas se basan en supuestos específicos que deben considerarse antes de aplicar una prueba (Carter et al., 2019). No existe una solución milagrosa: ninguna de estas técnicas puede corregir el sesgo de publicación. Ninguna puede decir con certeza cuál es el verdadero tamaño del efecto corregido por sesgo de publicación. Lo máximo que pueden hacer es detectar el sesgo causado por mecanismos específicos bajo condiciones específicas. El sesgo de publicación puede detectarse, pero no corregirse.

En el capítulo sobre verosimilitudes vimos que es esperable encontrar resultados mixtos y que pueden constituir evidencia fuerte para la hipótesis alternativa. No solo es esperable encontrar resultados mixtos, sino que observar exclusivamente resultados estadísticamente significativos —especialmente cuando la potencia estadística es baja— resulta muy sorprendente. Con el límite inferior habitual de potencia estadística del 80 %, podemos esperar un resultado no significativo en uno de cada cinco estudios cuando existe un efecto real.

Algunos investigadores han señalado que no encontrar resultados mixtos puede ser muy improbable o “demasiado bueno para ser verdad” en un conjunto de estudios (Francis, 2014; Schimmack, 2012). No tenemos una buena intuición sobre cómo se ven realmente los patrones de resultados en los estudios, porque estamos continuamente expuestos a una literatura científica que no refleja la realidad. Casi todos los artículos con múltiples estudios en la literatura científica presentan únicamente resultados estadísticamente significativos, aunque esto sea poco probable.

La [aplicación Shiny en línea](http://shiny.ieis.tue.nl/mixed_results_likelihood/)  que utilizamos para calcular verosimilitudes binomiales muestra, si te desplazas hasta la parte inferior de la página, las probabilidades binomiales de encontrar múltiples resultados significativos dado un supuesto específico sobre la potencia de las pruebas. Francis (2014) utilizó estas verosimilitudes binomiales para calcular la prueba de significación excesiva (Ioannidis & Trikalinos, 2007) en 44 artículos publicados en la revista Psychological Science entre 2009 y 2012 que contenían cuatro estudios o más. Encontró que, para 36 de estos artículos, la probabilidad de observar cuatro resultados significativos, dada la potencia media calculada a partir de los tamaños del efecto observados, era inferior al 10 %.
12.2 Detección de sesgos en metaanálisis
Dado que eligió un nivel alfa de 0.10, esta probabilidad binomial constituye una prueba de hipótesis y permite afirmar (con un nivel alfa del 10 %) que siempre que la probabilidad binomial del número de resultados estadísticamente significativos sea inferior al 10 %, los datos resultan sorprendentes y podemos rechazar la hipótesis de que se trata de un conjunto de estudios no sesgado. En otras palabras, es poco probable observar tantos resultados significativos, lo que sugiere que el sesgo de publicación u otros efectos de selección han desempeñado un papel en estos artículos.

Uno de estos 44 artículos había sido coescrito por mí mismo (Jostmann et al., 2009). En ese momento sabía muy poco sobre potencia estadística y sesgo de publicación, y ser acusado de conducta científica inapropiada resultó estresante. Sin embargo, las acusaciones eran correctas: habíamos informado selectivamente los resultados e informado selectivamente los análisis que funcionaban. Como prácticamente no habíamos recibido formación sobre este tema, nos formamos por nuestra cuenta y subimos un estudio no publicado al sitio web psychfiledrawer.org (que ya no existe) para compartir nuestro “cajón de archivos”.

Algunos años más tarde colaboramos cuando Many Labs 3 incluyó uno de los estudios que habíamos publicado en el conjunto de estudios que estaban replicando (Ebersole et al., 2016), y cuando se observó un resultado nulo escribimos: “Hemos tenido que concluir que en realidad no existe evidencia fiable del efecto” (Jostmann et al., 2016). Espero que este material educativo evite que otros hagan el ridículo como nosotros lo hicimos.

## 12.2 Detección de sesgos en metaanálisis

Se desarrollan continuamente nuevos métodos para detectar el sesgo de publicación, y los métodos antiguos se vuelven obsoletos (aunque todavía pueden verse en algunos metaanálisis). Un método ya obsoleto se conoce como fail-safe N. La idea consistía en calcular cuántos resultados no significativos tendrían que estar ocultos en cajones antes de que la estimación del tamaño del efecto metaanalítico observado dejara de ser estadísticamente distinta de 0.

Este método ya no se recomienda. Becker (2005) escribe:

“Dado que ahora existen otros enfoques para tratar el sesgo de publicación, el fail-safe N debería abandonarse en favor de otros análisis más informativos”.

Actualmente, el único uso del fail-safe N es como indicador de metaanálisis que **no** están al día metodológicamente.

Antes de explicar un segundo método (trim-and-fill), conviene explicar una forma común de visualizar metaanálisis conocida como funnel plot (gráfico en embudo). En un funnel plot, el eje x representa el tamaño del efecto de cada estudio y el eje y representa la precisión de cada estimación del tamaño del efecto (normalmente el error estándar). Cuanto mayor es el número de observaciones en un estudio, más precisa es la estimación del tamaño del efecto, menor es el error estándar y, por tanto, más arriba aparece el estudio en el gráfico. Un estudio infinitamente preciso (con error estándar igual a 0) estaría en la parte superior del eje y.

El siguiente script simula metaanálisis para nsims estudios y guarda todos los resultados necesarios para examinar la detección de sesgos. En la primera sección del script se simulan resultados estadísticamente significativos en la dirección esperada y, en la segunda parte, se generan resultados nulos. El script genera un porcentaje de resultados significativos indicado por pub.bias: cuando se establece en 1, todos los resultados son significativos. En el código siguiente, pub.biasse establece en 0.05.

    library(metafor)
    library(truncnorm)
    nsims <- 100 # number of simulated experiments
    pub.bias <- 0.05 # set percentage of significant results in the literature
    m1 <- 0 # too large effects will make non-significant results extremely rare
    sd1 <- 1
    m2 <- 0
    sd2 <- 1
    metadata.sig <- data.frame(m1 = NA, m2 = NA, sd1 = NA, sd2 = NA, 
                               n1 = NA, n2 = NA, pvalues = NA, pcurve = NA)
    metadata.nonsig <- data.frame(m1 = NA, m2 = NA, sd1 = NA, sd2 = NA, 
                              n1 = NA, n2 = NA, pvalues = NA, pcurve = NA)
    # simulate significant effects in the expected direction
    if(pub.bias > 0){
    for (i in 1:nsims*pub.bias) { # for each simulated experiment
      p <- 1 # reset p to 1
      n <- round(truncnorm::rtruncnorm(1, 20, 1000, 100, 100)) # n based on truncated normal
      while (p > 0.025) { # continue simulating as along as p is not significant
        x <- rnorm(n = n, mean = m1, sd = sd1) 
        y <- rnorm(n = n, mean = m2, sd = sd2) 
        p <- t.test(x, y, alternative = "greater", var.equal = TRUE)$p.value
      }

      metadata.sig[i, 1] <- mean(x)
      metadata.sig[i, 2] <- mean(y)
      metadata.sig[i, 3] <- sd(x)
      metadata.sig[i, 4] <- sd(y)
      metadata.sig[i, 5] <- n
      metadata.sig[i, 6] <- n
      out <- t.test(x, y, var.equal = TRUE)
      metadata.sig[i, 7] <- out$p.value
      metadata.sig[i, 8] <- paste0("t(", out$parameter, ")=", out$statistic)
    }}

    # simulate non-significant effects (two-sided)
    if(pub.bias < 1){
    for (i in 1:nsims*(1-pub.bias)) { # for each simulated experiment
      p <- 0 # reset p to 1
      n <- round(truncnorm::rtruncnorm(1, 20, 1000, 100, 100))
      while (p < 0.05) { # continue simulating as along as p is significant
        x <- rnorm(n = n, mean = m1, sd = sd1) # produce simulated participants
        y <- rnorm(n = n, mean = m2, sd = sd2) # produce simulated participants
        p <- t.test(x, y, var.equal = TRUE)$p.value
      }
      metadata.nonsig[i, 1] <- mean(x)
      metadata.nonsig[i, 2] <- mean(y)
      metadata.nonsig[i, 3] <- sd(x)
      metadata.nonsig[i, 4] <- sd(y)
      metadata.nonsig[i, 5] <- n
      metadata.nonsig[i, 6] <- n
      out <- t.test(x, y, var.equal = TRUE)
      metadata.nonsig[i, 7] <- out$p.value
      metadata.nonsig[i, 8] <- paste0("t(", out$parameter, ")=", out$statistic)
    }}

    # Combine significant and non-significant effects
    metadata <- rbind(metadata.nonsig, metadata.sig)
    # Use escalc to compute effect sizes
    metadata <- escalc(n1i = n1, n2i = n2, m1i = m1, m2i = m2, sd1i = sd1, 
      sd2i = sd2, measure = "SMD", data = metadata[complete.cases(metadata),])
    # add se for PET-PEESE analysis
    metadata$sei <- sqrt(metadata$vi)
    #Perform meta-analysis
    result <- metafor::rma(yi, vi, data = metadata)
    result
    # Print a Funnel Plot
    metafor::funnel(result, level = 0.95, refline = 0)
    abline(v = result$b[1], lty = "dashed") # vertical line at meta-analytic ES
    points(x = result$b[1], y = 0, cex = 1.5, pch = 17) # add point

Como en la simulación no existe un efecto real (m1 y m2 son iguales, por lo que no hay diferencia entre los grupos), los únicos resultados significativos que deberían observarse son el 5 % de falsos positivos. Finalmente, se realiza el metaanálisis, se imprimen los resultados y se crea un funnel plot.

Comencemos observando cómo se ve una investigación no sesgada, ejecutando el código con pub.bias = 0.05, de modo que solo el 5 % de errores de Tipo I entren en la literatura científica.

    Random-Effects Model (k = 100; tau^2 estimator: REML) tau^2 (estimated amount of total heterogeneity): 0.0000 (SE = 0.0018) tau (square root of estimated tau^2 value): 0.0006 I^2 (total heterogeneity / total variability): 0.00% H^2 (total variability / sampling variability): 1.00 Test for Heterogeneity: Q(df = 99) = 91.7310, p-val = 0.6851 Model Results: estimate se zval pval ci.lb ci.ub -0.0021 0.0121 -0.1775 0.8591 -0.0258 0.0215 --- Signif. codes: 0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Cuando examinamos los resultados del metaanálisis vemos que hay 100 estudios en el metaanálisis (k = 100) y que no hay heterogeneidad estadísticamente significativa (p = 0.69). Esto no resulta sorprendente, ya que programamos la simulación con un tamaño del efecto verdadero igual a 0 y sin heterogeneidad entre tamaños del efecto.

La estimación metaanalítica es d = −0.002, muy cercana a 0 (como debería ser, dado que el efecto verdadero es 0). El error estándar de esta estimación es 0.012. Con 100 estudios tenemos una estimación muy precisa del tamaño del efecto verdadero. El valor Z para la prueba frente a d = 0 es −0.177 y el valor p es 0.86, por lo que no podemos rechazar la hipótesis de que el tamaño del efecto verdadero sea 0. El intervalo de confianza alrededor de la estimación (−0.026, 0.021) incluye 0.

Si examinamos el funnel plot (Figura 12.5) vemos cada estudio representado como un punto. Cuanto mayor es el tamaño muestral, más arriba aparece el punto; cuanto menor es el tamaño muestral, más abajo aparece. La pirámide blanca representa el área dentro de la cual un estudio no es estadísticamente significativo, porque el tamaño del efecto observado (eje x) no está lo suficientemente alejado de 0 como para que el intervalo de confianza excluya 0.

Cuanto menor es el error estándar, más estrecho es el intervalo de confianza y menor debe ser el tamaño del efecto para resultar estadísticamente significativo. Al mismo tiempo, cuanto menor es el error estándar, más cerca estará el tamaño del efecto del verdadero valor poblacional, por lo que es menos probable observar efectos muy alejados de 0.

Deberíamos esperar que el 95 % de las estimaciones de tamaño del efecto caigan dentro del embudo si está centrado en el tamaño del efecto verdadero. Observamos que solo unos pocos estudios (cinco, exactamente) caen fuera de la pirámide blanca en el lado derecho del gráfico. Estos son los 5 % de resultados significativos que programamos en la simulación. Obsérvese que los cinco son falsos positivos, ya que no existe un efecto real.

Si hubiera un efecto real (puedes volver a ejecutar la simulación estableciendo d = 0.5 cambiando m1 <- 0 por m1 <- 0.5), la nube de puntos se desplazaría hacia la derecha y se centraría en 0.5 en lugar de 0.

**Figura 12.5:** Funnel plot de resultados nulos no sesgados.

![Figura 12.5](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-5.png)

Ahora podemos comparar el metaanálisis no sesgado anterior con un metaanálisis sesgado. Podemos simular una situación de sesgo de publicación extremo. Basándonos en la estimación de Scheel et al. (2021), supongamos que el 96 % de los estudios muestran resultados positivos. Para ello establecemos pub.bias <- 0.96 en el código.

Mantenemos ambas medias en 0, por lo que sigue sin existir un efecto real, pero terminaremos con principalmente errores de Tipo I en la dirección predicha en el conjunto final de estudios. Tras simular resultados sesgados, podemos realizar el metaanálisis para ver si la inferencia estadística basada en él resulta engañosa.

    Random-Effects Model (k = 100; tau^2 estimator: REML) tau^2 (estimated amount of total heterogeneity): 0 (SE = 0.0019) tau (square root of estimated tau^2 value): 0 I^2 (total heterogeneity / total variability): 0.00% H^2 (total variability / sampling variability): 1.00 Test for Heterogeneity: Q(df = 99) = 77.6540, p-val = 0.9445 Model Results: estimate se zval pval ci.lb ci.ub 0.2701 0.0125 21.6075 <.0001 0.2456 0.2946 *** --- Signif. codes: 0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

La naturaleza sesgada del conjunto de estudios se vuelve evidente al examinar el funnel plot. El patrón es bastante peculiar. Observamos cuatro resultados nulos no sesgados (tal como programamos en la simulación), pero los 96 estudios restantes son estadísticamente significativos, aunque la hipótesis nula sea verdadera.

La mayoría de los estudios se sitúan justo en el borde de la pirámide blanca. Como los valores p se distribuyen uniformemente bajo la hipótesis nula, los errores de Tipo I que observamos suelen tener valores p entre 0.02 y 0.05, a diferencia de lo que esperaríamos si existiera un efecto real.

Cuanto mayor es el estudio, menor es el tamaño del efecto necesario para resultar significativo. El hecho de que los tamaños del efecto no varíen alrededor de un único valor verdadero, sino que disminuyan a medida que aumenta el tamaño muestral, es un fuerte indicador de sesgo.

La línea vertical discontinua y el triángulo negro en la parte superior del gráfico ilustran la estimación metaanalítica observada (sesgada al alza).

**Figura 12.6:** Funnel plot de resultados nulos sesgados con mayoría de resultados significativos.

![Figura 12.6](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-6.png)

Podría pensarse que un sesgo tan extremo rara vez aparece en la investigación científica. Sin embargo, sí ocurre. En la Figura 12.7 se muestra un funnel plot de Carter y McCullough (2014), quienes examinaron el sesgo en 198 estudios publicados sobre el efecto de agotamiento del ego (ego-depletion), la idea de que el autocontrol depende de un recurso limitado.

Utilizando técnicas de detección de sesgo como la meta-regresión PET-PEESE, concluyeron que el tamaño del efecto no sesgado estimado por PET era d = −0.1, estadísticamente indistinguible de 0, lo que sugiere que el verdadero efecto podría ser d = 0, aunque el tamaño del efecto metaanalítico sin corrección por sesgo era d = 0.62.

No resulta sorprendente que, aunque antes de 2015 los investigadores pensaban que existía una literatura sólida que demostraba el efecto de ego-depletion, un **Registered Replication Report** encontró un efecto no significativo (Hagger et al., 2016), y posteriormente los propios autores originales tampoco lograron replicar el efecto (Vohs et al., 2021).

Imagina la enorme cantidad de tiempo, esfuerzo y dinero desperdiciados en una literatura basada en sesgos de investigación. Este desperdicio tiene implicaciones éticas evidentes, y los investigadores deben asumir la responsabilidad de prevenirlo en el futuro.

**Figura 12.7:** Funnel plot de Carter y McCullough (2014) que visualiza el sesgo en 198 estudios sobre ego-depletion, incluyendo estimaciones PET-PEESE corregidas por sesgo.

![Figura 12.7](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-7.png)

También podemos observar señales de sesgo en un forest plot de un metaanálisis. En la Figura 12.8 se muestran dos forest plots. El de la izquierda se basa en datos no sesgados y el de la derecha en datos sesgados.

En el forest plot de la izquierda los efectos varían aleatoriamente alrededor de 0, como cabría esperar. En el de la derecha, a partir del cuarto estudio, todos los intervalos de confianza excluyen milagrosamente el valor 0.

**Figura 12.8:** Forest plot de un metaanálisis no sesgado (izquierda) y sesgado (derecha).

![Figura 12.8](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-8.png)

Cuando existe sesgo de publicación porque los investigadores solo publican resultados estadísticamente significativos, la estimación metaanalítica del tamaño del efecto será mayor que en ausencia de sesgo. Esto ocurre porque el sesgo de publicación elimina los tamaños del efecto pequeños (no significativos), que por tanto no se incluyen en el cálculo del tamaño del efecto metaanalítico.

Esto conduce a una estimación metaanalítica inflada respecto al verdadero tamaño del efecto poblacional. Con un sesgo de publicación fuerte sabemos que la estimación está inflada, pero no sabemos cuánto. El efecto real podría ser solo un poco menor, o incluso ser cero, como en el caso de la literatura sobre ego-depletion.

# 12.3 Trim and Fill

El trim and fill es una técnica que pretende ampliar un conjunto de datos añadiendo estudios hipotéticos “faltantes” (que podrían estar en el “cajón de archivo”). El procedimiento comienza eliminando (“trimming”) los estudios pequeños que sesgan el tamaño del efecto metaanalítico, luego estima el verdadero tamaño del efecto y termina “rellenando” un funnel plot con estudios que se supone que faltan debido al sesgo de publicación. En la Figura 12.9 puedes ver el mismo funnel plot de antes, pero ahora con estudios hipotéticos añadidos (los círculos sin rellenar, que representan estudios “imputados”). Si te fijas bien, verás que cada uno de estos puntos tiene una imagen especular en el lado opuesto de la estimación del tamaño del efecto metaanalítico (esto se aprecia con mayor claridad en la mitad inferior del funnel plot). Si examinamos el resultado del metaanálisis que incluye estos estudios imputados, vemos que trim and fill logra advertirnos de que el metaanálisis está sesgado (si no, no añadiría estudios imputados), pero fracasa estrepitosamente al corregir la estimación del tamaño del efecto. En el funnel plot vemos la estimación original (sesgada) del tamaño del efecto indicada por el triángulo, y la estimación del tamaño del efecto metaanalítico ajustada con el método trim-and-fill (indicada por el círculo negro). Vemos que la estimación metaanalítica del tamaño del efecto es algo menor, pero dado que el verdadero tamaño del efecto en la simulación era 0, el ajuste es claramente insuficiente.

**Figura 12.9:** Funnel plot con efectos supuestamente faltantes añadidos mediante trim-and-fill.

![Figura 12.9](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-9.png)

El método trim-and-fill no funciona muy bien en muchos escenarios realistas de sesgo de publicación. El método ha sido criticado por depender del fuerte supuesto de simetría en el funnel plot. Cuando el sesgo de publicación se basa en el valor p del estudio (posiblemente la fuente más importante de sesgo de publicación en muchos campos), el método trim-and-fill no funciona lo bastante bien como para producir una estimación corregida del tamaño del efecto metaanalítico cercana al verdadero tamaño del efecto (Peters et al., 2007; Terrin et al., 2003). Cuando se cumplen sus supuestos, puede utilizarse como análisis de sensibilidad. Los investigadores no deberían informar de la estimación del tamaño del efecto corregida por trim-and-fill como si fuera una estimación realista del tamaño del efecto no sesgado. Si otras pruebas de detección de sesgo (como p-curve o z-curve, tratadas más abajo) ya han indicado la presencia de sesgo, el procedimiento trim-and-fill puede no aportar información adicional.

## 12.4 PET-PEESE

Una clase novedosa de soluciones al sesgo de publicación es la meta-regresión. En lugar de trazar una línea a través de puntos de datos individuales, en la meta-regresión se traza una línea a través de puntos de datos que representan cada uno un estudio. Igual que en la regresión ordinaria, cuantos más datos haya en la meta-regresión, más precisa será la estimación y, por tanto, cuantos más estudios haya en un metaanálisis, mejor funcionará en la práctica la meta-regresión. Si el número de estudios es pequeño, todas las pruebas de detección de sesgo pierden potencia, y esto es algo que debe tenerse en cuenta al utilizar meta-regresión. Además, la regresión requiere suficiente variación en los datos, lo que en el caso de la meta-regresión significa un amplio rango de tamaños muestrales (las recomendaciones indican que la meta-regresión funciona bien si los estudios tienen entre 15 y 200 participantes por grupo, algo que no es típico de la mayoría de las áreas de investigación en psicología). Las técnicas de meta-regresión intentan estimar el tamaño del efecto poblacional si la precisión fuera perfecta (es decir, cuando el error estándar = 0).

Una técnica de meta-regresión se conoce como PET-PEESE (Stanley et al., 2017; Stanley & Doucouliagos, 2014). Consiste en una prueba del efecto-precisión (precision-effect-test, PET), que puede utilizarse dentro del marco de contraste de hipótesis de Neyman-Pearson para probar si la estimación de meta-regresión permite rechazar un tamaño del efecto de 0 basándose en el IC del 95 % alrededor de la estimación PET en la intersección cuando SE = 0. Obsérvese que, cuando el intervalo de confianza es muy amplio debido a un pequeño número de observaciones, esta prueba puede tener poca potencia y una baja probabilidad a priori de rechazar el efecto nulo. El tamaño del efecto estimado para PET se calcula con: donde d es el tamaño del efecto estimado, SE es el error estándar, y la ecuación se estima usando mínimos cuadrados ponderados (WLS), con 1/SE²ᵢ como pesos. La estimación PET subestima el tamaño del efecto cuando existe un efecto real. Por ello, el procedimiento PET-PEESE recomienda primero utilizar PET para probar si puede rechazarse la hipótesis nula y, si es así, entonces utilizar la estimación del efecto-precisión con error estándar (precision-effect estimate with standard error, PEESE) para estimar el tamaño del efecto metaanalítico. En PEESE, el error estándar (utilizado en PET) se sustituye por la varianza (es decir, el cuadrado del error estándar), lo que, según Stanley y Doucouliagos (2014), reduce el sesgo de la intersección estimada en la meta-regresión.

PET-PEESE tiene limitaciones, como todas las técnicas de detección de sesgo. Las limitaciones más importantes son que no funciona bien cuando hay pocos estudios, cuando todos los estudios de un metaanálisis tienen tamaños muestrales pequeños o cuando existe una gran heterogeneidad en el metaanálisis (Stanley et al., 2017). Cuando estas situaciones se dan (y en la práctica se darán), PET-PEESE puede no ser un buen enfoque. Además, hay algunas situaciones en las que puede existir una correlación entre tamaño muestral y precisión, lo que en la práctica a menudo estará relacionado con la heterogeneidad de los tamaños del efecto incluidos en un metaanálisis. Por ejemplo, si los efectos verdaderos difieren entre estudios y las personas realizan análisis de potencia con información precisa sobre el verdadero tamaño del efecto esperado, los tamaños del efecto grandes en un metaanálisis tendrán tamaños muestrales pequeños y los efectos pequeños tendrán tamaños muestrales grandes. La meta-regresión es, igual que la regresión ordinaria, una manera de probar una asociación, pero es necesario pensar en el mecanismo causal que hay detrás de esa asociación.

Exploremos cómo la meta-regresión PET-PEESE intenta ofrecernos una estimación no sesgada del tamaño del efecto, bajo supuestos específicos sobre cómo se produce el sesgo de publicación. Volvemos a ver una vez más el funnel plot, ahora complementado con dos líneas adicionales. La línea vertical en d = 0.27 es la estimación metaanalítica del tamaño del efecto, que está sesgada al alza porque estamos promediando únicamente estudios estadísticamente significativos. Hay dos líneas adicionales, que son las líneas de meta-regresión para PET-PEESE basadas en las fórmulas detalladas antes. La línea diagonal continua nos proporciona la estimación PET cuando SE = 0 (una muestra infinita, en la parte superior del gráfico), indicada por el círculo. La línea discontinua alrededor de esta estimación PET es el intervalo de confianza del 95 % de la estimación. 

En este caso, el IC del 95 % contiene 0, lo que significa que, basándonos en la estimación PET de d = 0.02, no podemos rechazar un tamaño del efecto metaanalítico de 0. Obsérvese que incluso con 100 estudios el IC del 95 % es bastante amplio. La meta-regresión, igual que la regresión ordinaria, es tan precisa como lo sean los datos de los que disponemos. Esta es una limitación de la meta-regresión PET-PEESE: con un número pequeño de estudios en el metaanálisis, su precisión es baja. Si hubiéramos podido rechazar la hipótesis nula basándonos en la estimación PET, entonces habríamos utilizado la estimación PEESE (indicada por la forma de rombo) de d = 0.17 como el tamaño del efecto metaanalítico corregido por sesgo (sin llegar nunca a saber si el modelo subyacente a la estimación PEESE se correspondía con los verdaderos mecanismos generadores de sesgo en el metaanálisis y, por tanto, si la estimación metaanalítica era precisa).

**Figura 12.10:** Funnel plot con líneas de regresión PETPEESE.

![Figura 12.10](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-10.png)

## 12.5 Metaanálisis de valores p

Además de un metaanálisis de tamaños del efecto, es posible realizar un metaanálisis de valores p. El primero de estos enfoques se conoce como la prueba combinada de probabilidad de Fisher, y pruebas más recientes de detección de sesgo, como el análisis p-curve (Simonsohn et al., 2014) y p-uniform* (Aert & Assen, 2018), se basan en esta idea. Estas dos técnicas son un ejemplo de enfoques de modelos de selección para probar y ajustar metaanálisis (Iyengar & Greenhouse, 1988), en los que un modelo sobre el proceso generador de los tamaños del efecto se combina con un modelo de selección sobre cómo el sesgo de publicación afecta a qué tamaños del efecto pasan a formar parte de la literatura científica. Un ejemplo de proceso generador de datos sería que los resultados de los estudios son producidos por pruebas estadísticas cuyos supuestos se cumplen todos, y que los estudios tienen una cierta potencia media. Un modelo de selección podría ser que todos los estudios se publiquen siempre que sean estadísticamente significativos con un nivel alfa de 0.05.

El análisis p-curve utiliza exactamente este modelo de selección. Asume que todos los resultados significativos se publican y examina si el proceso generador de los datos refleja lo que cabría esperar si los estudios tuvieran una cierta potencia, o si refleja el patrón esperado cuando la hipótesis nula es verdadera. Como se discutió en la sección sobre qué valores p cabe esperar, para estadísticos de contraste con distribución continua (por ejemplo, valores t, valores F o puntuaciones Z) deberíamos observar valores p distribuidos uniformemente cuando la hipótesis nula es verdadera, y más valores p significativos pequeños (por ejemplo, 0.01) que valores p significativos grandes (por ejemplo, 0.04) cuando la hipótesis alternativa es verdadera.

El análisis p-curve realiza dos pruebas. En la primera, examina si la distribución de valores p es más plana de lo que cabría esperar si los estudios que analizas tuvieran una potencia del 33 %. Este valor es algo arbitrario (y puede ajustarse), pero la idea es rechazar en el nivel más bajo de potencia estadística que todavía permitiría extraer conclusiones útiles sobre la presencia de efectos. Si la potencia media en el conjunto de estudios es inferior al 33 %, podría existir un efecto, pero los estudios no están diseñados lo bastante bien como para aprender algo sobre él mediante contrastes estadísticos. Si podemos rechazar la presencia de un patrón de valores p que tenga al menos un 33 % de potencia, esto sugiere que la distribución se parece más a la esperada cuando la hipótesis nula es verdadera. Es decir, dudaríamos de que exista un efecto en el conjunto de estudios incluidos en el metaanálisis, aunque todos los estudios individuales fueran estadísticamente significativos.

La segunda prueba examina si la distribución de valores p está suficientemente sesgada a la derecha (más valores p significativos pequeños que grandes), de tal manera que el patrón permita rechazar una distribución uniforme de valores p. Si podemos rechazar una distribución uniforme de valores p, esto sugiere que los estudios podrían haber examinado un efecto real y haber tenido al menos cierta potencia. Si la segunda prueba es significativa, actuaríamos como si el conjunto de estudios examinara algún efecto real, aunque pudiera existir sesgo de publicación. Como ejemplo, consideremos la Figura 3 de Simonsohn y colegas (2014). Los autores compararon 20 artículos del Journal of Personality and Social Psychology que utilizaban una covariable en el análisis y 20 estudios que no utilizaban covariable. Los autores sospechaban que los investigadores podían añadir una covariable en sus análisis para intentar obtener un valor p inferior a 0.05 cuando el primer análisis que probaron no había producido un efecto significativo.

**Figura 12.11:** Figura 3 de Simonsohn et al. (2014), que muestra una p-curve con y sin sesgo.

![Figura 12.11](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-11.png)

La distribución p-curve de los valores p observados está representada por cinco puntos en la línea azul. El análisis p-curve se realiza solo sobre resultados estadísticamente significativos, basándose en el supuesto de que estos siempre se publican y, por tanto, que esta parte de la distribución de valores p contiene todos los estudios que se realizaron. Los cinco puntos ilustran el porcentaje de valores p entre 0 y 0.01, entre 0.01 y 0.02, entre 0.02 y 0.03, entre 0.03 y 0.04, y entre 0.04 y 0.05. En la figura de la derecha se observa una distribución de valores p razonablemente normal y sesgada a la derecha, con más valores p bajos que altos. El análisis p-curve muestra que la línea azul en la figura de la derecha está más sesgada a la derecha que la línea roja uniforme (donde la línea roja representa la distribución uniforme de valores p esperada si no hubiera efecto). Simonsohn y colegas resumen este patrón como una indicación de que el conjunto de estudios tiene “valor evidencial”, pero esta terminología es algo engañosa. La interpretación formalmente correcta es que podemos rechazar una distribución de valores p como la esperada cuando la hipótesis nula fuera verdadera en todos los estudios incluidos en el análisis p-curve. Rechazar una distribución uniforme de valores p no significa automáticamente que haya evidencia a favor del efecto teorizado (por ejemplo, el patrón podría estar causado por una mezcla de efectos nulos y un pequeño subconjunto de estudios que muestran un efecto debido a una variable de confusión metodológica).

En la figura de la izquierda vemos el patrón opuesto, con principalmente valores p altos, alrededor de 0.05, y casi ningún valor p alrededor de 0.01. Como la línea azul es significativamente más plana que la línea verde, el análisis p-curve sugiere que este conjunto de estudios es el resultado de un sesgo de selección y no fue generado por un conjunto de estudios con potencia suficiente. El análisis p-curve es una herramienta útil. Pero es importante interpretar correctamente lo que un análisis p-curve puede decirte. Una p-curve sesgada a la derecha no demuestra que no exista sesgo ni que la hipótesis teórica sea verdadera. Una p-curve plana no demuestra que la teoría sea incorrecta, pero sí muestra que los estudios metaanalizados se parecen más al patrón que cabría esperar si la hipótesis nula fuera verdadera y existiera sesgo de selección.

El script guarda todos los estadísticos de contraste de los 100 tests t simulados que se incluyen en el metaanálisis. Las primeras filas tienen este aspecto:

    t(136)=0.208132209831132
    t(456)=-1.20115958535433
    t(58)=0.0422284763301259
    t(358)=0.0775200850900646
    t(188)=2.43353676652346

Imprime todos los resultados de las pruebas con cat(metadata$pcurve, sep = "\n"), y ve a la aplicación p-curve en línea en http://www.p-curve.com/app4/. Pega todos los resultados de las pruebas y haz clic en el botón “Make the p-curve”. Obsérvese que la aplicación p-curve solo producirá un resultado cuando existan valores p menores que 0.05; si todos los estadísticos de contraste producen un p > 0.05, no se puede calcular la p-curve, ya que esas pruebas se ignoran.

**Figura 12.12:** Resultado del análisis p-curve de los estudios sesgados.

![Figura 12.12](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-12.png)

La distribución de valores p parece claramente provenir de una distribución uniforme (como de hecho ocurre), y la prueba estadística indica que podemos rechazar una distribución de valores p tan pronunciada o más pronunciada como la que sería generada por un conjunto de estudios con un 33 % de potencia, p < 0.0001. La aplicación también proporciona una estimación de la potencia media de las pruebas que generaron la distribución de valores p observada: 5 %, que en efecto es correcta. Por tanto, podemos concluir que estos estudios, aunque muchos efectos sean estadísticamente significativos, son más compatibles con un informe selectivo de errores de Tipo I que con una distribución de valores p que cabría esperar si existiera un efecto real estudiado con potencia estadística suficiente. La teoría aún podría ser verdadera, pero el conjunto de estudios que hemos analizado aquí no proporciona apoyo para esa teoría.

Una técnica metaanalítica similar es p-uniform*. Esta técnica es parecida al análisis p-curve y a los modelos de sesgo de selección, pero utiliza tanto los resultados significativos como los no significativos, y puede emplearse para estimar un tamaño del efecto metaanalítico ajustado por sesgo. La técnica utiliza un modelo de efectos aleatorios para estimar los tamaños del efecto de cada estudio y los pondera a partir de un modelo de selección que asume que los resultados significativos tienen más probabilidad de publicarse que los no significativos. A continuación vemos la salida de p-uniform*, que estima el tamaño del efecto corregido por sesgo en d = 0.0126. Este tamaño del efecto no es estadísticamente distinto de 0, p = 0.3857, y por tanto esta técnica de detección de sesgo indica correctamente que, aunque todos los efectos fueran estadísticamente significativos, el conjunto de estudios no proporciona una buena razón para rechazar una estimación metaanalítica del tamaño del efecto igual a 0.

     puniform::puniform(m1i = metadata$m1, m2i = metadata$m2, n1i = metadata$n1, 
     n2i = metadata$n2, sd1i = metadata$sd1, sd2i = metadata$sd2, side = "right")

Method: P Effect size estimation p-uniform est ci.lb ci.ub L.0 pval ksig 0.0126 -0.0811 0.0887 -0.2904 0.3857 96 === Publication bias test p-uniform L.pb pval 7.9976 <.001 === Fixed-effect meta-analysis est.fe se.fe zval.fe pval.fe ci.lb.fe ci.ub.fe Qstat Qpval 0.2701 0.0125 21.6025 <.001 0.2456 0.2946 77.6031 0.945

Una técnica alternativa que también realiza un metaanálisis de los valores p de estudios individuales es el análisis z-curve, que es un metaanálisis de la potencia observada (Bartoš & Schimmack, 2020; Brunner & Schimmack, 2020; para un ejemplo, véase Sotola, 2022). Igual que en un metaanálisis tradicional, el análisis z-curve transforma los resultados observados de las pruebas (valores p) en puntuaciones z. En una literatura no sesgada en la que la hipótesis nula es verdadera, deberíamos observar aproximadamente un 5 % de resultados significativos. Si la hipótesis nula es verdadera, la distribución de las puntuaciones z está centrada en 0. El análisis z-curve calcula valores z absolutos y, por tanto, un 5 % de las puntuaciones z debería ser mayor que el valor crítico (1.96 para un nivel alfa del 5 %). En la Figura 12.13 se representan puntuaciones z para 1000 estudios, con un tamaño del efecto verdadero de 0, donde exactamente el 5 % de los resultados observados son estadísticamente significativos.

**Figura 12.13:** Análisis z-curve para 1000 estudios con un verdadero tamaño del efecto de 0 sin sesgo de publicación.

![Figura 12.13](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-13.png)

Si existe un efecto real, la distribución de las puntuaciones z se desplaza alejándose de 0 en función de la potencia estadística de la prueba. Cuanto mayor es la potencia, más a la derecha se situará la distribución de puntuaciones z. Por ejemplo, al examinar un efecto con una potencia del 66 %, una distribución no sesgada de puntuaciones z, calculada a partir de valores p observados, tiene el aspecto mostrado en la Figura 12.14.

**Figura 12.14:** Análisis z-curve para 1000 estudios con un verdadero tamaño del efecto de d = 0.37 y n = 100 por condición en una prueba t para muestras independientes sin sesgo de publicación.

![Figura 12.14](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-14.png)

En cualquier metaanálisis, los estudios incluidos diferirán en su potencia estadística y en su verdadero tamaño del efecto (debido a la heterogeneidad). El análisis z-curve utiliza mezclas de distribuciones normales centradas en medias de 0 a 6 para ajustar un modelo de los tamaños del efecto subyacentes que represente lo mejor posible los resultados observados en los estudios incluidos (para los detalles técnicos, véase Bartoš & Schimmack, 2020). A continuación, la z-curve pretende estimar la potencia media del conjunto de estudios y calcula después la observed discovery rate (ODR: el porcentaje de resultados significativos, o la potencia observada), la expected discovery rate (EDR: la proporción del área bajo la curva a la derecha del criterio de significación) y la expected replication rate (ERR: la proporción esperada de estudios significativos replicados con éxito entre todos los estudios significativos). La z-curve es capaz de corregir el sesgo de selección para resultados positivos (bajo supuestos específicos) y puede estimar la EDR y la ERR usando solo los valores p significativos.

Para examinar la presencia de sesgo, es preferible introducir en un análisis z-curve tanto valores p no significativos como significativos, aunque solo los significativos se utilicen para producir las estimaciones. El sesgo de publicación puede examinarse comparando la ODR con la EDR. Si el porcentaje de resultados significativos en el conjunto de estudios (ODR) es mucho mayor que la tasa esperada de descubrimiento (EDR), esto es una señal de sesgo. Si analizamos el mismo conjunto de estudios sesgados que utilizamos para ilustrar las técnicas de detección de sesgo comentadas antes, el análisis z-curve debería ser capaz de indicar la presencia de sesgo. Podemos realizar la z-curve con el siguiente código:

    z_res <- zcurve::zcurve(p = metadata$pvalues, method = "EM", bootstrap = 1000)
    summary(z_res, all = TRUE)
    plot(z_res, annotation = TRUE, CI = TRUE)

![](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/image1.png)

Call: zcurve::zcurve(p = metadata$pvalues, method = "EM", bootstrap = 1000) model: EM via EM Estimate l.CI u.CI ERR 0.052 0.025 0.160 EDR 0.053 0.050 0.119 Soric FDR 0.947 0.389 1.000 File Drawer R 17.987 7.399 19.000 Expected N 1823 806 1920 Missing N 1723 706 1820 Model converged in 38 + 205 iterations Fitted using 96 p-values. 100 supplied, 96 significant (ODR = 0.96, 95% CI [0.89, 0.99]). Q = -6.69, 95% CI[-23.63, 11.25]

Vemos que la distribución de puntuaciones z tiene un aspecto peculiar. Faltan la mayoría de las puntuaciones z esperadas entre 0 y 1.96. 96 de 100 estudios fueron significativos, lo que hace que la observed discovery rate (ODR), o potencia observada (a través de todos estos estudios con distintos tamaños muestrales), sea 0.96, IC del 95 % [0.89; 0.99]. La expected discovery rate (EDR) es solo 0.053, y difiere estadísticamente de la ODR observada, como indica el hecho de que el intervalo de confianza de la EDR no se superpone con la ODR de 0.96. Esto significa que hay una indicación clara de sesgo de selección basada en el análisis z-curve. La expected replicability rate (ERR) para estos estudios es solo 0.052, lo que concuerda con la expectativa de que solo observaremos un 5 % de errores de Tipo I, dado que en esta simulación no existía un efecto real. Así, aunque solo introdujimos valores p significativos, el análisis z-curve sugiere correctamente que no deberíamos esperar que estos resultados se repliquen con una frecuencia mayor que la tasa de error de Tipo I.

## 12.6 Conclusión

El sesgo de publicación es un gran problema en la ciencia. Está presente en casi todos los metaanálisis realizados sobre la prueba principal de hipótesis de los artículos científicos, porque es mucho más probable que estos artículos se envíen y acepten para publicación si la prueba principal de hipótesis es estadísticamente significativa. Las estimaciones del tamaño del efecto metaanalítico que no están ajustadas por sesgo casi siempre sobreestimarán el verdadero tamaño del efecto, y las estimaciones ajustadas por sesgo todavía pueden resultar engañosas. Una vez que la literatura científica ha quedado distorsionada por el sesgo de publicación, no hay manera de saber si estamos calculando a partir de ella estimaciones metaanalíticas precisas del tamaño del efecto. El sesgo de publicación infla la estimación del tamaño del efecto en una magnitud desconocida, y ya ha habido varios casos en los que el verdadero tamaño del efecto resultó ser cero. Las pruebas de sesgo de publicación tratadas en este capítulo quizá no proporcionen certeza sobre el tamaño del efecto no sesgado, pero sí pueden funcionar como una señal de alerta para indicar cuándo hay sesgo, y ofrecer estimaciones ajustadas que, si el modelo subyacente del sesgo de publicación es correcto, bien podrían estar más cerca de la verdad.

Existe mucha actividad en la literatura sobre pruebas de sesgo de publicación. Hay muchas pruebas distintas, y debes comprobar cuidadosamente los supuestos de cada una antes de aplicarla. La mayoría de las pruebas no funcionan bien cuando hay una gran heterogeneidad, y la heterogeneidad es bastante probable. Un metaanálisis debería examinar siempre si existe sesgo de publicación, preferiblemente utilizando múltiples pruebas de sesgo de publicación, y por tanto resulta útil no solo codificar tamaños del efecto, sino también estadísticos de contraste o valores p. Ninguna de las técnicas de detección de sesgo tratadas en este capítulo será una solución milagrosa, pero serán mejores que interpretar ingenuamente la estimación del tamaño del efecto no corregida del metaanálisis.

Para otro recurso educativo abierto sobre pruebas de sesgo de publicación, véase Doing Meta-Analysis in R.

## 12.7 Ponte a prueba

### P1: ¿Qué ocurre cuando existe sesgo de publicación porque los investigadores publican solo resultados estadísticamente significativos (p < ), y calculas el tamaño del efecto en un metaanálisis?
- La estimación metaanalítica del tamaño del efecto es idéntica tanto si hay sesgo de publicación (donde los investigadores publican solo efectos con p < ) como si no lo hay.
- La estimación metaanalítica del tamaño del efecto está más cerca del verdadero tamaño del efecto cuando hay sesgo de publicación (donde los investigadores publican solo efectos con p < ) que cuando no lo hay.
- La estimación metaanalítica del tamaño del efecto está inflada cuando hay sesgo de publicación (donde los investigadores publican solo efectos con p < ) en comparación con cuando no lo hay.
- La estimación metaanalítica del tamaño del efecto es menor cuando hay sesgo de publicación (donde los investigadores publican solo efectos con p < ) en comparación con cuando no lo hay.

### P2: El forest plot de la figura de abajo parece bastante peculiar. ¿Qué observas?

![](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/image2.png)

- Todos los tamaños del efecto son bastante parecidos, lo que sugiere tamaños muestrales grandes y medidas del tamaño del efecto muy precisas.
- Los estudios parecen haber sido diseñados a partir de análisis de potencia a priori perfectos, produciendo todos ellos resultados justo significativos.
- Los estudios tienen intervalos de confianza que casi justo no incluyen 0, lo que sugiere que la mayoría de los estudios son solo justo estadísticamente significativos. Esto sugiere sesgo de publicación.
- Todos los efectos van en la misma dirección, lo que sugiere que se han realizado pruebas unilaterales, aunque estas podrían no haber sido preregistradas.

### P3: ¿Qué afirmación es verdadera?

- Con un sesgo de publicación extremo, todos los estudios individuales de una literatura pueden ser significativos, pero los errores estándar son tan grandes que la estimación metaanalítica del tamaño del efecto no es significativamente distinta de 0.
- Con un sesgo de publicación extremo, todos los estudios individuales de una literatura pueden ser significativos, pero la estimación metaanalítica del tamaño del efecto estará gravemente inflada, dando la impresión de que existe un apoyo abrumador a , cuando en realidad el verdadero tamaño del efecto es pequeño o incluso 0.
- Con un sesgo de publicación extremo, todos los estudios individuales son significativos, pero las estimaciones metaanalíticas del tamaño del efecto se corrigen automáticamente por sesgo de publicación en la mayoría de los paquetes estadísticos y, por tanto, la estimación metaanalítica del tamaño del efecto es bastante fiable.
- Independientemente de que exista o no sesgo de publicación, la estimación metaanalítica del tamaño del efecto está gravemente sesgada y nunca debería considerarse una estimación fiable de la población.

### P4: ¿Qué afirmación es verdadera basándose en la figura de abajo, que visualiza una meta-regresión PET-PEESE?

![Figura 12.15](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-15.png)

**Figura 12.15:** Funnel plot con líneas de regresión PETPEESE para los mismos estudios que en P2.

- Utilizando meta-regresión PET-PEESE podemos mostrar que el verdadero tamaño del efecto es d = 0 (basándonos en la estimación PET).
- Utilizando meta-regresión PET-PEESE podemos mostrar que el verdadero tamaño del efecto es d = r round(PEESE$b[1],2) (basándonos en la estimación PEESE).
- Utilizando meta-regresión PET-PEESE podemos mostrar que el verdadero tamaño del efecto es d = r round(result.biased$b, 2) (basándonos en la estimación metaanalítica normal del tamaño del efecto).
- El pequeño tamaño muestral (10 estudios) significa que PET tiene muy poca potencia para rechazar la hipótesis nula y, por tanto, no es un indicador fiable de sesgo, aunque podría haber motivos de preocupación.

### P5: Mira la figura y la tabla de resultados de la aplicación p-curve de abajo, que ofrece los resultados de los estudios de P2. ¿Qué interpretación del resultado es correcta?

![Figura 12.16](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-16.png)

**Figura 12.16:** Resultado del análisis p-curve de los estudios sesgados de P2.

- Basándonos en la prueba continua de Stouffer para la p-curve completa, no podemos rechazar una distribución de valores p esperada bajo , y podemos rechazar una distribución de valores p como la esperada si es verdadera y los estudios tuvieran un 33 % de potencia.
- Basándonos en la prueba continua de Stouffer para la p-curve completa, podemos concluir que la distribución observada de valores p no está lo bastante sesgada como para interpretarse como señal de un verdadero tamaño del efecto y, por tanto, la teoría utilizada para deducir estos estudios es incorrecta.
- Basándonos en la prueba continua de Stouffer para la p-curve completa, podemos concluir que la distribución observada de valores p está lo bastante sesgada como para interpretarse en línea con una distribución de valores p como la esperada si es verdadera y los estudios tuvieran un 33 % de potencia.
- Basándonos en la prueba continua de Stouffer para la p-curve completa, podemos concluir que la distribución observada de valores p es más plana de lo que cabría esperar si los estudios tuvieran un 33 % de potencia y, por tanto, podemos concluir que estos estudios se basan en datos fabricados.

### P6: El verdadero tamaño del efecto en los estudios simulados en P2 es 0: no existe un efecto real. ¿Qué afirmación sobre el análisis z-curve de abajo es verdadera?

![Figura 12.17](https://raw.githubusercontent.com/juangff85/inferencias-estadisticas-ESP/main/images/12/figura12-17.png)

**Figura 12.17:** Resultado del análisis z-curve de los estudios sesgados de P2.

- La tasa esperada de descubrimiento y la tasa esperada de replicabilidad son ambas estadísticamente significativas y, por tanto, podemos esperar que los efectos observados se repliquen con éxito en estudios futuros.
- A pesar de que la potencia media observada (la tasa observada de descubrimiento) es del 100 %, la z-curve predice correctamente la tasa esperada de replicabilidad (que es del 5 %, ya que solo los errores de Tipo I serán estadísticamente significativos).
- La z-curve no es capaz de encontrar una indicación de sesgo, ya que la tasa esperada de descubrimiento y la tasa esperada de replicabilidad no difieren entre sí estadísticamente.
- Aunque la tasa observada de descubrimiento es 1 (lo que indica una potencia observada del 100 %), el intervalo de confianza oscila entre 0.66 y 1, lo que indica que los estudios podrían tener una potencia menor pero más realista y que el hecho de que el 100 % de los resultados fueran significativos podría haber ocurrido por azar.

### P7: Todavía no hemos realizado un análisis trim and fill y, dados los análisis anteriores (por ejemplo, el análisis z-curve), ¿qué afirmación es verdadera?

- Lo más probable es que el método trim-and-fill no indicara ningún estudio faltante que “rellenar”.
- El método trim-and-fill tiene una baja potencia conocida para detectar sesgo y contradeciría el análisis z-curve o p-curve informado antes.
- El análisis trim-and-fill indicaría sesgo, pero también lo hicieron el análisis p-curve y z-curve, y la estimación del tamaño del efecto ajustada mediante trim-and-fill no corrige adecuadamente el sesgo, por lo que el análisis no añadiría nada.
- El método trim-and-fill proporciona una estimación fiable del verdadero tamaño del efecto, cosa que no ofrece ninguno de los otros métodos discutidos hasta ahora, y por tanto debería informarse junto con otras pruebas de detección de sesgo.

### P8: El sesgo de publicación se define como la práctica de enviar y publicar selectivamente investigación científica. A lo largo de este capítulo nos hemos centrado en el envío selectivo de resultados significativos. ¿Puedes pensar en una línea de investigación o una pregunta de investigación en la que los investigadores pudieran preferir publicar selectivamente resultados no significativos?

## 12.7.1 Preguntas abiertas

- ¿Cuál es la idea detrás de la prueba GRIM?
- ¿Cuál es la definición de “sesgo de publicación”?
- ¿Qué es el problema del cajón de archivo (file-drawer problem)?
- En un funnel plot, ¿qué es cierto para los estudios que caen dentro del embudo (cuando está centrado en 0)?
- ¿Qué es cierto del enfoque trim-and-fill con respecto a su capacidad para detectar y corregir estimaciones del tamaño del efecto?
- Al utilizar el enfoque PET-PEESE, ¿qué es importante tener en cuenta cuando el metaanálisis tiene un número pequeño de estudios?
- ¿Qué conclusiones podemos extraer de las dos pruebas que se informan en un análisis p-curve?
