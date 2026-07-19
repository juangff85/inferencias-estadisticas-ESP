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
