# 6. Tamaños del Efecto

## 6.1. La Importancia del Tamaño del Efecto (Effect Size, ES)

Un error común en la investigación es centrarse únicamente en la significación estadística (el valor $p$) e ignorar la **magnitud** o el **tamaño del efecto (ES)**.

El tamaño del efecto es una medida estandarizada o no estandarizada de la magnitud de un fenómeno de interés. Mientras que el valor $p$ informa sobre si un efecto es *probable* que sea distinto de cero, el ES informa sobre *qué tan grande* es ese efecto.

### 6.1.1. Significancia Estadística vs. Significación Práctica

* **Significancia Estadística:** Se refiere a si el efecto es improbable bajo la hipótesis nula ($p < \alpha$).
* **Significancia Práctica:** Se refiere a si el efecto es lo suficientemente grande como para ser importante, relevante o útil en el mundo real.

Un efecto puede ser estadísticamente significativo ($p$ muy pequeño) pero prácticamente insignificante (ES muy pequeño), especialmente con muestras muy grandes.

## 6.2. Tipos de Tamaños del Efecto

Los tamaños del efecto se dividen generalmente en dos categorías:

### 6.2.1. ES Estandarizados (Basados en la Varianza)

Estos tamaños del efecto expresan la magnitud del efecto en unidades de desviación estándar, lo que permite la comparación entre estudios que utilizan diferentes escalas de medición.

* **$d$ de Cohen (para diferencias de medias):** Mide la diferencia entre dos medias dividida por la desviación estándar combinada (o agrupada). Un $d$ de Cohen de 0.50 significa que las medias difieren en media desviación estándar.
    $$d = \frac{\mu_1 - \mu_2}{\sigma_{\text{pooled}}}$$
    * **Pautas de Cohen (Interpretación Común, aunque simplista):**
        * $d = 0.20$: Efecto Pequeño
        * $d = 0.50$: Efecto Medio
        * $d = 0.80$: Efecto Grande
* **Eta Cuadrada ($\eta^2$) y Omega Cuadrada ($\omega^2$) (para ANOVA):** Miden la proporción de la varianza total que es atribuible al efecto. La $\omega^2$ es preferible porque es un estimador de ES menos sesgado que $\eta^2$.
* **$r$ (Coeficiente de Correlación):** Mide la fuerza y dirección de la relación lineal entre dos variables.

### 6.2.2. ES No Estandarizados (Basados en la Métrica Original)

Estos tamaños del efecto se expresan en las unidades originales de la variable de resultado, lo que a menudo facilita la interpretación práctica.

* **Diferencia de Medias no estandarizada ($\mu_1 - \mu_2$):** Útil cuando las unidades de medida son significativas (por ejemplo, kilogramos, segundos, ingresos).
* **Coeficientes de Regresión no estandarizados ($b$):** Muestra el cambio en la variable dependiente por un cambio de una unidad en la variable predictora.

## 6.3. Justificación del Tamaño del Efecto de Interés

Para realizar inferencias significativas, el investigador debe especificar un **Tamaño del Efecto de Interés (ESOI)** antes de recopilar los datos. Este ESOI se utiliza para:

1.  **Justificar el Tamaño de la Muestra (Capítulo 8):** Calcular cuántos participantes se necesitan para detectar el ESOI con suficiente potencia.
2.  **Formular Hipótesis de Intervalo (Capítulo 9):** Definir los umbrales de importancia práctica para realizar Pruebas de Equivalencia.

El ESOI debe basarse en:

* **Valores Mínimos de Importancia Práctica:** El efecto más pequeño que sería relevante en el mundo real (por ejemplo, la reducción mínima en la presión arterial que justificaría el costo de un medicamento).
* **Conocimiento Previo/Literatura:** El tamaño del efecto encontrado en estudios previos (Meta-análisis, Capítulo 11).
* **Restricciones de Recursos:** El efecto más grande que se puede detectar dadas las limitaciones presupuestarias o de tiempo.

## 6.4. Intervalos de Confianza para el ES

Siempre se debe informar un tamaño del efecto junto con una medida de su precisión, como un **Intervalo de Confianza (IC)**.

El IC para el ES cuantifica la incertidumbre de la estimación. Un IC estrecho indica una estimación precisa del tamaño del efecto real.

Si el Intervalo de Confianza:
* **Excluye el cero:** El resultado es estadísticamente significativo al nivel $\alpha$.
* **Incluye el cero:** El resultado no es estadísticamente significativo.

La estimación del ES y su IC proporcionan una imagen mucho más informativa que el solo valor $p$. Esto permite al lector juzgar tanto la magnitud del efecto como la precisión de la estimación. 

## 6.5. Recomendaciones de Reporte

Al reportar los resultados, es una mejor práctica:

* Reportar y discutir siempre los **tamaños del efecto** junto con los valores $p$.
* Incluir el **Intervalo de Confianza** (o Intervalo de Credibilidad) para el tamaño del efecto.
* Utilizar **tamaños del efecto no estandarizados** siempre que las unidades de medida originales sean significativas para la interpretación.
* Utilizar **estimadores de ES menos sesgados** (como $\omega^2$ en lugar de $\eta^2$).
