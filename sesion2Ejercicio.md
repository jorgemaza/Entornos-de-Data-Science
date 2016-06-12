
# Generar 10000 números aleatorios con una distribución normal estándar (media 0 y varianza 1).

```R
> r<-rnorm(10000)
```

# Realizar un histograma de los valores anteriores. ¿Cuál es el menor y mayor valor generado?.

```R
> hist(r)
```

![Hist1](https://github.com/jorgemaza/Entornos-de-Data-Science/blob/master/HistogramR.png)

```R
> min(r)
[1] -3.58055
> max(r)
[1] 3.861133
```

Mínimo: -3.58055. Máximo: 3.861133

# Generar los valores de la distribución normal teóricos en el intervalo anterior utilizando la función dnorm().

La distribución normal teórica utilizando la función dnorm() se obtiene generando la lista de 10000 valores no aleatorios sino sucesivos
con la función seq desde el mínimo hastra el máximo valor generado en la distribución de rnorm previamente calculada.

```R
> s<-seq(min(r),max(r),length.out = length(r))
> d<-dnorm(s)
```

# Al histograma anterior, superponer una curva con la función de densidad teórica calculada. ¿Se aproxima el histograma al valor teórico?

```R
> lines(s,d)
```

No se aproxima al valor teórico de la distribución. Se dibuja la línea en una región muy pequeña del histograma de la variable "r".

# Ver el parametro probability de la función hist y volver a generar el histograma cambiando su valor.
¿Se aproxima ahora a la función de densidad teórica?

El parámetro probability permite establecer el rango de la distribución normal y tipificar así los valores.

```R
> hist(r, probability = T)
```

El histograma cambia el eje Y de "frecuencia" a "densidad".

![Hist2](https://github.com/jorgemaza/Entornos-de-Data-Science/blob/master/HistogramRp.png)

```R
> lines(s,d)
```

Finalmente aparece superpuesta la línea y se puede apreciar la diferencia entre rnorm y dnorm con las diferencias entre valores aleatorios 
y valores que cumplen perfectamente la distribución respectivamente.

![Hist3](https://github.com/jorgemaza/Entornos-de-Data-Science/blob/master/HistogramRSuperpuesto.png)

