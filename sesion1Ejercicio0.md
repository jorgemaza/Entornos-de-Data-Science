Con el data frame mtcars (viene cargado en R).

#1. Previsualizar el contenido con la funcióon head().

```R
> head(mtcars)
                   mpg cyl disp  hp drat    wt  qsec vs am gear carb
Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0    3    1
```

#2. Mirar el número de filas y columnas con nrow() y ncol().

```R
> nrow(mtcars)
[1] 32
> ncol(mtcars)
[1] 11
```

#3. Crear un nuevo data frame con los modelos de coche que
consumen menos de 15 millas/galón.

```R
> nuevoDF <- mtcars[mtcars$mpg<15,]
> nuevoDF
                     mpg cyl disp  hp drat    wt  qsec vs am gear carb
Duster 360          14.3   8  360 245 3.21 3.570 15.84  0  0    3    4
Cadillac Fleetwood  10.4   8  472 205 2.93 5.250 17.98  0  0    3    4
Lincoln Continental 10.4   8  460 215 3.00 5.424 17.82  0  0    3    4
Chrysler Imperial   14.7   8  440 230 3.23 5.345 17.42  0  0    3    4
Camaro Z28          13.3   8  350 245 3.73 3.840 15.41  0  0    3    4
```

#4. Ordenar el data frame anterior por disp.

```R
> nuevoDF[order(nuevoDF$disp),]
                     mpg cyl disp  hp drat    wt  qsec vs am gear carb
Camaro Z28          13.3   8  350 245 3.73 3.840 15.41  0  0    3    4
Duster 360          14.3   8  360 245 3.21 3.570 15.84  0  0    3    4
Chrysler Imperial   14.7   8  440 230 3.23 5.345 17.42  0  0    3    4
Lincoln Continental 10.4   8  460 215 3.00 5.424 17.82  0  0    3    4
Cadillac Fleetwood  10.4   8  472 205 2.93 5.250 17.98  0  0    3    4
```

Por defecto aparece en order creciente. 
Se puede ordernar por orden creciente o decreciente según el valor booleano que asignemos al parámetro decreasing de la función order.

```R
> nuevoDF[order(nuevoDF$disp, decreasing = T),]
                     mpg cyl disp  hp drat    wt  qsec vs am gear carb
Cadillac Fleetwood  10.4   8  472 205 2.93 5.250 17.98  0  0    3    4
Lincoln Continental 10.4   8  460 215 3.00 5.424 17.82  0  0    3    4
Chrysler Imperial   14.7   8  440 230 3.23 5.345 17.42  0  0    3    4
Duster 360          14.3   8  360 245 3.21 3.570 15.84  0  0    3    4
Camaro Z28          13.3   8  350 245 3.73 3.840 15.41  0  0    3    4
```

#5. Calcular la media de las marchas (gear) de los modelos del
data frame anterior.

```R
> mean(nuevoDF$gear)
[1] 3
```

#6. Cambiar los nombres de las variables del data frame a
var1, var2, ..., var11.
Pista: Mirar la documentacióon de la funcióon paste y
usarla para generar el vector (\var1", \var2", ..., \varN")
donde N es el número de variables del data frame.

Se ha utilizado paste0 para eliminar los espacios a la hora de generar las variables del dataframe.

```R
> paste("var",c(1:ncol(mtcars)))
 [1] "var 1"  "var 2"  "var 3"  "var 4"  "var 5"  "var 6"  "var 7"  "var 8" 
 [9] "var 9"  "var 10" "var 11"
> paste0("var",c(1:ncol(mtcars)))
 [1] "var1"  "var2"  "var3"  "var4"  "var5"  "var6"  "var7"  "var8"  "var9" 
[10] "var10" "var11"
```

Por lo tanto esta sería la manera de cambiar el nombre de las columnas (con la utilidad que ofrece la función colnames())

```R
> colnames(nuevoDF) <- paste0("var",c(1:ncol(mtcars)))
> nuevoDF
                    var1 var2 var3 var4 var5  var6  var7 var8 var9 var10 var11
Duster 360          14.3    8  360  245 3.21 3.570 15.84    0    0     3     4
Cadillac Fleetwood  10.4    8  472  205 2.93 5.250 17.98    0    0     3     4
Lincoln Continental 10.4    8  460  215 3.00 5.424 17.82    0    0     3     4
Chrysler Imperial   14.7    8  440  230 3.23 5.345 17.42    0    0     3     4
Camaro Z28          13.3    8  350  245 3.73 3.840 15.41    0    0     3     4
```
