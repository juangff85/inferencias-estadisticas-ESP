---
title: 2. Control de errores
---

# 2. Control de errores

## 2.1. ¿Qué resultado puedes esperar si realizas un estudio?

Si realizas un estudio y planeas hacer una afirmación basada en la prueba estadística que vas a realizar, la probabilidad a largo plazo de hacer una afirmación correcta o errónea está determinada por *tres factores*: la **tasa de error Tip**, la **tasa de error Tipo II**, y la **probabilidad de que la hipótesis nula sea verdadera**. Hay **cuatro posibles resultados** de una prueba estadística, dependiendo de si el resultado es estadísticamente significativo o no, y de si la hipótesis nula es verdadera o no.

### Falso positivo (FP):
Concluir que existe un efecto real cuando en realidad **no existe un efecto real** (H₀ es verdadera). Esto también se denomina **error Tipo I**, y se indica con **α**.
### Falso negativo (FN):
Concluir que no existe un efecto real cuando en realidad **sí existe un efecto real** (H₁ es verdadera). Esto también se denomina **error Tipo II**, y se indica con **β**.
### Verdadero negativo (TN):
Concluir que no existe un efecto real cuando realmente **no existe un efecto real** (H₀ es verdadera). Este es el complemento de un falso positivo y, por tanto, se indica por **1 − α**.
### Verdadero positivo (TP):
Concluir que existe un efecto real cuando realmente **sí existe un efecto real** (H₁ es verdadera). Este es el complemento de un falso negativo y, por tanto, se indica por **1 − β**.

La probabilidad de observar un **verdadero positivo** cuando existe un efecto real es, a largo plazo, igual a la **potencia estadística** de tu estudio. La probabilidad de observar un **falso positivo** cuando la hipótesis nula es verdadera es, a largo plazo, igual al **nivel alfa** que hayas fijado, o a la **tasa de error Tipo I**.

*Figura 2.1: Diferencia entre errores Tipo I y Tipo II. Figura elaborada por Paul Ellis*.

