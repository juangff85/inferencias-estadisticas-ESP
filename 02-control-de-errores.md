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

![Figura 2.1](https://github.com/Surprised-Kiwi/inferencias-estadisticas-ESP/blob/main/images/02/figura2-1.jpg?raw=true)

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

![Figura 2.2](https://github.com/Surprised-Kiwi/inferencias-estadisticas-ESP/blob/main/images/02/figura2-2.jpg?raw=true)

Es útil entender cuál es la probabilidad de que, si has observado un resultado significativo en un experimento, el resultado sea realmente un verdadero positivo. En otras palabras, en el largo plazo, ¿cuántos verdaderos positivos podemos esperar, entre todos los resultados positivos (tanto verdaderos positivos como falsos positivos)? Esto se conoce como el Valor Predictivo Positivo (PPV). También podemos calcular cuántos falsos positivos podemos esperar, entre todos los resultados positivos (de nuevo, tanto verdaderos positivos como falsos positivos). Esto se conoce como la Probabilidad de Falso Positivo Reportado (Wacholder et al., 2004), a veces también denominada el Riesgo de Falso Positivo (Colquhoun, 2019).

![Imagen 1](https://github.com/Surprised-Kiwi/inferencias-estadisticas-ESP/blob/main/images/02/img1.png?raw=true)
