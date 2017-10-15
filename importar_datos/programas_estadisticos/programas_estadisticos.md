


<!-- ```{r, include=FALSE} -->
<!-- tutorial::go_interactive() -->
<!-- ``` -->


# Lectura de Archivos de Programas Estadísticos en R

Como ya sabemos, R es un lenguaje de programación y un entorno de computación para computación estadística. Su naturaleza de código fuente abierto ha hecho que en los últimos años prolifere ante alternativas a programas estadísticos de tipo comercial, como SPSS, SAS, etc.

En esta sección, veremos como podemos importar datos desde programas estadísticos avanzados. Así mismo, examinaremos los paquetes que necesitamos instalar para leer nuestros datos en R, de igual manera que hemos hechos con los datos almacenados en archivos Excel o JSON.

## Lectura de Archivos SPSS en R

Si somos usuarios del programa SPSS y deseamos importar nuestros archivos SPSS a R, en primer lugar necesitaremos instalar el paquete [haven](http://haven.tidyverse.org/) que forma parte del ecosistema [tidyverse](http://tidyverse.org/). 

### Instalación

La forma mas fácil de instalar `haven` es instalar el ecosistema
`tidyverse`:


```r
install.packages("tidyverse")
```

Alternativamente, para instalar únicamente `haven`:


```r
install.packages("haven")
```

Por último, podemos instalar la última versión en desarrollo desde su repositorio en GitHub:


```r
# install.packages("devtools")
devtools::install_github("tidyverse/haven")
```

__Nota__ que la última opción requiere de la instalación del paquete `devtools`.

### Uso


Para leer archivos SPSS desde R haremos uso de la función `read_sav()`:


```r
# Lectura de los datos SPSS
read_sav("data/Child_Data.sav")
```

Por supuesto `haven` nos permite gravar nuestros datos en un archivo SPSS con la ayuda de la función `write_sas`:


```r
# Escritura del dataframe `mtcars` a un archivo SPSS
write_sav(mtcars, "data/mtcars.sav")
```



## Lectura de Archivos Stata en R

Como en el caso anterior utilizaremos el paquete `haven` y pero en este caso utilizaremos la función `read_stata()`:



```r
# Lectura de los datos STATA
read_dta("data/Milk_Production.dta")
```

De igual manera que en el caso anterior podemos exportar nuestros datos a STATA sin embargo, para archivos Stata utilizaremos la función  `write_dta()`:


```r
# Escritura del dataframe `mtcars` a un archivo STATA
write_dta(mtcars, "data/mtcars.dta")
```



## Lectura de Archivos SAS en R

De la misma forma que en los dos casos anteriores utilizaremos el paquete `haven`, pero en este caso utilizaremos la función `read_sas()` para leer nuestros datos SAS dentro de R:


```r
# Lectura de los datos STATA
read_sas("data/iris.sas7bdat")
```

De manera semejante podemos exportar nuestros datos a STATA, aunque en esta ocasión utilizaremos la función `write_sas()`:


```r
# Escritura del dataframe `mtcars` a un archivo SAS
write_sas(mtcars, "data/mtcars.sas7bdat")
```



## Lectura de Archivos Systat en R

Si deseamos importar archivos Systat en R, en esta caso tenemos que hacer uso del paquete [foreign](https://cran.r-project.org/web/packages/foreign/foreign.pdf), como podemos ver a continuación:



```r
# Instalamos el paquete `foreing`
install.packages("foreign")
# Activamos la libreria `foreign`
library(foreign)
# Leemos los datos Systat
datos <- read.systat("<ruta archivo>")
```

## Lectura de Archivos Minitab en R

De igual manera que en el caso anterior utilizaremos el mismo paquete, pero en este caso utilizaremos la función `read.mtp()`:


```r
# Instalamos el paquete `foreing`
install.packages("foreign")
# Activamos la libreria `foreign`
library(foreign)
# Leemos los datos Systat
datos <- read.mtp("<ruta archivo>")
```


