![Figura 2.1](https://github.com/juangff85/inferencias-estadisticas-ESP/blob/main/images/02/figura2-1.jpg?raw=true)

Entonces, para el próximo estudio que realices, ¿cuál de los cuatro resultados posibles es más probable? Primero, supongamos que has fijado el nivel alfa en **5%**. Además, supongamos que has diseñado un estudio de manera que tenga 80% de potencia (y para este ejemplo supongamos que **Omniscient Jones** sabe que realmente tienes exactamente **80% de potencia**). Lo último que hay que especificar es la **probabilidad de que la hipótesis nula sea verdadera**. Supongamos que para este próximo estudio no tienes idea de si la hipótesis nula es verdadera o no, y que es **igual de probable que la hipótesis nula sea verdadera o que la hipótesis alternativa sea verdadera** (ambas con una probabilidad del 50%). Ahora podemos calcular cuál es el resultado más probable de un estudio de este tipo.

Antes de realizar este cálculo, tómate un momento para pensar si conoces la respuesta. Puede que hayas diseñado estudios con un nivel alfa del 5% y una potencia del 80%, donde creías que era igualmente probable que H₀ o H₁ fueran verdaderas. Sin duda, es útil tener **expectativas razonables sobre qué resultado esperar** cuando realizamos un estudio de este tipo. Sin embargo, según mi experiencia, muchos investigadores realizan estudios **sin pensar en estas probabilidades en absoluto**. A menudo esperan observar un **verdadero positivo**, incluso cuando, en la situación descrita anteriormente, el resultado más probable es un **verdadero negativo**. Calculemos ahora estas probabilidades.

Supongamos que realizamos **200 estudios** con un nivel alfa del **5%, 80% de potencia**, y una **probabilidad del 50% de que H₀ sea verdadera**. ¿Cuántos falsos positivos, verdaderos positivos, falsos negativos y verdaderos negativos deberíamos esperar en el largo plazo?

|          |H₀ verdadera (50%)|H₁ verdadera (50%)|
|----------|------------------|------------------|
|Resultado significativo (positivo)|Falso positivo: 5% × 50% = 2.5% (5 estudios)|Verdadero positivo: 80% × 50% = 40% (80 estudios)|
|Resultado no significativo (negativo)|Verdadero negativo: 95% × 50% = 47.5% (95 estudios)|Falso negativo: 20% × 50% = 10% (20 estudios)

En la tabla anterior vemos que **2.5% de todos los estudios serán falsos positivos** (una tasa de error Tipo I del 5%, multiplicada por una probabilidad del 50% de que H₀ sea verdadera). El **40% de todos los estudios serán verdaderos positivos** (80% de potencia multiplicado por una probabilidad del 50% de que H₁ sea verdadera). La probabilidad de un **falso negativo es 10%** (una tasa de error Tipo II del 20% multiplicada por una probabilidad del 50% de que H₁ sea verdadera). El resultado **más probable** es un **verdadero negativo**, con **47.5%**.

Puedes comprobar que estos porcentajes suman **100%**, por lo que hemos cubierto todas las posibilidades.

Puede que esta perspectiva no te entusiasme demasiado y que prefieras realizar estudios con una mayor probabilidad de observar un verdadero positivo. ¿Qué deberías hacer? Podemos **reducir el nivel alfa**, **aumentar la potencia**, o **aumentar la probabilidad de que H₁ sea verdadera**. Dado que la probabilidad de observar un verdadero positivo depende de la potencia multiplicada por la probabilidad de que H₁ sea verdadera, deberíamos diseñar estudios donde **ambos valores sean altos**. La potencia estadística puede aumentarse mediante cambios en el diseño del estudio (por ejemplo, aumentando el tamaño de muestra). La probabilidad de que H₁ sea verdadera depende de la hipótesis que estés poniendo a prueba.

Si la probabilidad de que H₁ sea verdadera es muy alta desde el principio, corres el riesgo de poner a prueba una hipótesis que ya está suficientemente establecida. Una solución —que quizá no ocurra muy a menudo en tu carrera— es idear una prueba de una hipótesis que no sea trivial pero que, cuando se la expliques a tus colegas, tenga mucho sentido para ellos. En otras palabras, ellos no habrían tenido la idea por sí mismos, pero después de que se la expliques, les parece extremadamente plausible. Ideas de investigación creativas de este tipo probablemente serán **muy raras en tu carrera académica**, si es que llegas a tener alguna. No toda la investigación necesita ser tan innovadora. También es extremadamente valioso realizar **estudios de replicación y extensión**, donde sea relativamente probable que H₁ sea verdadera, pero donde la comunidad científica aún se beneficie de saber que los hallazgos **se generalizan a diferentes circunstancias**.

## Valor predictivo positivo

John Ioannidis escribió un artículo muy conocido titulado “Why Most Published Research Findings Are False” (Ioannidis, 2005). Al mismo tiempo, hemos aprendido que si fijas tu alfa en 5%, la tasa de error Tipo 1 no será mayor que 5% (en el largo plazo). ¿Cómo se relacionan estas dos afirmaciones? ¿Por qué no son verdaderos el 95% de los hallazgos de investigación publicados? La clave para entender esta diferencia es que se calculan dos probabilidades diferentes. La tasa de error Tipo 1 es la probabilidad de decir que hay un efecto, cuando no hay efecto. Ioannidis calcula el valor predictivo positivo (PPV), que es la probabilidad condicional de que, si un estudio resulta mostrar un resultado estadísticamente significativo, realmente exista un efecto verdadero. Esta probabilidad es útil de entender, porque la gente a menudo se centra selectivamente en resultados significativos, y porque debido al sesgo de publicación, en algunas áreas de investigación solo se publican resultados significativos.

Un ejemplo de la vida real donde es útil entender el concepto de valor predictivo positivo se refiere al número de personas vacunadas y no vacunadas ingresadas en el hospital con síntomas de COVID-19. En algunos lugares, las estadísticas oficiales mostraban que el 50% de las personas hospitalizadas con COVID-19 estaban vacunadas. Si no entiendes el concepto de valor predictivo positivo, podrías creer que esto revela que es igual de probable terminar en el hospital, estés vacunado o no. Esto es incorrecto. Como visualiza muy bien la Figura 2.2, la probabilidad de que una persona esté vacunada es muy alta, y la probabilidad de que una persona vacunada termine en el hospital es mucho menor que la probabilidad de que una persona no vacunada termine en el hospital. Sin embargo, si seleccionamos solo a aquellos individuos que terminan en el hospital, estamos calculando una probabilidad condicionada a estar en el hospital.

*Figura 2.2: El valor predictivo positivo puede usarse para explicar por qué hay más personas vacunadas en el hospital que no vacunadas.*

![Figura 2.2](https://github.com/juangff85/inferencias-estadisticas-ESP/blob/main/images/02/figura2-2.jpg?raw=true)

Es útil entender cuál es la probabilidad de que, si has observado un resultado significativo en un experimento, el resultado sea realmente un verdadero positivo. En otras palabras, en el largo plazo, ¿cuántos verdaderos positivos podemos esperar, entre todos los resultados positivos (tanto verdaderos positivos como falsos positivos)? Esto se conoce como el Valor Predictivo Positivo (PPV). También podemos calcular cuántos falsos positivos podemos esperar, entre todos los resultados positivos (de nuevo, tanto verdaderos positivos como falsos positivos). Esto se conoce como la Probabilidad de Falso Positivo Reportado (Wacholder et al., 2004), a veces también denominada el Riesgo de Falso Positivo (Colquhoun, 2019).

![Imagen 1](https://github.com/juangff85/inferencias-estadisticas-ESP/blob/main/images/02/img1.png?raw=true)

El PPV y la FPRP combinan conceptos frecuentistas clásicos de potencia estadística y niveles alfa con probabilidades previas de que H₁ y H₀ sean verdaderas. Dependen de la proporción de estudios que ejecutas donde hay un efecto (H₁ es verdadera), y donde no hay un efecto (H₀ es verdadera), además de la potencia estadística y el nivel alfa. Al fin y al cabo, solo puedes observar un falso positivo si la hipótesis nula es verdadera, y solo puedes observar un verdadero positivo si la hipótesis alternativa es verdadera. Siempre que realizas un estudio, o bien estás operando en una realidad donde hay un efecto verdadero, o bien estás operando en una realidad donde no hay efecto —pero no sabes en qué realidad estás.

Cuando realizas estudios, serás consciente de todos los resultados de tus estudios (tanto los hallazgos significativos como los no significativos). En contraste, cuando lees la literatura, existe sesgo de publicación, y a menudo solo tienes acceso a resultados significativos. Aquí es donde pensar en el PPV (y la FPRP) se vuelve importante. Si fijamos el nivel alfa en 5%, en el largo plazo el 5% de los estudios donde H₀ es verdadera (FP + TN) serán significativos. Pero en una literatura con solo resultados significativos, no tenemos acceso a todos los verdaderos negativos, y por tanto es posible que la proporción de falsos positivos en la literatura sea mucho mayor que 5%.

Si continuamos el ejemplo anterior, vemos que hay 85 resultados positivos (80 + 5) en los 200 estudios. La probabilidad de falso positivo reportado es 5/85 = 0.0588. Al mismo tiempo, el nivel alfa del 5% garantiza que (en el largo plazo) el 5% de los 100 estudios donde la hipótesis nula es verdadera serán errores Tipo 1: 5% × 100 = 5. Cuando hacemos 200 estudios, como máximo 5% × 200 = 10 podrían ser falsos positivos (si H₀ fuera verdadera en todos los experimentos). En los 200 estudios que realizamos (y donde H₀ era verdadera solo en el 50% de los estudios), la proporción de falsos positivos para todos los experimentos es solo 2.5%. Así, para todos los experimentos que realizas, la proporción de falsos positivos, en el largo plazo, nunca será mayor que la tasa de error Tipo I fijada por el investigador (por ejemplo, 5% cuando H₀ es verdadera en todos los experimentos), pero puede ser menor (cuando H₀ es verdadera en menos del 100% de los experimentos).

*Figura 2.3: Captura de pantalla de la salida de los resultados de la app Shiny de PPV de Michael Zehetleitner y Felix Schönbrodt.
(Nota: FDR y FPRP son abreviaturas diferentes para lo mismo.)*

![Figura 2.3](https://github.com/juangff85/inferencias-estadisticas-ESP/blob/main/images/02/figura2-3.png?raw=true)

La gente a menudo dice algo como: “Bueno, todos sabemos que 1 de cada 20 resultados en la literatura publicada son errores Tipo 1”. Deberías ser capaz de entender que esto no es cierto en la práctica, después de aprender sobre el valor predictivo positivo. Solo cuando en el 100% de los estudios que realizas la hipótesis nula es verdadera, y todos los estudios se publican, solo entonces 1 de cada 20 estudios, en el largo plazo, son falsos positivos (y el resto correctamente revela que no hay una diferencia estadísticamente significativa). También explica por qué la concepción errónea común sobre el p-valor “Si has observado un hallazgo significativo, la probabilidad de que hayas cometido un error Tipo 1 (un falso positivo) es 5%.” no es correcta, porque en la práctica la hipótesis nula no es verdadera en todas las pruebas que se realizan (a veces la hipótesis alternativa es verdadera). De manera importante, mientras haya sesgo de publicación (donde hallazgos con resultados deseados acaban en la literatura científica, y por ejemplo resultados no significativos no se comparten), entonces incluso si los investigadores usan un nivel alfa del 5%, es bastante razonable asumir que mucho más del 5% de los hallazgos significativos en la literatura publicada son falsos positivos. En la literatura científica, la probabilidad de falso positivo reportado puede ser bastante alta, y bajo circunstancias específicas, incluso podría ser tan alta que la mayoría de los hallazgos de investigación publicados sean falsos. Esto ocurrirá cuando los investigadores examinen sobre todo estudios donde 1) la hipótesis nula es verdadera, 2) con baja potencia, o 3) cuando la tasa de error Tipo 1 esté inflada debido a p-hacking u otros tipos de sesgo.

## 2.3 Inflación del error Tipo 1

*Figura 2.4: Cita del libro de 1830 de Babbage, “Reflections on the Decline of Science in England And on Some of Its Causes.”*

![Figura 2.4](https://github.com/juangff85/inferencias-estadisticas-ESP/blob/main/images/02/figura2-4.jpg?raw=true)

Si realizas múltiples comparaciones, existe el riesgo de que la tasa de error Tipo 1 pueda inflarse. Cuando se planifican múltiples comparaciones, en algunos casos es posible controlar la tasa de error Tipo 1 reduciendo el nivel alfa para cada análisis individual. El enfoque más conocido para controlar comparaciones múltiples es la corrección de Bonferroni, donde el nivel alfa se divide por el número de pruebas que se realizan. Sin embargo, los investigadores también a menudo utilizan estrategias informales de análisis de datos que inflan la tasa de error Tipo 1. Babbage (1830) ya se quejaba de estas prácticas problemáticas en 1830, y dos siglos después, siguen siendo comunes. Barber (1976) ofrece una discusión en profundidad de una serie de enfoques, como mirar los datos para decidir qué hipótesis probar (a veces llamado “double dipping”); informar selectivamente solo aquellos análisis que confirman predicciones e ignorar resultados no significativos, recolectar muchas variables y realizar multitud de pruebas, o realizar análisis de subgrupos cuando el análisis planificado produce resultados no significativos; o tras una predicción no significativa, derivar una nueva hipótesis que esté apoyada por los datos y probar la hipótesis en los mismos datos de los que se derivó la hipótesis (a veces llamado HARKing, Hypothesizing After Results are Known (Kerr, 1998)). Muchos investigadores admiten haber usado prácticas que inflan las tasas de error (véase la sección sobre prácticas de investigación cuestionables en el Capítulo 15 sobre integridad de la investigación). Yo mismo he utilizado tales prácticas en el primer artículo científico que publiqué, antes de ser plenamente consciente de lo problemático que era esto; para un artículo que mis coautores y yo publicamos varios años después en el que reflexionamos sobre esto, véase Jostmann et al. (2016).

Para algunos paradigmas, los investigadores tienen mucha flexibilidad en cómo computar la variable dependiente principal. Elson y colegas examinaron 130 publicaciones que usaban la Competitive Reaction Time Task, en la que los participantes seleccionan la duración y la intensidad de ráfagas de un ruido desagradable que se entregará a un competidor (Elson et al., 2014). La tarea se usa para medir “conducta agresiva” de una manera ética. Para computar la puntuación, los investigadores pueden usar la duración de una ráfaga de ruido, la intensidad, o una combinación de ambas, promediada sobre cualquier número de ensayos, con varias transformaciones posibles de los datos. Las 130 publicaciones examinadas informaron 157 estrategias diferentes de cuantificación en total, mostrando que la mayoría de los cálculos de la variable dependiente eran únicos, usados solo en un único artículo. Uno podría preguntarse por qué los mismos autores a veces usaron cómputos diferentes entre artículos. Una posible explicación es que usaron esta flexibilidad en el análisis de datos para encontrar resultados estadísticamente significativos.

*Figura 2.5: Gráfico de publicaciones que usan CRTT (azul) y cuantificaciones únicas de la medida (rojo). Figura de FlexibleMeasures.com por Malte Elson.*

![Figura 2.5](https://github.com/juangff85/inferencias-estadisticas-ESP/blob/main/images/02/figura2-5.png?raw=true)

## 2.4 Detención opcional (Optional stopping)

*Figura 2.6: Captura de pantalla de un artículo científico que admite explícitamente haber utilizado optional stopping.*

![Figura 2.6](https://github.com/juangff85/inferencias-estadisticas-ESP/blob/main/images/02/figura2-6.png?raw=true)

Una práctica que **infla la tasa de error Tipo 1* se conoce como **optional stopping**. En el optional stopping un investigador analiza repetidamente los datos, continúa la recogida de datos cuando el resultado de la prueba no es estadísticamente significativo, pero se detiene cuando se observa un efecto significativo. La cita de un artículo publicado en la Figura 2.6 es un ejemplo donde los investigadores informan de manera transparente que utilizaron optional stopping, pero más comúnmente las personas **no revelan el uso de optional stopping en sus secciones de métodos**. En los últimos años, muchos investigadores han aprendido que el optional stopping es problemático. Esto ha llevado a algunos a la idea general de que **nunca se deberían recoger datos, mirar si los resultados son significativos y detener la recogida de datos cuando el resultado es significativo o, si no lo es, continuar recogiendo datos**. Esa no es la conclusión correcta, y es un ejemplo de volverse demasiado inflexible. El enfoque correcto —recoger datos en bloques, lo que se denomina **análisis secuencial**— ha sido ampliamente desarrollado por estadísticos, y se utiliza en muchos ensayos médicos. Hablaremos de los análisis secuenciales en el **Capítulo 10**. La principal lección es que ciertas prácticas de investigación pueden **aumentar la flexibilidad y la eficiencia de los estudios** que realizas cuando se hacen correctamente, pero las mismas prácticas pueden **inflar la tasa de error Tipo 1** cuando se hacen incorrectamente. Intentemos, por tanto, comprender mejor **cuándo y cómo corremos el riesgo de inflar nuestra tasa de error Tipo 1 con optional stopping**, y cómo hacerlo correctamente utilizando análisis secuencial.

Copia el código siguiente en **R** y ejecútalo. Este script simulará una recogida de datos en curso. Tras **10 participantes en cada condición**, se calcula un p-valor realizando una **prueba t independiente**, y esta prueba t se repite después de cada participante adicional que se recoja. Después, todos estos p-valores se representan gráficamente en función del tamaño de muestra creciente.

    n <- 200 # total number of datapoints (per condition) after initial 10
    d <- 0.0 # effect size d

    p <- numeric(n) # store p-values
    x <- numeric(n) # store x-values
    y <- numeric(n) # store y-values

    n <- n + 10 # add 10 to number of datapoints

    for (i in 10:n) { # for each simulated participants after the first 10
      x[i] <- rnorm(n = 1, mean = 0, sd = 1)
      y[i] <- rnorm(n = 1, mean = d, sd = 1)
      p[i] <- t.test(x[1:i], y[1:i], var.equal = TRUE)$p.value
    }

    p <- p[10:n] # Remove first 10 empty p-values

    # Create the plot
    par(bg = "#fffafa")
    plot(0, col = "red", lty = 1, lwd = 3, ylim = c(0, 1), xlim = c(10, n), 
         type = "l", xlab = "sample size", ylab = "p-value")
    lines(p, lwd = 2)
    abline(h = 0.05, col = "darkgrey", lty = 2, lwd = 2) # draw line at p = 0.05

    min(p) # Return lowest p-value from all looks
    cat("The lowest p-value was observed at sample size", which.min(p) + 10) 
    cat("The p-value dropped below 0.05 for the first time at sample size:", 
        ifelse(is.na(which(p < 0.05)[1] + 10), "NEVER", which(p < 0.05)[1] + 10))

Por ejemplo, en la **Figura 2.7** ves el p-valor representado en el eje y (de 0 a 1) y el tamaño de muestra representado en el eje x (de 0 a 200). Para esta simulación, el tamaño del efecto verdadero era **d = 0**, lo que significa que **no hay efecto real**. Por tanto, solo podemos observar **verdaderos negativos o falsos positivos**. A medida que aumenta el tamaño de la muestra, el p-valor se mueve lentamente hacia arriba y hacia abajo (recuerda del **Capítulo 1 sobre p-valores** que cuando no hay efecto real, los p-valores están distribuidos uniformemente). En la **Figura 2.7** el p-valor cae por debajo de la línea gris (que indica un nivel alfa de 0.05) después de recoger **83 participantes** en cada condición, solo para volver después a valores de p mayores. A partir de esta figura queda claro que **cuantas más veces miramos los datos, y cuanto mayor es el tamaño total de la muestra, mayor es la probabilidad de que uno de los análisis produzca un p < α**. Si los recursos fueran infinitos, la tasa de error Tipo 1 sería **1**, y un investigador siempre podría encontrar un resultado significativo mediante optional stopping.

*Figura 2.7: p-valores simulados para cada observación adicional cuando la hipótesis nula es verdadera.*

![Figura 2.7](https://github.com/juangff85/inferencias-estadisticas-ESP/blob/main/images/02/figura2-7.gif?raw=true)

Cuando existe un efecto verdadero, vemos que los p-valores también varían, pero **eventualmente caerán por debajo del nivel alfa**. Simplemente no sabemos exactamente cuándo ocurrirá esto debido al **error de muestreo**. Cuando realizamos un **análisis de potencia a priori**, podemos calcular la probabilidad de que examinar un tamaño de muestra específico produzca un p-valor significativo. En la **Figura 2.8** vemos la misma simulación, pero ahora cuando existe un efecto verdadero pequeño de **d = 0.3**. Con **200 observaciones por condición**, un análisis de potencia de sensibilidad revela que tenemos **85% de potencia**. Si analizáramos los datos en un análisis intermedio (por ejemplo, después de **150 observaciones**) a menudo ya encontraríamos un efecto estadísticamente significativo (ya que tendríamos **74% de potencia**). Esto ilustra un beneficio de los **análisis secuenciales**, donde controlamos las tasas de error pero podemos **detenernos antes en un análisis intermedio**. Los análisis secuenciales son especialmente útiles en estudios grandes o costosos donde existe incertidumbre sobre el tamaño del efecto verdadero.

*Figura 2.8: p-valores simulados para cada observación adicional cuando d = 0.3.*

![Figura 2.8](https://github.com/juangff85/inferencias-estadisticas-ESP/blob/main/images/02/figura2-8.gif?raw=true)

Examinemos ahora de forma más formal la **inflación de la tasa de error Tipo 1** mediante optional stopping en un estudio de simulación. Copia el código siguiente en **R** y ejecútalo. Ten en cuenta que las **50 000 simulaciones** (necesarias para obtener tasas de error razonablemente precisas) tardan algo de tiempo en ejecutarse.

    N <- 100 # total datapoints (per condition)
    looks <- 5 # set number of looks at the data
    nsims <- 50000 # number of simulated studies
    alphalevel <- 0.05 # set alphalevel

    if(looks > 1){
      look_at_n <- ceiling(seq(N / looks, N, (N - (N / looks)) / (looks - 1)))
    }  else {
      look_at_n <- N
    }
    look_at_n <- look_at_n[look_at_n > 2] # Remove looks at N of 1 or 2
    looks<-length(look_at_n) # if looks are removed, update number of looks

    matp <- matrix(NA, nrow = nsims, ncol = looks) # Matrix for p-values l tests
    p <- numeric(nsims) # Variable to save pvalues

    # Loop data generation for each study, then loop to perform a test for each N
    for (i in 1:nsims) {
      x <- rnorm(n = N, mean = 0, sd = 1)
      y <- rnorm(n = N, mean = 0, sd = 1)
      for (j in 1:looks) {
        matp[i, j] <- t.test(x[1:look_at_n[j]], y[1:look_at_n[j]], 
                             var.equal = TRUE)$p.value # perform the t-test, store
      }
      cat("Loop", i, "of", nsims, "\n")
    }

    # Save Type 1 error rate smallest p at all looks
    for (i in 1:nsims) {
      p[i] <- ifelse(length(matp[i,which(matp[i,] < alphalevel)]) == 0, 
                     matp[i,looks], matp[i,which(matp[i,] < alphalevel)])
    }

    hist(p, breaks = 100, col = "grey") # create plot
    abline(h = nsims / 100, col = "red", lty = 3)

    cat("Type 1 error rates for look 1 to", looks, ":", 
        colSums(matp < alphalevel) / nsims)
    cat("Type 1 error rate when only the lowest p-value for all looks is reported:", 
        sum(p < alphalevel) / nsims)

(Este código realiza múltiples pruebas t independientes sobre datos simulados, examinando los datos varias veces hasta alcanzar el tamaño máximo de muestra).

Cuando realizas **solo una prueba**, la tasa de error Tipo 1 es la probabilidad de encontrar un p-valor menor que tu nivel alfa cuando no hay efecto. En un escenario de optional stopping en el que miras los datos **dos veces**, la tasa de error Tipo 1 es la probabilidad de encontrar un p-valor menor que el nivel alfa en la primera mirada **más** la probabilidad de no encontrar un p-valor menor que el nivel alfa en la primera mirada pero encontrar uno en la segunda. Esto es una **probabilidad condicional**, lo que hace que el control del error sea un poco más complejo que cuando múltiples análisis son completamente independientes.

Entonces, ¿cuánto **infla optional stopping la tasa de error Tipo 1**? ¿Y qué p-valores podemos esperar bajo optional stopping?

Comienza ejecutando la simulación **sin cambiar ningún valor**, simulando **100 participantes en cada condición**, mirando los datos **5 veces**, con un alfa de **0.05**. Las **50 000 simulaciones** tardarán un rato. Deberías ver algo similar a la **Figura 2.9**.

*Figura 2.9: Simulación de 500 000 estudios realizando 5 análisis intermedios con un nivel alfa del 5%*.

![Figura 2.9](https://github.com/juangff85/inferencias-estadisticas-ESP/blob/main/images/02/figura2-9.png?raw=true)

Observamos **100 barras**, una para cada percentil (por ejemplo, todos los p-valores entre 0.00 y 0.01, entre 0.01 y 0.02, etc.). Hay una línea horizontal que indica dónde caerían todos los p-valores si estuvieran **distribuidos uniformemente**.

La distribución de p-valores es peculiar. Vemos que, en comparación con una distribución uniforme, **faltan muchos resultados justo por encima del umbral alfa de 0.05**, y parecen haberse desplazado **justo por debajo de 0.05**, donde hay una frecuencia mucho mayor de resultados que cuando los datos no se analizan repetidamente. Observa cómo p-valores relativamente altos (por ejemplo p = 0.04) son más comunes que p-valores más bajos (por ejemplo p = 0.01). En el **Capítulo 12 sobre detección de sesgos** veremos que técnicas estadísticas como **p-curve** pueden detectar este patrón.

Cuando se utiliza un nivel alfa del **5% con 5 miradas a los datos**, la tasa global de error Tipo 1 se **infla hasta el 14%**. Si reducimos el nivel alfa en cada análisis intermedio, la tasa global de error Tipo 1 puede controlarse. La forma de la distribución de p-valores seguirá siendo peculiar, pero el número total de resultados significativos se mantendrá en el nivel alfa deseado. La conocida **corrección de Bonferroni** controla la tasa de error Tipo 1 dividiendo α por el número de análisis, pero la **corrección de Pocock** es ligeramente más eficiente. Para más información sobre cómo realizar análisis intermedios controlando las tasas de error, véase el **Capítulo 10 sobre análisis secuencial**.

## 2.5 Justificación de las tasas de error

Si rechazamos , podemos rechazarla cuando es verdadera; si aceptamos , podemos estar aceptándola cuando es falsa, es decir, cuando realmente alguna alternativa es verdadera. Estas dos fuentes de error rara vez pueden eliminarse completamente; en algunos casos será más importante evitar la primera, en otros la segunda. Se nos recuerda el viejo problema considerado por Laplace sobre el número de votos en un tribunal de jueces que debería ser necesario para condenar a un prisionero. ¿Es más grave condenar a un hombre inocente o absolver a un culpable? Eso dependerá de las consecuencias del error; de si el castigo es la muerte o una multa; de cuál es el peligro para la comunidad de los criminales liberados; y de cuáles son las opiniones éticas actuales sobre el castigo. Desde el punto de vista de la teoría matemática, todo lo que podemos hacer es mostrar cómo el riesgo de los errores puede ser controlado y minimizado. El uso de estas herramientas estadísticas en cualquier caso dado, al determinar exactamente cómo debe establecerse el equilibrio, debe dejarse al investigador.

Aunque en teoría la tasa de error Tipo 1 y Tipo 2 debería ser justificada por el investigador (como escriben Neyman y Pearson (1933) arriba), en la práctica los investigadores tienden a imitar a otros. El uso por defecto de un nivel alfa de 0.05 ya puede encontrarse en el trabajo de Gosset sobre la distribución t (Cowles & Davis, 1982; Kennedy-Shaffer, 2019), quien creía que una diferencia de dos errores estándar (un valor z de 2) era suficientemente rara. El uso por defecto de 80% de potencia (o una tasa de error Tipo 2 del 20%) está igualmente basado en preferencias personales de Cohen (1988), quien escribe:

Se propone aquí como convención que, cuando el investigador no tenga otra base para fijar el valor de potencia deseado, se utilice el valor .80. Esto significa que beta se fija en .20. Este valor se ofrece por varias razones (Cohen, 1965, pp. 98-99). La principal de ellas toma en consideración la convención implícita para alfa de .05. El beta de .20 se elige con la idea de que la gravedad relativa general de estos dos tipos de errores es del orden de .20/.05, es decir, que los errores Tipo I son del orden de cuatro veces más graves que los errores Tipo II. Esta convención de potencia deseada de .80 se ofrece con la esperanza de que sea ignorada siempre que un investigador pueda encontrar una base en sus preocupaciones sustantivas sobre su investigación específica para elegir un valor ad hoc.

Vemos que las convenciones se construyen sobre convenciones: la norma de aspirar a 80% de potencia está construida sobre la norma de fijar el nivel alfa en 5%. Aunque no hay nada especial en un nivel alfa del 5%, es interesante reflexionar sobre por qué se ha vuelto tan ampliamente establecido. Irwin Bross (1971) sostiene que el uso de un nivel alfa es funcional y eficiente cuando se ve como un aspecto de las redes de comunicación entre científicos, y escribe “Así, la especificación de los niveles críticos […] ha demostrado en la práctica ser un método eficaz para controlar el ruido en las redes de comunicación.” Bross cree que el umbral de 0.05 es algo, pero no completamente, arbitrario, y nos pide imaginar qué habría ocurrido si se hubiera propuesto un nivel alfa de 0.001, o un nivel alfa de 0.20. En ambos casos, cree que la convención no se habría difundido – en el primer caso porque en muchos campos no hay recursos suficientes para hacer afirmaciones con una tasa de error tan baja, y en el segundo caso porque pocos investigadores habrían encontrado que ese nivel alfa fuera una cuantificación satisfactoria de eventos ‘raros’. Uygun Tunç et al. (2023) argumentan que una posible razón es que, en lo que respecta a las convenciones, un nivel alfa del 5% podría ser lo suficientemente bajo como para que los colegas se tomen en serio cualquier afirmación hecha con esta tasa de error, mientras que al mismo tiempo sea lo suficientemente alto como para que los colegas estén motivados a realizar un estudio de replicación independiente para aumentar o disminuir nuestra confianza en la afirmación. Aunque tasas de error más bajas establecerían afirmaciones de forma más convincente, esto también requeriría más recursos. Uno podría especular que en áreas de investigación donde no toda afirmación es lo suficientemente importante como para justificar cuidadosamente costes y beneficios, el 5% tiene una función pragmática al facilitar conjeturas y refutaciones en campos que por lo demás carecen de un enfoque coordinado para la generación de conocimiento, pero se enfrentan a recursos limitados.

No obstante, algunos investigadores han propuesto alejarse del uso por defecto de un nivel alfa del 5%. Por ejemplo, Johnson (2013) propone un nivel de significación por defecto de 0.005 o 0.001. Otros han advertido contra una recomendación tan general porque los recursos adicionales necesarios para reducir la tasa de error Tipo 1 podrían no merecer la pena en relación con los costes (Lakens et al., 2018). Un nivel alfa más bajo requiere un tamaño de muestra mayor para lograr la misma potencia estadística. Si el tamaño de muestra no puede aumentarse, un nivel alfa más bajo reduce la potencia estadística y aumenta la tasa de error Tipo 2. Que eso sea deseable debería evaluarse caso por caso.

Hay dos razones principales para abandonar el uso universal de un nivel alfa del 5%. La primera es que la toma de decisiones se vuelve más eficiente (Gannon et al., 2019; Mudge et al., 2012). Si los investigadores usan contrastes de hipótesis para tomar decisiones dicotómicas desde un enfoque falsacionista metodológico de las inferencias estadísticas, y tienen un cierto tamaño máximo de muestra que están dispuestos o son capaces de recoger, típicamente es posible tomar decisiones de forma más eficiente eligiendo tasas de error de modo que el coste combinado de errores Tipo 1 y Tipo 2 se minimice. Si pretendemos o bien minimizar o bien equilibrar las tasas de error Tipo 1 y Tipo 2 para un tamaño de muestra y un tamaño de efecto dados, el nivel alfa debería fijarse no basándose en la convención, sino ponderando el coste relativo de ambos tipos de errores (Maier & Lakens, 2022).

Por ejemplo, imagina que un investigador planea recoger 64 participantes por condición para detectar un efecto de d = 0.5, y pondera el coste de los errores Tipo 1 cuatro veces más que el de los errores Tipo 2. Este es exactamente el escenario que Cohen (1988) describió, y con 64 participantes por condición el peso relativo de los errores Tipo 1 y Tipo 2 produce una tasa de error Tipo 1 del 5% y una tasa de error Tipo 2 del 20%. Ahora imagina que este investigador se da cuenta de que tiene recursos para recoger 80 observaciones en lugar de solo 64. Con un interés en un tamaño de efecto de d = 0.5, el peso relativo de los errores Tipo 1 y Tipo 2 de 4 (un como sugirió Cohen) se vería satisfecho si fijaran el nivel alfa en 0.037, ya que la tasa de error Tipo 2 sería 0.147. Alternativamente, el investigador podría haber decidido recoger 64 observaciones, pero en lugar de equilibrar las tasas de error, fijar el nivel alfa de tal manera que la tasa de error combinada ponderada se minimice, lo cual se logra cuando el nivel alfa se fija en 0.033, como se visualiza en la Figura 2.10 (para más información, véase Maier & Lakens (2022)).

Warning in ggplot2::geom_point(ggplot2::aes(x = res$minimum, y = (costT1T2 * : All aesthetics have length 1, but the data has 9999 rows.
ℹ Please consider using annotate() or provide this layer with data containing
a single row.

*Figura 2.10: Tasa de error combinada ponderada, minimizada en alfa = 0.037.*

![Figura 2.10](https://github.com/juangff85/inferencias-estadisticas-ESP/blob/main/images/02/figura2-10.png?raw=true)

Justificar las tasas de error puede llevar a situaciones donde el nivel alfa se incrementa por encima de 0.05, porque esto conduce a una mejor toma de decisiones. Winer (1962) escribe:

El uso frecuente de los niveles de significación .05 y .01 es una cuestión de convención con poca base científica o lógica. Cuando es probable que la potencia de las pruebas sea baja bajo estos niveles de significación, y cuando los errores Tipo 1 y Tipo 2 son de aproximadamente igual importancia, los niveles de significación .30 y .20 pueden ser más apropiados que .05 y .01.

El razonamiento aquí es que un diseño que tiene 70% de potencia para el tamaño de efecto más pequeño de interés no equilibraría las tasas de error Tipo 1 y Tipo 2 de una manera sensata. Por supuesto, tal incremento del nivel alfa solo debería considerarse aceptable cuando los autores puedan justificar que el coste del incremento en la tasa de error Tipo 1 está suficientemente compensado por el beneficio de la disminución de la tasa de error Tipo 2. Esto abarcará casos donde (1) el estudio tendrá implicaciones prácticas que requieren toma de decisiones, (2) se proporciona un análisis coste-beneficio que da una justificación clara para los costes relativamente altos de un error Tipo 2, (3) la probabilidad de que sea falsa es relativamente baja, y (4) no es factible reducir las tasas de error globales recogiendo más datos.

Uno también debería reflexionar cuidadosamente sobre la elección del nivel alfa cuando un experimento alcanza una potencia estadística muy alta para todos los tamaños de efecto que se consideran significativos. Si un estudio tiene 99% de potencia para tamaños de efecto de interés, y por tanto una tasa de error Tipo 2 del 1%, pero usa el nivel alfa por defecto del 5%, también sufre de una falta de equilibrio, y el uso de un nivel alfa más bajo conduciría a una decisión más equilibrada, y aumentaría la severidad de la prueba.

La segunda razón para hacer una elección específica del estudio del nivel alfa es más relevante para grandes conjuntos de datos, y está relacionada con la paradoja de Lindley. A medida que la potencia estadística aumenta, algunos p-valores por debajo de 0.05 (por ejemplo, p = 0.04) pueden ser más probables cuando no hay efecto que cuando hay un efecto. Para prevenir situaciones donde un frecuentista rechaza la hipótesis nula basándose en p < 0.05, cuando la evidencia en la prueba favorece la hipótesis nula sobre la alternativa, se recomienda reducir el nivel alfa como función del tamaño de muestra. La necesidad de hacerlo se discute por Leamer (1978), quien escribe “La regla general bastante popular ahora, es decir, fijar el nivel de significación arbitrariamente en .05, se muestra deficiente en el sentido de que desde todo punto de vista razonable el nivel de significación debería ser una función decreciente del tamaño de muestra.” La idea de este enfoque es reducir el nivel alfa de modo que un factor de Bayes o una verosimilitud calculada para un resultado significativo nunca sería evidencia para la hipótesis nula (para una aplicación Shiny en línea para realizar tales cálculos, véase aquí.

## 2.6 Por qué no necesitas ajustar tu nivel alfa para todas las pruebas que harás en tu vida.

Algunos investigadores critican las correcciones por comparaciones múltiples porque también se podría corregir por todas las pruebas que harás en tu vida (Perneger, 1998). Si eliges usar un enfoque de Neyman-Pearson a la estadística, la única razón para corregir por todas las pruebas que realizas en tu vida es cuando todo el trabajo que has hecho en tu vida pone a prueba una sola teoría, y usarías tus últimas palabras para decidir aceptar o rechazar esta teoría, siempre que solo una de todas las pruebas individuales que has realizado haya producido un p < . Los investigadores rara vez trabajan así.

En cambio, en un enfoque de Neyman-Pearson al contraste de hipótesis, el objetivo es usar datos para tomar decisiones sobre cómo actuar. Neyman (1957) llama a su enfoque conducta inductiva. El resultado de un experimento lleva a uno a tomar diferentes posibles acciones, que pueden ser prácticas (por ejemplo, implementar un nuevo procedimiento, abandonar una línea de investigación) o científicas (por ejemplo, afirmar que hay o no hay un efecto). Desde un enfoque error-estadístico (Mayo, 2018), tasas de error Tipo 1 infladas significan que se ha vuelto muy probable que puedas afirmar apoyo para tu hipótesis, incluso cuando la hipótesis está equivocada. Esto reduce la severidad de la prueba. Para prevenir esto, necesitamos controlar nuestra tasa de error al nivel de nuestra afirmación.

Una distinción útil en la literatura sobre pruebas múltiples es un enfoque de prueba unión-intersección, y un enfoque de prueba intersección-unión (Dmitrienko & D’Agostino Sr, 2013). En un enfoque unión-intersección, se hace una afirmación cuando al-menos-una prueba es significativa. En estos casos, se requiere una corrección por comparaciones múltiples para controlar la tasa de error. En un enfoque intersección-unión, se hace una afirmación cuando todas las pruebas realizadas son estadísticamente significativas, y no se requiere corrección por comparaciones múltiples (de hecho, bajo algunos supuestos los investigadores incluso podrían incrementar el nivel alfa en un enfoque intersección-unión).

Supongamos que recogemos datos de 100 participantes en una condición de control y de tratamiento. Recogemos 3 variables dependientes (dv1, dv2, y dv3). En la población no hay diferencia entre grupos en ninguna de estas tres variables (el tamaño del efecto verdadero es 0). Analizaremos las tres dv en pruebas t independientes. Esto requiere especificar nuestro nivel alfa, y por tanto decidir si necesitamos corregir por comparaciones múltiples. Por alguna razón que no entiendo del todo, varios investigadores creen que es difícil decidir cuándo necesitas corregir por comparaciones múltiples. Como escriben Bretz, Hothorn, & Westfall (2011) en su excelente libro “Multiple Comparisons Using R”: “La elección apropiada de las hipótesis nulas de interés primario es una cuestión controvertida. Es decir, no siempre está claro qué conjunto de hipótesis debería constituir la familia H1,…,Hm. Este tema a menudo ha estado en disputa y no hay consenso general.” En uno de los mejores artículos sobre controlar por comparaciones múltiples que existen, Bender & Lange (2001) escriben: “Desafortunadamente, no hay una respuesta simple y única a cuándo es apropiado controlar qué tasa de error. Diferentes personas pueden tener opiniones diferentes pero no obstante razonables. Además del problema de decidir qué tasa de error debería estar bajo control, primero debe definirse qué pruebas de un estudio pertenecen a un experimento.”

Nunca he entendido esta confusión, al menos no cuando se trabaja dentro de un enfoque de Neyman-Pearson al contraste de hipótesis, donde el objetivo es controlar las tasas de error al nivel de una afirmación estadística. Cómo controlamos las tasas de error depende de la(s) afirmación(es) que queremos hacer. Podríamos querer actuar como si (o afirmar que) nuestro tratamiento funciona si hay una diferencia entre las condiciones de tratamiento y control en cualquiera de las tres variables. Esto significa que consideramos la predicción corroborada cuando el p-valor de la primera prueba t es menor que el nivel alfa, el p-valor de la segunda prueba t es menor que el nivel alfa, o el p-valor de la tercera prueba t es menor que el nivel alfa. Esto cae bajo el enfoque unión-intersección, y un investigador debería corregir el nivel alfa por comparaciones múltiples.

También podríamos querer hacer tres predicciones diferentes. En lugar de una hipótesis (“algo ocurrirá”) tenemos tres hipótesis diferentes, y predecimos que habrá un efecto en dv1, dv2, y dv3. Cada una de estas afirmaciones puede ser corroborada, o no. Como estas son tres pruebas, que informan tres afirmaciones, no hay comparaciones múltiples, y no se requiere corrección del nivel alfa.

Podría parecer que los investigadores pueden librarse de realizar correcciones por comparaciones múltiples formulando una hipótesis para cada posible prueba que realizarán. De hecho, pueden. Para una matriz de correlaciones de 10, un investigador podría declarar que está probando 45 predicciones únicas, cada una con un nivel alfa no corregido. Sin embargo, los lectores podrían cuestionar razonablemente si estas 45 pruebas fueron todas predichas por una teoría sensata, o si el autor simplemente está inventando predicciones para no tener que corregir el nivel alfa. Distinguir entre estos dos escenarios no es una cuestión estadística, sino una cuestión teórica. Si solo unas pocas de las 45 pruebas corroboran la predicción, el pobre historial de las predicciones debería hacer que los lectores duden de si el cuerpo de trabajo que se usó para derivar las predicciones tiene algo a favor.

Hay diferentes maneras de controlar las tasas de error, siendo la más fácil la corrección de Bonferroni y el procedimiento secuencial Holm-Bonferroni, apenas un poco menos conservador. Cuando el número de pruebas estadísticas se vuelve sustancial, a veces es preferible controlar lo que se conoce como la tasa de descubrimientos falsos (o la proporción esperada de descubrimientos falsos), en lugar de la tasa de error de falsos positivos (Benjamini & Hochberg, 1995).

## 2.7 Análisis de potencia

Hasta ahora nos hemos centrado en gran medida en el control del error Tipo 1. Como quedó claro en la Figura 2.8, cuando hay un efecto verdadero los p-valores eventualmente se volverán más pequeños que cualquier nivel alfa dado a medida que el tamaño de muestra se vuelve lo suficientemente grande. Al diseñar un experimento, un objetivo podría ser elegir un tamaño de muestra que proporcione una tasa de error Tipo 2 deseada para un tamaño de efecto de interés. Esto puede lograrse realizando un análisis de potencia a priori. La potencia estadística de una prueba (y, por tanto, la tasa de error Tipo 2) depende del tamaño del efecto estandarizado (o el tamaño del efecto en bruto y la desviación estándar), el tamaño de muestra, y el nivel alfa. Manteniendo todo lo demás constante, cuanto mayores sean el tamaño del efecto, el tamaño de muestra, y el nivel alfa, mayor será la potencia estadística, y cuanto menores sean el tamaño del efecto, el tamaño de muestra, y el nivel alfa, menor será la potencia estadística.

Es importante destacar que el objetivo de un análisis de potencia a priori no es lograr suficiente potencia para el tamaño del efecto verdadero. El tamaño del efecto verdadero siempre es desconocido cuando se diseña un estudio. El objetivo de un análisis de potencia a priori es lograr suficiente potencia, dada una suposición específica del tamaño del efecto que un investigador quiere detectar. Del mismo modo que una tasa de error Tipo I es la probabilidad máxima de cometer un error Tipo I condicional al supuesto de que la hipótesis nula es verdadera, un análisis de potencia a priori se calcula bajo el supuesto de un tamaño de efecto específico. Se desconoce si este supuesto es correcto. Todo lo que un investigador puede hacer es asegurarse de que sus supuestos estén bien justificados. Las inferencias estadísticas basadas en una prueba donde el error Tipo II está controlado son condicionales al supuesto de un tamaño de efecto específico. Permiten la inferencia de que, suponiendo que el tamaño del efecto verdadero es al menos tan grande como el utilizado en el análisis de potencia a priori, la tasa máxima de error Tipo II en un estudio no es mayor que un valor deseado.

En la Figura 2.11 vemos la distribución esperada de tamaños de efecto estandarizados observados (d de Cohen) para una prueba t independiente con 50 observaciones en cada condición. La curva en forma de campana de la izquierda representa las expectativas si la hipótesis nula es verdadera, y las áreas rojas en la cola representan errores Tipo 1. La curva en forma de campana de la derecha representa las expectativas si la hipótesis alternativa es verdadera, y un tamaño de efecto de d = 0.5. La línea vertical en d = 0.4 representa el tamaño de efecto crítico. Con este tamaño de muestra y un nivel alfa de 0.05, los tamaños de efecto observados menores que d = 0.4 no serán estadísticamente significativos. El tamaño de efecto crítico es independiente del tamaño del efecto verdadero (puedes cambiar d = 0.5 por cualquier otro valor). Si hay un efecto verdadero, estos resultados serán errores Tipo 2, ilustrados por el área sombreada azul. El resto de la curva refleja verdaderos positivos, cuando hay un efecto verdadero, y los tamaños de efecto observados son estadísticamente significativos. La potencia de la prueba es la proporción de la distribución de la derecha que es mayor que el valor crítico.

*Figura 2.11: Distribución de d = 0 y d = 0.5 para una prueba t independiente con n = 50.*

![Figura 2.11](https://github.com/juangff85/inferencias-estadisticas-ESP/blob/main/images/02/figura2-11.png?raw=true)

La cuestión del control del error Tipo 2 se discutirá con más detalle en el Capítulo 8 sobre la justificación del tamaño de muestra. Aunque el tema del control del error Tipo 2 solo se discute brevemente aquí, es al menos tan importante como el control del error Tipo 1. Un estudio informativo debería tener una alta probabilidad de observar un efecto si hay un efecto. De hecho, la recomendación por defecto de aspirar a 80% de potencia deja una probabilidad sorprendentemente grande (20%) de un error Tipo 2. Si a un investigador solo le importa no cometer un error de decisión, pero al investigador no le importa si este error de decisión es un falso positivo o un falso negativo, podría argumentarse que los errores Tipo 1 y Tipo 2 se ponderan por igual. Por lo tanto, diseñar un estudio con tasas de error equilibradas (por ejemplo, una tasa de error Tipo 1 del 5% y 95% de potencia) tendría sentido.
