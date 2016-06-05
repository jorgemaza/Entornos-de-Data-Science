Con el data frame iris (viene cargado en R).
#1. ¿Cómo está estructurado el data frame? (utilizar las
funciones str() y dim()).

```R
> str(iris)
'data.frame':	150 obs. of  5 variables:
 $ Sepal.Length: num  5.1 4.9 4.7 4.6 5 5.4 4.6 5 4.4 4.9 ...
 $ Sepal.Width : num  3.5 3 3.2 3.1 3.6 3.9 3.4 3.4 2.9 3.1 ...
 $ Petal.Length: num  1.4 1.4 1.3 1.5 1.4 1.7 1.4 1.5 1.4 1.5 ...
 $ Petal.Width : num  0.2 0.2 0.2 0.2 0.2 0.4 0.3 0.2 0.2 0.1 ...
 $ Species     : Factor w/ 3 levels "setosa","versicolor",..: 1 1 1 1 1 1 1 1 1 1 ...
> dim(iris)
[1] 150   5
```

El dataframe está formado por 5 medidas de pétalos y sépalos de ciertas especies de un total de 150 lirios.

#2. ¿De qué tipo es cada una de las variables del data frame?
Con la función str() se puede apreciar que todas son de tipo "numeric" excepto la columna "Species" 
que es de un tipo "factor" de especies ("setosa", "versicolor" y "virginica").

#3. Utilizar la función summary() para obtener un resumen de
los estadísticos de las variables.

```R
> summary(iris)
  Sepal.Length    Sepal.Width     Petal.Length    Petal.Width   
 Min.   :4.300   Min.   :2.000   Min.   :1.000   Min.   :0.100  
 1st Qu.:5.100   1st Qu.:2.800   1st Qu.:1.600   1st Qu.:0.300  
 Median :5.800   Median :3.000   Median :4.350   Median :1.300  
 Mean   :5.843   Mean   :3.057   Mean   :3.758   Mean   :1.199  
 3rd Qu.:6.400   3rd Qu.:3.300   3rd Qu.:5.100   3rd Qu.:1.800  
 Max.   :7.900   Max.   :4.400   Max.   :6.900   Max.   :2.500  
       Species  
 setosa    :50  
 versicolor:50  
 virginica :50  
```
#4. Comprobar con las funciones mean(), range(), que se
obtienen los mismos valores.

Se han comprobado los valores de la primera columna. 
La función mean() devuelve la media y range() los valores mínimo y máximo del dataframe.

```R
> range(iris$Sepal.Length)
[1] 4.3 7.9
> mean(iris$Sepal.Length)
[1] 5.843333
```

#5. Cambia los valores de las variables Sepal.Length
Sepal.Width de las 5 primeras observaciones por NA.

