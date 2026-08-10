---
bibliography: include/book-14.bib
---

# Reproducibilidad computacional {#sec-computationalreproducibility}

> Traducción literal al castellano del capítulo 14, «Computational Reproducibility», de Daniël Lakens, *Improving Your Statistical Inferences*.<br>
> Original: https://lakens.github.io/statistical_inferences/14-computationalreproducibility.html<br>
> Licencia del original: CC-BY-4.0. Traducción no oficial.

La tecnología ha mejorado enormemente la forma en que trabajan los científicos. Internet ha facilitado compartir información —incluidos datos, materiales y código— y han aparecido nuevos programas y plataformas en línea que facilitan el flujo de trabajo científico [@spellman_short_2015]. Un objetivo importante de cualquier flujo de trabajo científico consiste en asegurarse de que el trabajo final que publicamos sea computacionalmente reproducible. **Reproducibilidad computacional** significa que, cuando utilizas los **mismos datos** que en el artículo publicado, puedes reproducir los **mismos resultados**. En otras palabras, si los autores de un artículo publicado te envían sus datos y su código, deberías ser capaz de obtener exactamente los mismos números que aparecen en el artículo. La investigación actual sobre la reproducibilidad computacional de los artículos científicos sugiere que, con frecuencia, no es posible ejecutar el código original sobre los datos y reproducir los resultados [@stodden_empirical_2018; @obels_analysis_2020; @hardwicke_data_2018; @cruwell_whats_2023]. A veces el código simplemente no funciona con los datos o no todos los análisis están incluidos en el código.

Sin embargo, la reproducibilidad computacional es importante tanto para que otros investigadores puedan verificar tus resultados como para que puedan construir sobre ellos. Podemos considerar la reproducibilidad computacional como un estándar mínimo de nuestro propio flujo de trabajo. Pero alcanzar este estándar requiere formación. Cuando yo hacía el doctorado, a menudo sufríamos un problema al que llamábamos «podredumbre de los datos» (*data rot*). Cuando enviaba un artículo para su publicación y recibía las revisiones varios meses después, no siempre podía reproducir fácilmente mis propios análisis. Por ejemplo, quizá no había guardado cómo había tratado los valores atípicos y no podía reproducir exactamente los resultados originales. A veces la «podredumbre de los datos» parecía haberse comido parte de mis datos o de mi código de análisis y este ya no funcionaba.

Obviamente, la «podredumbre de los datos» no existe. El problema era que yo no utilizaba un flujo de trabajo reproducible. En este capítulo aprenderemos cómo es un flujo de trabajo computacionalmente reproducible y cómo puedes compartir resultados computacionalmente reproducibles junto con tu artículo publicado. El objetivo de aplicar un flujo de trabajo computacionalmente reproducible a tus proyectos es permitir que otra persona —o tú mismo dentro de un año— tome tus datos, ejecute tu código y obtenga exactamente los mismos resultados que comunicaste en tu trabajo.