```R
> iris$Sepal.Length
  [1] 5.1 4.9 4.7 4.6 5.0 5.4 4.6 5.0 4.4 4.9 5.4 4.8 4.8 4.3 5.8 5.7 5.4 5.1
 [19] 5.7 5.1 5.4 5.1 4.6 5.1 4.8 5.0 5.0 5.2 5.2 4.7 4.8 5.4 5.2 5.5 4.9 5.0
 [37] 5.5 4.9 4.4 5.1 5.0 4.5 4.4 5.0 5.1 4.8 5.1 4.6 5.3 5.0 7.0 6.4 6.9 5.5
 [55] 6.5 5.7 6.3 4.9 6.6 5.2 5.0 5.9 6.0 6.1 5.6 6.7 5.6 5.8 6.2 5.6 5.9 6.1
 [73] 6.3 6.1 6.4 6.6 6.8 6.7 6.0 5.7 5.5 5.5 5.8 6.0 5.4 6.0 6.7 6.3 5.6 5.5
 [91] 5.5 6.1 5.8 5.0 5.6 5.7 5.7 6.2 5.1 5.7 6.3 5.8 7.1 6.3 6.5 7.6 4.9 7.3
[109] 6.7 7.2 6.5 6.4 6.8 5.7 5.8 6.4 6.5 7.7 7.7 6.0 6.9 5.6 7.7 6.3 6.7 7.2
[127] 6.2 6.1 6.4 7.2 7.4 7.9 6.4 6.3 6.1 7.7 6.3 6.4 6.0 6.9 6.7 6.9 5.8 6.8
[145] 6.7 6.7 6.3 6.5 6.2 5.9
> iris$Sepal.Length[1:5]<-NA
> iris$Sepal.Length
  [1]  NA  NA  NA  NA  NA 5.4 4.6 5.0 4.4 4.9 5.4 4.8 4.8 4.3 5.8 5.7 5.4 5.1
 [19] 5.7 5.1 5.4 5.1 4.6 5.1 4.8 5.0 5.0 5.2 5.2 4.7 4.8 5.4 5.2 5.5 4.9 5.0
 [37] 5.5 4.9 4.4 5.1 5.0 4.5 4.4 5.0 5.1 4.8 5.1 4.6 5.3 5.0 7.0 6.4 6.9 5.5
 [55] 6.5 5.7 6.3 4.9 6.6 5.2 5.0 5.9 6.0 6.1 5.6 6.7 5.6 5.8 6.2 5.6 5.9 6.1
 [73] 6.3 6.1 6.4 6.6 6.8 6.7 6.0 5.7 5.5 5.5 5.8 6.0 5.4 6.0 6.7 6.3 5.6 5.5
 [91] 5.5 6.1 5.8 5.0 5.6 5.7 5.7 6.2 5.1 5.7 6.3 5.8 7.1 6.3 6.5 7.6 4.9 7.3
[109] 6.7 7.2 6.5 6.4 6.8 5.7 5.8 6.4 6.5 7.7 7.7 6.0 6.9 5.6 7.7 6.3 6.7 7.2
[127] 6.2 6.1 6.4 7.2 7.4 7.9 6.4 6.3 6.1 7.7 6.3 6.4 6.0 6.9 6.7 6.9 5.8 6.8
[145] 6.7 6.7 6.3 6.5 6.2 5.9
```

#6. ¿Qué pasa si usamos ahora las funciones mean(), range()
con las variables Sepal.Length y Sepal.Width? ¿Tiene el
mismo problema la función summary()?

```R
> range(iris$Sepal.Length)
[1] NA NA
> mean(iris$Sepal.Lenght)
[1] NA

> summary(iris)
  Sepal.Length    Sepal.Width     Petal.Length    Petal.Width   
 Min.   :4.300   Min.   :2.000   Min.   :1.000   Min.   :0.100  
 1st Qu.:5.200   1st Qu.:2.800   1st Qu.:1.600   1st Qu.:0.300  
 Median :5.800   Median :3.000   Median :4.350   Median :1.300  
 Mean   :5.877   Mean   :3.057   Mean   :3.758   Mean   :1.199  
 3rd Qu.:6.400   3rd Qu.:3.300   3rd Qu.:5.100   3rd Qu.:1.800  
 Max.   :7.900   Max.   :4.400   Max.   :6.900   Max.   :2.500  
 NA's   :5                                                      
       Species  
 setosa    :50  
 versicolor:50  
 virginica :50  
```

Los valores de Sepal.Lenght no son tomados como numéricos a causa del "NA". 
Por eso range() devuelve el mismo valor NA en mínimo y máximo.
La función mean(), no es capaz de hacer una media con ese mismo valor no numérico.

Sin embargo, summary() obvia los NA y realiza el cálculo correctamente.

#7. Ver la documentación de mean(), range(), etc. ¿Qué
parámetro habría que cambiar para arreglar el problema
anterior?.

```R
>?mean

Usage

mean(x, ...)

## Default S3 method:
mean(x, trim = 0, na.rm = FALSE, ...)
Arguments

x	
An R object. Currently there are methods for numeric/logical vectors and date, date-time and time interval objects. Complex vectors are allowed for trim = 0, only.
trim	
the fraction (0 to 0.5) of observations to be trimmed from each end of x before the mean is computed. Values of trim outside that range are taken as the nearest endpoint.
na.rm	
a logical value indicating whether NA values should be stripped before the computation proceeds.
...	
further arguments passed to or from other methods.
```

La ayuda de R aclara la duda. Hay que pasar el parámetro na.rm a TRUE de forma que obvie los NA.