Aunque existen múltiples maneras de alcanzar un flujo de trabajo completamente reproducible, en este capítulo quiero presentarte lo que considero que podría convertirse en uno de los estándares emergentes de la investigación psicológica. Mediante un ejemplo aprenderás a trabajar con un sistema de control de versiones —como [Git](https://git-scm.com) junto con [GitHub](https://github.com), que se integra bien con Open Science Framework— mientras programas en R, de modo que se almacenen las versiones anteriores de tus archivos. Después aprenderás a escribir un script de análisis de datos completamente reproducible —incluidas las figuras— que puedas guardar como archivo HTML o PDF utilizando R Markdown. Finalmente, veremos Code Ocean, una plataforma en línea que permite compartir código computacionalmente reproducible y facilita enormemente que otras personas ejecuten pequeñas variaciones de tu código. No terminarás este capítulo convertido en un programador experimentado, pero verás cómo es un flujo de trabajo plenamente reproducible y adquirirás una primera experiencia con herramientas que probablemente querrás explorar con mayor profundidad en el futuro.

Conseguir que el software y el código funcionen en tu sistema puede ser un reto y, lamentablemente, no puedo ofrecer soporte informático. Las diferencias entre Windows, Linux y los sistemas operativos de Apple hacen que en ocasiones tengas que buscar en internet soluciones a los problemas que aparezcan. Esto es completamente normal y los programadores experimentados también lo hacen continuamente. Si te atascas, puedes comparar lo que has hecho con las versiones públicas de distintas partes de este ejemplo:

Repositorio de GitHub: <https://github.com/Lakens/reproducibility_assignment>

Proyecto de OSF: <https://osf.io/jky8s/>

Contenedor de Code Ocean: <https://codeocean.com/capsule/2529779/tree/v1>

## Paso 1: configurar un repositorio de GitHub

En este ejercicio utilizaremos GitHub, aunque una alternativa de código abierto es [GitLab](https://www.gitlab.com). Si todavía no tienes una cuenta de GitHub, créala ahora. Ve a <https://github.com/> y crea una cuenta. Git es un sistema de control de versiones que permite hacer seguimiento de los cambios en archivos informáticos y coordinar el trabajo sobre esos archivos entre varias personas. El control de versiones permite registrar los cambios y volver a versiones anteriores cuando sea necesario. GitHub y GitLab son servicios web que facilitan el uso del control de versiones mediante Git. Utilizaremos GitHub porque es el servicio con el que estoy más familiarizado y porque se integra con algo más de herramientas, pero puedes utilizar GitLab si lo prefieres.

Si ya tienes una cuenta, puedes crear un nuevo repositorio. Un **repositorio** es una colección de carpetas y archivos que componen un proyecto. En la esquina superior derecha de la página de GitHub, haz clic en el símbolo `+` y selecciona «New repository» en el menú desplegable.

![](https://lakens.github.io/statistical_inferences/images/7a1725550cadb293b13fe058631a24ba.png)

Lo primero que debes hacer es poner nombre al repositorio. A la hora de nombrar carpetas y archivos conviene seguir algunas **buenas prácticas para la denominación de archivos**:

- Mantén los nombres cortos, pero claros. `data_analysis_project` resulta más comprensible para otras personas que `dat_an_prjct`.
- No utilices espacios. Algunas posibilidades son:
  - Guion bajo: `this_is_a_file.R` —esta es mi opción preferida—.
  - *CamelCase*: `ThisIsAFile.R`.
  - Guiones: `this-is-a-file.R`.
  - Sin espacios: `thisisafile.R`.
- Si quieres numerar varios archivos secuenciales, no uses `1_start`, `2_end`, sino ceros iniciales siempre que puedas llegar a más de diez archivos: por ejemplo `01`, `02`, etc., o `001`, `002`, etc.
- No utilices caracteres especiales como `$#&*{}:` en los nombres de archivo.
- Si quieres incorporar una fecha al nombre, utiliza el formato `AAAAMMDD`.

Llamemos a nuestro repositorio `reproducibility_assignment`.

![](https://lakens.github.io/statistical_inferences/images/5cddb5d5a5ef1b470b5d160857a71719.png)

Puedes añadir una breve descripción, por ejemplo: «This is an assignment to practice an open and reproducible data analysis workflow». Si eres estudiante o académico, puedes obtener una [cuenta académica](https://education.github.com/pack), que proporciona algunas opciones adicionales, como mantener repositorios privados.

Marca la casilla «Initialize this repository with a README». Un archivo README es una forma útil de proporcionar una descripción más detallada del proyecto, que será visible cuando otras personas visiten la página del repositorio. También puede contener instrucciones sobre cómo reproducir los análisis, por ejemplo qué archivos deben ejecutarse y en qué orden, así como los cambios que deban realizarse a medida que se ejecutan.

También se te pregunta si quieres añadir una **licencia**. Añadir una licencia es una forma sencilla de comunicar a otras personas cómo pueden utilizar los datos, el código y los materiales que compartirás en el repositorio de GitHub. Ten en cuenta que no elegir una licencia también es una elección: si no añades ninguna, tu trabajo queda protegido por derechos de autor exclusivos de manera predeterminada y otras personas no pueden reutilizarlo fácilmente. Puedes [informarte sobre las licencias](https://choosealicense.com/), pero por ahora una opción sencilla es la licencia MIT, que establece muy pocas restricciones a la reutilización, aunque existen licencias más restrictivas. Puedes seleccionar la licencia MIT en el menú desplegable. Esta permite que otras personas hagan prácticamente lo que quieran con tu código siempre que te atribuyan la autoría y no te hagan responsable de su uso. También existen [licencias Creative Commons](https://creativecommons.org/choose/) que puedes utilizar cuando compartes algo distinto de software, como materiales de investigación. Por ejemplo, este material educativo se comparte con una licencia [CC-BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0).

Ya estamos preparados para crear el repositorio. Haz clic en:

![](https://lakens.github.io/statistical_inferences/images/ccb66558822a17c4a3ec6511c9bf5a7b.png){width=20%}

Puede resultar poco intuitivo, pero es importante recordar que no se espera que interactúes directamente con tu nuevo repositorio a través de la página web de GitHub. La página del repositorio proporciona información sobre su contenido y sobre el historial de sus archivos, pero no es especialmente cómoda para añadir o descargar archivos directamente. La idea es utilizar otro software para interactuar con tu repositorio de GitHub.

## Paso 2: clonar el repositorio de GitHub en RStudio

RStudio puede comunicarse con GitHub. Para que ambos trabajen conjuntamente, primero debemos configurar el sistema. [Aquí](https://support.rstudio.com/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN) encontrarás una explicación detallada para distintos sistemas operativos. En primer lugar, descarga [Git](https://git-scm.com/downloads) para tu sistema operativo e instálalo —puedes aceptar todas las opciones predeterminadas durante la instalación—. Si aún no lo has hecho, descarga e instala [R](https://cran.r-project.org/) y descarga e instala la versión gratuita de [RStudio](https://www.rstudio.com/products/rstudio/download/).

En RStudio, ve a `Tools > Global Options` y selecciona la opción `Git/SVN`.

![](https://lakens.github.io/statistical_inferences/images/cfc1e6fc415fb90fad16f4856338b890.png)

Comprueba si el ejecutable de Git —`git.exe`— se ha encontrado automáticamente. Si no es así, tendrás que pulsar «Browse…» y localizarlo manualmente. Estará en la ubicación donde hayas instalado Git.

Pulsa el botón «Create SSH Key…». Aparecerá una ventana. En *SSH key type* selecciona `ED25519` y, si quieres, añade una contraseña segura que no vayas a olvidar.

![](https://lakens.github.io/statistical_inferences/images/afd9d82e34e9fbff7e9d83c9b89e29c0.png)

Puedes cerrar la ventana. Todavía dentro de las opciones de RStudio, haz clic en el enlace azul «View public key». Aparecerá una ventana que te indica que puedes utilizar `CTRL+C` para copiar la clave. Hazlo.

Ve a GitHub, abre la configuración y selecciona la opción «SSH and GPG keys».

![](https://lakens.github.io/statistical_inferences/images/e2c7d8cad7b8127e20ad6caf6d2b84ea.png){width=50%}

![](https://lakens.github.io/statistical_inferences/images/e949d47fdc97cef38499f82cb70f7e11.png){width=50%}

Haz clic en «New SSH key».

![](https://lakens.github.io/statistical_inferences/images/02ee9504ceacd79b3706f18e8497ed43.png)

Introduce un nombre —por ejemplo, `RStudio`— y pega la clave en el campo correspondiente. Haz clic en «Add SSH Key». Esto permitirá enviar código desde RStudio a tus repositorios de GitHub sin tener que introducir el nombre de usuario y la contraseña de GitHub cada vez. En otras palabras, RStudio ya está conectado con tu cuenta de GitHub y estás preparado para crear un **proyecto con control de versiones**.

**Reinicia RStudio**. En RStudio, ve a `File > New Project`.

![](https://lakens.github.io/statistical_inferences/images/7549d0317ad5f80afe7f3c6be4ad0ba3.png)

Aparecen tres opciones. Selecciona «Version Control».

![](https://lakens.github.io/statistical_inferences/images/5eff851f02909023dac665978c716a9d.png)

Selecciona «Git».

![](https://lakens.github.io/statistical_inferences/images/a37a25fa7b6b9534d8f16154ce417be6.png)

Vamos a clonar el repositorio de GitHub que hemos creado. **Clonar** es un término de Git que significa crear en tu ordenador una copia local de todos los archivos del repositorio. Puedes copiar y pegar la URL del repositorio de GitHub, por ejemplo <https://github.com/Lakens/reproducibility_assignment>. Si pegas esta URL en el campo superior, se creará automáticamente un nombre para el directorio del proyecto similar al que utilizaste en GitHub. Puedes seleccionar una carpeta de tu ordenador mediante el botón «Browse» para indicar dónde quieres guardar la copia local del repositorio.

![](https://lakens.github.io/statistical_inferences/images/085ad47bd94f834aca501b87baa7c0eb.png)

Haz clic en «Create Project». R descargará rápidamente los archivos del repositorio y abrirá el nuevo proyecto. Sabrás que la creación ha funcionado porque la pestaña «Files» de RStudio mostrará algunos de los archivos descargados desde GitHub —`README.md` y `LICENSE`—. RStudio también habrá creado un archivo `.Rproj` y un archivo `.gitignore`. El **archivo de proyecto** almacena información sobre el proyecto y es necesario para trabajar con GitHub.

![](https://lakens.github.io/statistical_inferences/images/386831c4f089bbb56758718619859308.png)

También podemos ver que se trata de un proyecto con control de versiones porque en la parte superior derecha de la interfaz aparece ahora una pestaña «Git». Si hacemos clic en ella veremos:

![](https://lakens.github.io/statistical_inferences/images/16361987bd66eec35a5b82b2efb9617b.png)

Aparecen varios botones, como `Diff`, `Commit`, `Pull` y `Push`. Los utilizaremos para interactuar con GitHub. Muchos programadores trabajan con Git desde la línea de comandos, por ejemplo:

```bash
git commit -m "This is a git commit message"
```

Aprender a utilizar Git desde la línea de comandos no es necesario para la mayoría de las personas que solo necesitan un control de versiones básico. Aquí me centraré exclusivamente en utilizar el control de versiones y Git mediante las opciones de los menús de RStudio. Es el momento de crear un archivo cuyas distintas versiones queramos controlar.

## Paso 3: crear un archivo R Markdown

Los archivos R Markdown permiten guardar y ejecutar código y, al mismo tiempo, crear informes del análisis de datos —¡e incluso artículos científicos completos que puedes enviar para su publicación!—. Hay una [introducción completa a R Markdown](https://rmarkdown.rstudio.com/lesson-1.html). La principal fortaleza de los documentos R Markdown es que permiten crear documentos completamente reproducibles. Esto significa que no tienes simplemente código de análisis en un script de R, sino un manuscrito que combina texto y código y que puedes **compilar** para crear una versión del manuscrito en PDF o HTML. Los archivos HTML o PDF tienen la ventaja de que cualquier persona puede leerlos con programas habituales. El archivo R Markdown contiene código que realiza los análisis **cada vez que se compila el documento**. En lugar de copiar y pegar valores desde tu programa de análisis a un documento de Word, combinas código y texto en el archivo R Markdown para crear un manuscrito en el que cada número o figura puede rastrearse hasta el código exacto que lo generó. La ventaja es que cualquier persona puede utilizar tu archivo R Markdown y generar el mismo documento —por ejemplo, tu manuscrito— que tú.

Puedes seguir cometiendo errores en los análisis aunque utilices R Markdown. La diferencia importante es que serán errores de programación que quedarán almacenados en el propio documento. Frente a un error tipográfico al copiar números desde un programa de análisis a Word, un error en el análisis dentro de R Markdown producirá siempre el mismo documento. Como el documento es reproducible, **todos los errores también serán reproducibles**. Es imposible evitar todos los errores, pero sí podemos hacer que sean reproducibles, lo que facilita identificarlos y corregirlos. Entiendo que pueda preocupar que otras personas vean tus errores si les permites comprobar exactamente lo que has hecho. Pero **todos cometemos errores**, y para la ciencia es importante poder identificarlos y corregirlos. Un aspecto esencial de avanzar hacia un flujo de trabajo más reproducible y compartir públicamente todos los archivos que sustentan un manuscrito consiste en aprender a **aceptar que todos cometemos errores** y valorar a quienes los corrigen [@bishop_fallibility_2018].

Comencemos creando un nuevo documento R Markdown en RStudio mediante `New File > R Markdown…`.

![](https://lakens.github.io/statistical_inferences/images/f13fad91521fb984d12577416fa1fa99.png)

Se abrirá una ventana en la que puedes especificar el título del documento R Markdown y el nombre del autor. Introduce el título «Main Analysis» y cambia el campo de autor si lo deseas. Los archivos R Markdown pueden compilarse —también se habla de *knit* o «tejer»— como un archivo HTML, un documento PDF o un documento de Word. Para generar PDF es necesario instalar MiKTeX, cosa que no haremos en este ejemplo. Existe [un buen tutorial para instalar MiKTeX](https://medium.com/%40sorenlind/create-pdf-reports-using-r-r-markdown-latex-and-knitr-on-windows-10-952b0c48bfa9). Mantén, por tanto, HTML como formato de salida predeterminado y pulsa `OK`.

![](https://lakens.github.io/statistical_inferences/images/be373a55333121dee2669025ba9fff3d.png)

Empecemos guardando el nuevo archivo. Pulsa el botón de guardar y guárdalo con el nombre `main_analysis.Rmd`. Como estamos trabajando dentro de un proyecto de RStudio, el archivo se guardará automáticamente en la misma carpeta que el resto de archivos del proyecto. Si miras la pestaña «Files» del panel inferior derecho, verás aparecer el nuevo archivo. Veamos ahora cómo es un archivo R Markdown.

Por defecto, el documento incluye varias secciones para ayudarte a comenzar. Primero aparece una cabecera. En ella hay código que determina cómo se renderiza el documento final. Es una sección delicada, porque tiene que escribirse exactamente bien —incluidos espacios y tabulaciones—, por lo que no es recomendable modificarla demasiado sin consultar documentación específica. Si quieres conocer los detalles técnicos: un archivo R Markdown se pasa al programa `knitr`, que crea un archivo Markdown normal; después `pandoc` genera el tipo de documento que has solicitado. Todo esto ocurre automáticamente.

![](https://lakens.github.io/statistical_inferences/images/fd284f329222582a56ecb4906f99afee.png)

A la cabecera le sigue una sección de **configuración** en la que puedes definir opciones generales para todo el archivo R Markdown. Después aparecen los dos componentes principales: **código Markdown**, un lenguaje de marcado con sintaxis de texto plano que puede convertirse fácilmente a HTML u otros formatos, y **código R**, utilizado para analizar datos o crear figuras. Para ver el resultado final pulsa:

![](https://lakens.github.io/statistical_inferences/images/270645a5be86fa1d9d534f78b8ca0724.png){width=20%}

el botón `Knit` de la barra de herramientas situada en la parte superior del panel.

Se abrirá una nueva ventana que permite ver el archivo HTML creado o el documento aparecerá en la pestaña «Viewer» de RStudio. Verás un documento HTML con formato que combina texto y la salida del código de R.

![](https://lakens.github.io/statistical_inferences/images/9405a78d629bc5abd36ba8b31c42cfd9.png)

Cierra la ventana. Ya estamos preparados para analizar los datos.

## Paso 4: análisis de datos reproducible en RStudio

Borra todo el texto desde `## R Markdown` hacia abajo. Conserva únicamente la cabecera y las secciones de configuración del documento predeterminado.

Primero necesitamos analizar algunos datos. Los descargaremos directamente desde un repositorio de GitHub que he creado. Estudiantes de un curso de introducción a la psicología realizaron un sencillo experimento Stroop. En el experimento, los participantes nombraban los colores en un ensayo congruente —por ejemplo, la palabra «rojo» escrita en color rojo— y en un ensayo incongruente —por ejemplo, la palabra «rojo» escrita en verde—. Se registró en segundos el tiempo empleado en nombrar todas las palabras —por ejemplo, 21,3 segundos— tanto en el ensayo congruente como en el incongruente. El conjunto de datos contiene cuatro columnas:

- Número de participante.
- Tiempo de respuesta para estímulos congruentes.
- Tiempo de respuesta para estímulos incongruentes.
- Año de recogida de datos.

Pulsa el botón `+C Insert` para insertar código. Aparecerá un menú desplegable. Selecciona `R`.

![](https://lakens.github.io/statistical_inferences/images/2f929ee323a9f222c85675f5fc45672f.png){width=50%}

En el archivo R Markdown aparecerá una nueva sección de código R que empieza con tres acentos graves seguidos de `{r}` y termina con otros tres acentos graves. También puedes crear estas secciones escribiendo manualmente ambas líneas.

Copia y pega el siguiente código —asegúrate de copiarlo completo— entre la línea inicial y final del bloque de código R:

```r
stroop_data <- read.table(
  "https://raw.githubusercontent.com/Lakens/Stroop/master/stroop.txt",
  sep = "\t", header = TRUE
)

write.table(stroop_data, file = "stroop.csv", quote = FALSE, row.names = FALSE)
```

Después de pegar el texto, la sección de código debería tener este aspecto:

![](https://lakens.github.io/statistical_inferences/images/6d87836ecdcc9b06891059acc43930a2.png)

Este código crea un `data.frame` llamado `stroop_data` que contiene los datos y, a continuación, los guarda en un archivo `.csv` llamado `stroop.csv`. Pulsa el botón `Knit` para ver el documento:

![](https://lakens.github.io/statistical_inferences/images/270645a5be86fa1d9d534f78b8ca0724.png){width=20%}

Deberías ver algo parecido a esto:

![](https://lakens.github.io/statistical_inferences/images/5bad7d8cde23291c2d67ff65897d60c4.png)

Quizá no parezca muy impresionante, pero lo importante está en el panel de archivos de la parte inferior derecha. Cierra la ventana que muestra la salida HTML y mira ese panel. Deberías ver varios archivos:

![](https://lakens.github.io/statistical_inferences/images/0ba38e2b99fd3e1a10f943d1ab45f156.png)

Uno de ellos es `stroop.csv`: nuestro archivo con los datos de Stroop, que hemos descargado de internet y guardado en la carpeta del proyecto mediante código R.

No necesitamos seguir descargando el archivo de internet si ya podemos cargarlo desde la carpeta local. Modifiquemos el código. No lo borraremos por completo; simplemente lo **comentaremos** colocando `#` delante de cada línea. De este modo podremos recordar de dónde descargamos el archivo, pero el código no se ejecutará.

Como siempre es importante **añadir comentarios al código**, escribe esta explicación encima de la línea utilizada para descargar los datos:

```r
# ejecutar solo una vez para descargar los datos
```

Selecciona después las líneas del bloque y pulsa `CTRL+SHIFT+C` en Windows —o abre `Code` en la barra de herramientas y selecciona `comment/uncomment lines`—. Esto añadirá `#` delante de cada línea, convirtiéndola en un comentario que no se ejecutará. Deberías terminar con algo parecido a esto:

![](https://lakens.github.io/statistical_inferences/images/0061d311bf4819c08afde5f9b110f9b6.png)

Ahora debemos añadir una línea de código que sí se ejecutará y que cargará el conjunto `stroop.csv` desde la carpeta local. Debajo de la última línea comentada, pero dentro del bloque de código R, añade:

```r
stroop_data <- read.csv("stroop.csv", sep = " ", header = TRUE)
```

![](https://lakens.github.io/statistical_inferences/images/f14461f73699f865e4850e99990606f2.png)

Haz clic en guardar o pulsa `CTRL+S`. Compila el archivo con `Knit`. Verás:

![](https://lakens.github.io/statistical_inferences/images/f860eea02424968a1c0ca4afc5b583df.png)

Cierra el archivo HTML. Hemos hecho bastante trabajo y sería una pena perderlo. Es un buen momento para guardar una versión de nuestro archivo R Markdown no solo localmente, sino también en GitHub.

## Paso 5: hacer *commit* y *push* a GitHub

Es hora de almacenar los cambios en la nube, en GitHub. El proceso consta de dos pasos. Primero registramos los cambios realizados en el repositorio —el código y los archivos que hemos creado—, lo que se denomina **commit**. Esto no requiere conexión a internet, porque simplemente estamos registrando los cambios localmente. Después debemos asegurarnos de que esos cambios registrados también se almacenan en GitHub, para lo cual hacemos **push** de los archivos.

Si miramos la pestaña `Git` del panel superior derecho de RStudio, veremos los botones `Commit` y `Push`, además de varios archivos. El estado de estos archivos se indica mediante dos signos de interrogación amarillos. Significan que esos archivos todavía no están siendo seguidos por Git. Vamos a cambiarlo.

![](https://lakens.github.io/statistical_inferences/images/ca36fd42cb6d9189534590e5cfcb9411.png)

Haz clic en el botón `Commit`. Se abrirá un menú. Puedes elegir qué cambios quieres **preparar** —*stage*—, es decir, qué archivos quieres registrar en el *commit*. Puedes hacerlo de varias formas: haciendo doble clic sobre cada archivo o seleccionándolos todos y pulsando `Enter`. Al preparar todos los archivos, los signos de interrogación amarillos cambian por una `A` verde. Todo *commit* debe ir acompañado de un **mensaje de commit** que describa los cambios realizados. Puedes escribir lo que quieras; la primera vez es frecuente utilizar algo como `initial commit`. El menú debería parecerse a esta captura:

![](https://lakens.github.io/statistical_inferences/images/df26ee077662dda7148be10da4c410e8.png)

Ya estamos preparados para hacer **commit** de los cambios. Pulsa el botón `Commit`. Se abrirá una nueva ventana que muestra los cambios registrados. Veremos que se han modificado cinco archivos. Puedes cerrar esta ventana y el menú anterior.

![](https://lakens.github.io/statistical_inferences/images/bd217abdabf5cc4e81637d8d0eb7db9e.png)

RStudio nos recuerda ahora que existe una diferencia entre la copia local del repositorio y la versión remota en GitHub. En la pestaña Git aparece el aviso: `Your branch is ahead of 'origin/master' by 1 commit.`

![](https://lakens.github.io/statistical_inferences/images/b3c606d72795bf88e1b7a04dbce381bb.png)

Esto significa que los archivos actualizados y registrados mediante un *commit* en nuestro ordenador aún no están sincronizados con el **repositorio remoto** de GitHub. Podemos solucionarlo haciendo *push* —es decir, sincronizando— los cambios con el repositorio remoto. Pulsa simplemente el botón **Push**:

![](https://lakens.github.io/statistical_inferences/images/7a363782af473d6da3e79f3a088d527b.png){width=20%}

Aparecerá otra ventana:

![](https://lakens.github.io/statistical_inferences/images/8b77f09c9c2cad752ec90ecdfa42e566.png)

Esta ventana nos informa de que no se produjeron errores y de que los cambios se enviaron correctamente al repositorio remoto. Puedes cerrarla.

Puedes comprobar que todos los archivos se han enviado correctamente visitando en el navegador la página de GitHub de tu repositorio. Deberías ver algo parecido a esto:

![](https://lakens.github.io/statistical_inferences/images/9eb79724ec82b5a99d62938388c43d3a.png)

¡Enhorabuena por tu primer *push* a GitHub! Si quieres una introducción más extensa a Git, consulta Vuorre y Curley [-@vuorre_curating_2018].

## Paso 6: análisis de datos reproducible

Hasta ahora solo hemos leído los datos. El objetivo de un archivo R Markdown es crear un manuscrito que contenga un **análisis de datos completamente reproducible**. En este capítulo no puedo enseñarte a analizar datos en R —aunque recomiendo encarecidamente aprenderlo; existen muchos recursos excelentes en línea—. En lugar de programar desde cero, visita [esta versión en texto plano del archivo R Markdown](https://raw.githubusercontent.com/Lakens/reproducibility_assignment/master/main_analysis.Rmd), que analiza los datos del Stroop. En la página web, selecciona todo el texto (`CTRL+A`) y cópialo (`CTRL+C`). Después abre `main_analysis.Rmd` en RStudio, selecciona todo (`CTRL+A`) y pulsa borrar. Sí: borra todo. No debes preocuparte por perder nada, porque tienes un **archivo bajo control de versiones** en tu repositorio de GitHub y siempre puedes volver a una versión anterior. En el archivo `main_analysis.Rmd`, ahora vacío, pulsa `CTRL+V` y pega todo el texto. Debería tener el aspecto de la primera captura siguiente.

Este archivo R Markdown hace varias cosas que explicaremos con detalle. Por ejemplo, instala automáticamente las bibliotecas que necesita, carga los datos y crea un informe en HTML. Puedes pulsar `Knit` y se cargará el documento HTML. Deberías ver una salida similar a la de las dos capturas siguientes.

![](https://lakens.github.io/statistical_inferences/images/23a19f01f3a23b3673656ee78860caf5.png)

![](https://lakens.github.io/statistical_inferences/images/79166b6bcc909e9e9e7fb0dd365fc8b2.png)

![](https://lakens.github.io/statistical_inferences/images/dc72012da17d44752af4ab572c6c20d2.png)

Es importante observar que ninguno de los números que aparecen en este texto es estático ni se ha copiado y pegado. Todos se calculan en el momento en que se crea el documento, directamente a partir de los datos brutos. Lo mismo ocurre con las figuras, que se generan a partir de esos datos cuando se compila el manuscrito. Si tienes acceso al archivo `.Rmd` —R Markdown— puedes **reproducir** perfectamente el análisis comunicado.

Como hemos realizado cambios importantes, este es un momento perfecto para hacer **commit** y **push** a GitHub. Ve a la pestaña Git de la parte superior derecha y pulsa `Commit`. Se abrirá la ventana siguiente. Si seleccionas `main_analysis.Rmd`, verás bloques de texto rojos y verdes que indican qué contenido era antiguo —rojo— y cuál es nuevo —verde—.

![](https://lakens.github.io/statistical_inferences/images/045aa0f44f3615a30aeaac241042fa3a.png)

Selecciona todos los archivos que hayan cambiado y prepáralos —*stage*—, por ejemplo pulsando `Enter`. Las casillas delante de los archivos, bajo la columna `Staged`, deberían quedar marcadas.

![](https://lakens.github.io/statistical_inferences/images/3d314b695f0d424b8792e4d179f6f4d3.png)

Escribe un mensaje como `update mean analysis` en el campo `commit message`. Pulsa `Commit`. Cierra la ventana emergente que informa del resultado del *commit*. Después pulsa `Push`. Cierra la ventana que informa del resultado del *push* y cierra la ventana de *commit*. Siempre puedes visitar el repositorio de GitHub en línea y consultar el historial completo del documento para ver todos los cambios que se han realizado.

Veamos algunas secciones del nuevo documento R Markdown. Primero, la cabecera:

![](https://lakens.github.io/statistical_inferences/images/5be3bc1c3f5a2ebf2d16d19430312057.png)

Aquí se establecen opciones generales —globales— para los bloques de código del archivo R Markdown. `echo`, `warning` y `message = FALSE` ocultan los bloques de código, las advertencias y otros mensajes, mientras que `include = TRUE` hace que todas las figuras aparezcan en el texto. Puedes cambiar algunas variables a `TRUE` y pulsar `Knit` para ver qué sucede. A veces querrás compartir el archivo HTML con todo el código visible, por ejemplo cuando trabajas con colaboradores.

Si te desplazas hacia abajo, verás el texto de la introducción, el código que genera la primera figura y el código que realiza los análisis. Las variables que se calculan allí se utilizan en la sección de Resultados. Observemos esa sección:

![](https://lakens.github.io/statistical_inferences/images/aab442e8c104cb1444a88b7a3a987de5.png)

Esta sección muestra cómo **mezclar texto y código R**. El comienzo es texto normal. `*M*` sigue siendo texto normal —los asteriscos hacen que la M aparezca en cursiva; del mismo modo, `~av~` convierte esas letras en subíndice—, pero después aparece código de R. En R Markdown puedes insertar código R en línea utilizando `` `r ...` ``. Todo el código que aparezca entre esos acentos graves se ejecutará. En este caso se calcula la media de los tiempos de reacción de la condición congruente y se redondea a dos decimales. Puedes ver el número resultante directamente en el texto.

Aprender a programar requiere tiempo. Algunas cosas son bastante complicadas de programar. Por ejemplo, el código:

```r
ifelse(ttest_result$p.value > 0.001, " = ", " < ")
ifelse(
  ttest_result$p.value > 0.001,
  formatC(round(ttest_result$p.value, digits = 3), digits = 3, format = "f"),
  "0.001"
)
```

es bastante largo para conseguir que se comunique el valor *p* exacto salvo cuando es inferior a 0,001, en cuyo caso se imprime `p < 0.001` —el paquete `papaja`, que veremos a continuación, facilita mucho la comunicación de estadísticos—. La primera vez que programas algo así lleva bastante tiempo, pero recuerda que después puedes reutilizar el código y que puedes aprovechar mucho código de otras personas. Puedes completar una [introducción a R Markdown](https://rmarkdown.rstudio.com/articles_intro.html).

### Extra: manuscritos con formato APA mediante `papaja`

Si quieres escribir un manuscrito reproducible con **formato APA** —habitual, por ejemplo, en psicología— quizá quieras probar el paquete de R [papaja](https://github.com/crsh/papaja), creado por Frederik Aust. Instala el paquete `papaja` y **reinicia RStudio**. Después crea un nuevo documento R Markdown, pero, en lugar de seleccionar la opción de documento, elige `From Template` y selecciona la plantilla `APA article (6th edition)` proporcionada por `papaja`.

![](https://lakens.github.io/statistical_inferences/images/b4edc7f85821527cd6f98a1c76dfc47d.png)

Verás una plantilla con numerosos campos que debes completar, como el título, los nombres de los autores y sus afiliaciones, la nota de autor, el resumen, etc. `papaja` se ocupa de que toda esa información termine con una presentación adecuada que sigue las normas APA. Esto significa que, si tienes instalado MiKTeX —necesario para convertir a PDF—, puedes compilar el documento a PDF y enviar un manuscrito con formato APA completamente reproducible. Hay un [tutorial de `papaja`](https://crsh.github.io/papaja_man/index.html) que cubre todas sus opciones, incluida la incorporación de citas.

![](https://lakens.github.io/statistical_inferences/images/50d0fc917605c24a8839a66437f9c18b.png)

## Paso 7: organizar tus datos y tu código

Es importante **organizar siempre los archivos de datos y de análisis**. Esto ayuda a otras personas a localizar rápidamente lo que necesitan. En general, recomiendo el [**protocolo TIER**](https://www.projecttier.org/tier-protocol/). Si compartes un archivo de datos algo mayor que el de este ejemplo, asegúrate de añadir un libro de códigos para que los demás entiendan qué significa cada variable. Para generar automáticamente un libro de códigos legible por máquinas puede resultar útil el paquete descrito por Arslan [-@arslan_how_2019].

Cuando organices el código, **presta mucha atención a que cualquier información personalmente identificable de los datos se almacene de manera segura**. La ciencia abierta es estupenda, pero eres responsable de compartir los datos de forma responsable. Esto significa que debes **pedir permiso a los participantes para compartir sus datos** en el consentimiento informado. La página de Research Data Management Support de la Universidad de Utrecht ofrece un [recurso útil sobre consentimiento para compartir datos](https://www.uu.nl/en/research/research-data-management/guides/informed-consent-for-data-sharing). Siempre que recojas datos personales, asegúrate de [tratarlos de manera responsable](https://www.uu.nl/en/research/research-data-management/guides/handling-personal-data). El personal especializado en información de la biblioteca de tu universidad debería poder ayudarte.

## Paso 8: archivar tus datos y tu código

Aunque hemos subido nuestros datos y código a GitHub, cuando publiques un artículo y quieras **compartir los datos y el código** debes recordar que GitHub no es un repositorio de datos que garantice el almacenamiento a largo plazo. GitHub pertenece actualmente a Microsoft y una empresa puede cambiar las condiciones de un servicio gratuito. Esto hace que GitHub sea menos adecuado como enlace único en los artículos científicos, porque esos artículos podrían seguir consultándose dentro de varias décadas. Para publicaciones científicas conviene enlazar a un repositorio estable de almacenamiento a largo plazo. Puedes consultar una [lista de repositorios de datos](http://journals.plos.org/plosone/s/data-availability#loc-recommended-repositories). En este ejemplo utilizaremos Open Science Framework (OSF) como almacenamiento estable, porque resulta muy sencillo integrar en un proyecto de OSF nuestro repositorio de GitHub.

Inicia sesión en [OSF](https://osf.io/) —crea una cuenta si todavía no tienes una—. Haz clic en `Create new project`. Ponle un nombre al proyecto, por ejemplo `Stroop Reproducible Analysis Assignment`.

También en OSF es importante añadir una **licencia** a tu trabajo. Después de crear el proyecto puedes hacer clic en `Add a license`.

![](https://lakens.github.io/statistical_inferences/images/372c6ba890617ecf396d540bed85698c.png)

Puedes volver a elegir una licencia MIT. Tendrás que indicar un año y los titulares de los derechos de autor —en este caso eres tú, así que escribe tu nombre; aparecerá en el texto de la licencia—. Después pulsa:

![](https://lakens.github.io/statistical_inferences/images/e137b9bdf5f301150dc3c06b6f3eb5ca.png){width=20%}

Aunque podríamos subir todos nuestros archivos a OSF, también podemos simplemente enlazar el proyecto de GitHub con OSF. En la barra de menú del proyecto de OSF, haz clic en `Add-ons`. Desplázate por la lista hasta `GitHub`.

![](https://lakens.github.io/statistical_inferences/images/e25382896d7b290ad6649a6f2d5c13a2.png)

Sigue la [guía paso a paso de OSF para conectar GitHub](https://help.osf.io/hc/en-us/articles/360019929813-Connect-GitHub-to-a-Project).

Selecciona el repositorio que contiene el ejercicio de reproducibilidad y haz clic en `Save`.

![](https://lakens.github.io/statistical_inferences/images/7570fb87913b1d687a9b8a3a72948e24.png)

Haz clic en el título de la página del proyecto de OSF para volver a la página principal. En el panel `Files` verás ahora que el repositorio de GitHub está enlazado.

![](https://lakens.github.io/statistical_inferences/images/4ecc8e0af472a95a3f01baf3af0538cf.png)

Es un buen momento para hacer clic en `Make Public`, en la esquina superior derecha del proyecto. Después de hacerlo, otras personas podrán encontrarlo en OSF. Si todavía no quieres hacerlo público pero necesitas proporcionar acceso a los archivos, puedes crear un enlace de **solo lectura** —`View-only`—. Ve a `Contributors` y pulsa `+Add` junto a `View-only links`. Existe un [tutorial paso a paso](https://help.osf.io/hc/en-us/articles/360019930333-Create-a-View-only-Link-for-a-Project).

![](https://lakens.github.io/statistical_inferences/images/fd54022300a51d07de93673aac3fb508.png)

Puedes utilizar un enlace de solo lectura para proporcionar acceso exclusivamente a los revisores. También puedes crear un enlace anonimizado para ocultar los nombres de los colaboradores del proyecto, algo especialmente útil en una **revisión por pares ciega**. Dar acceso a los archivos durante la revisión facilita mucho el trabajo de los revisores, que podrán resolver con mayor facilidad cualquier pregunta sobre tus materiales, datos o código. Ten presente que esto significa que personas que no conoces tendrán acceso a tus archivos. Hasta ahora no conozco experiencias negativas relacionadas con este proceso, pero conviene ser consciente de que otras personas pueden acceder a los archivos antes de que se publiquen.

La página de OSF, en este momento, únicamente enlaza a los archivos de GitHub; no los almacena de forma independiente. Por tanto, todavía no tenemos una **solución estable de almacenamiento a largo plazo**.

Para crear una instantánea de todos los archivos del repositorio de GitHub que se conserve a largo plazo debes crear un **Registration** del proyecto. **No crearemos un registro de este proyecto en el ejemplo. Crear un registro inicia varios procedimientos formales: los datos de repositorios enlazados —como GitHub— son almacenados por OSF y el proyecto aparece en la lista de registros. Solo debes registrarlo cuando quieras crear una copia estable de tu trabajo.** A continuación puedes ver un ejemplo de los archivos de un proyecto de OSF que se ha registrado. El repositorio de GitHub enlazado se ha convertido en un `Archive of GitHub`, lo que crea una versión estable del proyecto tal como existía en el momento del registro.

![](https://lakens.github.io/statistical_inferences/images/e0b28289fbe42988cbe04111e4aee6ad.png)

Un buen momento para crear una versión estable del proyecto es cuando el manuscrito ha sido aceptado para su publicación. Puedes crear un `Registration` y utilizar su identificador digital de objetos (**DOI**) para enlazar al código, los datos y los materiales desde el artículo —puedes añadir este DOI al manuscrito cuando revises las pruebas antes de la publicación—. Se recomienda enlazar los materiales mediante el **DOI**. Un DOI es un enlace persistente, es decir, seguirá funcionando aunque cambie la dirección de una página web. Crear un registro no genera un DOI automáticamente. Después de crear el `Registration`, debes hacer clic en `Create DOI` para crear el identificador persistente.

![](https://lakens.github.io/statistical_inferences/images/502f57cf747457838ed0a0e2c5af0496.png)

Si estás preparado para crear un registro, sigue las [instrucciones de OSF](https://help.osf.io/article/158-create-a-preregistration). Como ejemplo de un registro creado para almacenar todo el trabajo relacionado con una de mis publicaciones científicas, puedes consultar <https://doi.org/10.17605/OSF.IO/9Z6WB>. Este enlace es también un ejemplo de cómo enlazar un proyecto de OSF mediante un DOI.

### Extra: compartir código reproducible en Code Ocean

Si has utilizado el flujo de trabajo anterior para crear un manuscrito reproducible, quizá quieras facilitar que otras personas exploren tus datos y código. Pueden clonar tu repositorio de GitHub, pero eso exige instalar el software que utilizaste y, aunque ya tengan R, instalar también los paquetes necesarios para analizar los datos. Esto puede generar problemas de reproducibilidad. Los paquetes de R se actualizan y cambian con el tiempo, y un código que funciona en un ordenador quizá no funcione correctamente en otro. Además, incluso cuando todo se comparte perfectamente, descargar todos los archivos y poner en marcha el código lleva tiempo. Existen varias soluciones, como `renv` o `Groundhog`, que gestionan dependencias en R, o [Docker](http://www.docker.com), que permite crear un contenedor que funciona como una máquina virtual e incorpora el entorno de computación, las bibliotecas, el código y los datos necesarios para reproducir un análisis [@wiebels_leveraging_2021].

Aquí me centraré en una solución diseñada para ser más sencilla de utilizar que Docker, pero que ofrece muchas de sus ventajas: [Code Ocean](https://codeocean.com/). Code Ocean es una plataforma en la nube para la reproducibilidad computacional. Permite crear una cápsula de computación que se ejecuta en línea y contiene todos los paquetes necesarios para ejecutar el código. Aunque Code Ocean no garantiza —al menos por ahora— el almacenamiento a largo plazo de los datos y el código, constituye una forma interesante de hacer que tu código reproducible esté disponible para otros investigadores y facilita mucho que investigadores o revisores realicen pequeñas modificaciones y examinen los resultados. Crea una cuenta gratuita en Code Ocean. Ve al panel principal, pulsa `New Capsule` y elige `Import Git Repository`.

![](https://lakens.github.io/statistical_inferences/images/b27f6ddcc48c4b808418612be7efd929.png)

Introduce la dirección web de tu repositorio de GitHub y pulsa `Import`.

![](https://lakens.github.io/statistical_inferences/images/51f0dab67e96b317ef54a0affabe14d6.png)

Haz clic en `Environment` en el panel izquierdo. En el panel central, pulsa el icono de R para seleccionar el lenguaje de programación. En el momento en que se escribió esta parte del capítulo, la versión predeterminada era R 3.5.3, pero puedes pulsar `2 more versions` y seleccionar la versión más reciente disponible.

![](https://lakens.github.io/statistical_inferences/images/d6a90fd36fce0555b797e269cdd8c992.png)

Debemos configurar el entorno de Code Ocean con los paquetes necesarios. Pulsa `+Add` junto a `apt-get`, escribe `pandoc` y pulsa dos veces la tecla Intro —no es necesario indicar una versión concreta de Pandoc—. Pulsa `+Add` junto a `R (CRAN)`, escribe `ggplot2` y pulsa Intro dos veces. Haz lo mismo con `reshape2` y, por último, con `rmarkdown`.

![](https://lakens.github.io/statistical_inferences/images/7be787e67b7e874fa88cfc2daae850b4.png)

En el panel izquierdo, arrastra `main_analysis.Rmd` a la carpeta `code` y `stroop.csv` a la carpeta `data`. Selecciona la carpeta `code` y pulsa el botón `+` de la barra situada en la parte superior del panel para añadir un archivo. Llámalo `run.sh`. Este archivo indicará a Code Ocean qué debe ejecutar. Selecciónalo. El panel central estará vacío. Añade el siguiente código:

```bash
#!/bin/bash
Rscript -e "rmarkdown::render(input = 'main_analysis.Rmd', \
output_dir = '../results', clean = TRUE)"
```

Debemos hacer un último cambio. Selecciona `main_analysis.Rmd` y desplázate hasta la línea 28, donde se leen los datos. Cambia:

```r
stroop_data <- read.csv("stroop.csv", sep = " ", header = TRUE)
```

por:

```r
stroop_data <- read.csv("../data/stroop.csv", sep = " ", header = TRUE)
```

¡Ya está todo preparado! Pulsa el botón `Reproducible Run` del panel derecho. Obtendrás una salida similar a esta:

![](https://lakens.github.io/statistical_inferences/images/6c4278d56ff2d9101052c74a61783b43.png)

Haz clic en `main_analysis.html`. Verás que el script ha generado nuestros resultados reproducibles. Haz *commit* de los cambios. En principio podrías hacer pública esta cápsula completamente reproducible y compartirla junto con el artículo publicado, aunque no lo haremos en este ejemplo.

![](https://lakens.github.io/statistical_inferences/images/f8904ae8e964bd88b2c21078ea9e81f9.png)

Ahora existe en línea un archivo de análisis completamente reproducible. Cualquiera puede no solo reproducir tu análisis, sino también entrar en `main_analysis.Rmd`, modificar lo que quiera y volver a ejecutarlo. Imagina, por ejemplo, que no te gusta la línea recta negra de la primera figura y quieres que sea roja. Basta cambiar `black` por `red` en la línea 42 y volver a ejecutar el análisis. Obtendrás una figura con una línea roja. Esto quizá no sea especialmente emocionante por sí mismo, pero la posibilidad de volver a analizar fácilmente los datos puede ser muy útil en situaciones más realistas. Imagina que estás revisando un artículo cuyos autores no muestran la distribución de los datos. Sin instalar ningún programa, puedes escribir `hist(stroop_data$Congruent)` después de que se hayan leído los datos —por ejemplo, en la línea 30—, volver a ejecutar el código y obtener un histograma de los tiempos de reacción de la condición congruente. Pruébalo.

## Algunos aspectos que pueden mejorar la reproducibilidad computacional

Recientemente intentamos reproducir computacionalmente Informes Registrados publicados en la literatura psicológica [@obels_analysis_2020]. Detectamos algunos problemas que, si se solucionan, pueden mejorar fácilmente la reproducibilidad computacional del trabajo científico.

En primer lugar, añade siempre un **libro de códigos** a los archivos de datos. Ya lo hemos señalado antes y, sí, da algo de trabajo y no resulta especialmente divertido, pero es esencial cuando compartes datos. Los datos son más fáciles de comprender y reutilizar si las variables y sus valores están claramente descritos. Los investigadores deberían asegurarse de que el libro de códigos y los nombres de las variables estén escritos en el mismo idioma que el artículo.

En segundo lugar, **anota el código** para dejar claro qué hace. Un código bien comentado muestra qué realiza el código de análisis, en qué orden deben ejecutarse los scripts cuando hay varios —por ejemplo, para preprocesar los datos brutos, calcular puntuaciones totales, analizar los resultados y generar gráficos— y qué salida produce cada sección del código. A veces incluso puede ser útil copiar desde el manuscrito final las frases de la sección de Resultados y pegarlas como comentarios en el archivo de código, para que quede muy clara la relación entre las frases del manuscrito y el código que las genera. También ayuda estructurar claramente el código —por ejemplo mediante un README— para que otras personas sepan qué salida crea cada script y en qué orden deben ejecutarse.

En tercer lugar, comprueba que el código compartido **sigue reproduciendo todos los análisis después de las revisiones**. Los investigadores suelen introducir cambios durante el proceso de revisión por pares y a veces olvidan actualizar los archivos de análisis.

Por último, recuerda que la mayoría del código de R depende de bibliotecas concretas —también llamadas paquetes—. Enumera al principio del script todos los paquetes que el código necesita para ejecutarse. Como los paquetes se actualizan, es necesario informar de las versiones utilizadas —por ejemplo mediante `packrat`, o copiando la salida de `sessionInfo()` como comentario en el script—. Recuerda también que los nombres y las estructuras de las carpetas difieren entre ordenadores; por ello debes utilizar rutas relativas y no rutas absolutas como `c:/user/myfolder/code`. Los proyectos de RStudio y el paquete `here` proporcionan una manera sencilla de trabajar con rutas relativas. Cuando el análisis utilice varios scripts, especifica en un archivo README el orden en el que deben ejecutarse sobre los datos.

## Conclusión

En este capítulo hemos utilizado varias plataformas y soluciones de software: GitHub, Open Science Framework, RStudio, R y R Markdown. Seguir paso a paso el ejemplo no equivale a dominar estas herramientas en tu propia investigación. Aprender a utilizarlas requiere tiempo. Habrá muchos momentos frustrantes en los que el código o el software no funcionen como deseas, o en los que tus repositorios local y remoto de GitHub estén tan desincronizados que la solución más sencilla parezca borrar todo lo que hay en tu ordenador y volver a descargar los archivos desde GitHub —`git reset --hard HEAD` es tu amigo—. En internet existen multitud de recursos para buscar respuestas o pedir ayuda.

En mi experiencia, requiere algo de trabajo, pero es perfectamente factible incluso si tienes conocimientos muy limitados de programación. Puedes poner en marcha un flujo de trabajo reproducible básico simplemente siguiendo los pasos descritos aquí y aprender nuevas habilidades cuando las necesites. Estas competencias se valoran tanto dentro como fuera del mundo académico —algo útil para los estudiantes de doctorado— y pronto empiezan a ahorrar tiempo, por ejemplo al recrear figuras durante una revisión o al analizar en el futuro conjuntos de datos muy similares. Un flujo de trabajo reproducible también mejora la calidad de tu trabajo científico y facilita que otros investigadores puedan reutilizarlo. Otro recurso educativo abierto sobre cómo hacer que la investigación científica sea accesible y reproducible es [The Open Science Manual](https://arca-dpss.github.io/manual-open-science/), de Claudio Zandonella Callegher y Davide Massidda.