```R
> mean(iris$Sepal.Length)
[1] NA
> mean(iris$Sepal.Length, na.rm=T)
[1] 5.877241
```

```R
>?range

Usage

range(..., na.rm = FALSE)

## Default S3 method:
range(..., na.rm = FALSE, finite = FALSE)
Arguments

...	
any numeric or character objects.
na.rm	
logical, indicating if NA's should be omitted.
finite	
logical, indicating if all non-finite elements should be omitted.
```

Igual con range(): utilizar na.rm.

```R
> range(iris$Sepal.Length)
[1] NA NA
> range(iris$Sepal.Length, na.rm=T)
[1] 4.3 7.9
```

#8. Visto lo anterior, ¿por qué es importante codificar los
missing values como NA y no como 0, por ejemplo?

Porque no es lo mismo obviar un valor que valorarlo. Es decir, la media y el rango se saltan los valores no numéricos o campos sin valor.
Sin embargo, si se utilizase 0, calcularía la media teniendo en cuenta los ceros y 
los resultados serían más bajos en la media el mínimo del rango sería cero.

#9. Eliminar los valores NA usando na.omit().

```R
> na.omit(iris$Sepal.Length)
  [1] 5.4 4.6 5.0 4.4 4.9 5.4 4.8 4.8 4.3 5.8 5.7
 [12] 5.4 5.1 5.7 5.1 5.4 5.1 4.6 5.1 4.8 5.0 5.0
 [23] 5.2 5.2 4.7 4.8 5.4 5.2 5.5 4.9 5.0 5.5 4.9
 [34] 4.4 5.1 5.0 4.5 4.4 5.0 5.1 4.8 5.1 4.6 5.3
 [45] 5.0 7.0 6.4 6.9 5.5 6.5 5.7 6.3 4.9 6.6 5.2
 [56] 5.0 5.9 6.0 6.1 5.6 6.7 5.6 5.8 6.2 5.6 5.9
 [67] 6.1 6.3 6.1 6.4 6.6 6.8 6.7 6.0 5.7 5.5 5.5
 [78] 5.8 6.0 5.4 6.0 6.7 6.3 5.6 5.5 5.5 6.1 5.8
 [89] 5.0 5.6 5.7 5.7 6.2 5.1 5.7 6.3 5.8 7.1 6.3
[100] 6.5 7.6 4.9 7.3 6.7 7.2 6.5 6.4 6.8 5.7 5.8
[111] 6.4 6.5 7.7 7.7 6.0 6.9 5.6 7.7 6.3 6.7 7.2
[122] 6.2 6.1 6.4 7.2 7.4 7.9 6.4 6.3 6.1 7.7 6.3
[133] 6.4 6.0 6.9 6.7 6.9 5.8 6.8 6.7 6.7 6.3 6.5
[144] 6.2 5.9
attr(,"na.action")
[1] 1 2 3 4 5
attr(,"class")
[1] "omit"
```

#10. Calcular la media de la variable Petal.Length para cada
uno de las distintas especies (Species). Pista: usar la
función tapply().

```R
>?tapply
Usage

tapply(X, INDEX, FUN = NULL, ..., simplify = TRUE)
Arguments

X	
an atomic object, typically a vector.
INDEX	
list of one or more factors, each of same length as X. The elements are coerced to factors by as.factor.
FUN	
the function to be applied, or NULL. In the case of functions like +, %*%, etc., the function name must be backquoted or quoted. If FUN is NULL, tapply returns a vector which can be used to subscript the multi-way array tapply normally produces.
...	
optional arguments to FUN: the Note section.
simplify	
If FALSE, tapply always returns an array of mode "list". If TRUE (the default), then if FUN always returns a scalar, tapply returns an array with the mode of the scalar.
```

La ayuda de R aclara la funcionalidad de tapply(). El vector de  longitudes de pétalos iris$Petal.Lenght y vector de iris$Species tienen la misma longitud lo que hace que 
esta función permita realizar los cálculos de la media teniendo en cuenta cada valor de cada elemento de los vectores según la especie marcada en INDEX.

```R
> tapply(iris$Petal.Length, iris$Species,mean)
    setosa versicolor  virginica 
     1.462      4.260      5.552 
```