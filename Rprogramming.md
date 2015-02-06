R es un lenguaje que se utiliza para eel analisis estadistico. Se hizo basado en el lenguaje S desarrollado por John Chambers
en 1976. Utiliza un lenguaje de los 70 que aún no ha cambiado en nada.
## Objetos R
Data Types:
  - Atomic class
   * character()
   * numeric()
   * integer()
   * complex()
   * logical(TRUE, FALSE)
  - Vectors, lists
  - Factors
  - Missing values
  - Data Frames
  - Names
El operador **:** se utiliza para crear intersecuencia, por ejemplo
```  
     x <- 1:6
      print (x)
      [1] 1 2 3 4 5 6
````
## Tipos de vectores
````
    logical = x <- c(TRUE, FALSE)
    numerical = x <- c(0.5,0.6)
    character = x <- c("a", "b", "c")
    integer = x <- 9:29
    complex = x <- (1+0i, 4+2i)
```
Factors: usado para representar datos categoricos. Pueden ser:
  * Ordenado (ordered)
  * No ordenado (undordered)
Usamos _factors_ que diga hombre y mujer es mucho mejor si usamos por ejemplo una variable numeral como
1 o 2
```
     x <- factor(c("yes","yes","no","yes","no"))
     > x
     [1] yes yes no yes no
     Levels: no yes
     > table(x)
     x
     no yes
     2  3
     > unclass(x)
     [1] 2 2 1 2 1
     attr(,"levels")
     [1] "no" "yes"
```
El ```unclass()``` se encarga de transformar de factor a integer o viceversa.

Para que el orden de los niveles sea explicito, necesitamos decirle a R el orden que nosotros
precisamos, por ejemplo:
```
     > x <- factor (c("yes", "yes", "no", "yes", "no")
                    levels = c("yes","no"))
     > x
     [1] yes yes no yes no
     Levels: yes no
 ```
 # Missing values
 Son dos values ```.na(), .nan()``` para definir si son o no numeros o valores
 # Data frames
 Son los datos que presentamos en las tablas
 Data frame tiene un atributo especial llamado ```row.names```
 Se crea usando o llamando ```read.table(), read.csv()```
 Se puede convertir en una matrix llamando ```data.matrix()```
 
```
     > x <- data.frame(foo = 1:4, bar = c(T,T,F,F))
     > x
  foo   bar
1   1  TRUE
2   2  TRUE
3   3 FALSE
4   4 FALSE
> nrow(x)
[1] 4
> ncol(x)
[1] 2
```
Si queremos también podemos cambiar el nombre a las columnas o filas:
```
     > x <- 1:3
> x
[1] 1 2 3
> names(x) <- c("foo", "bar", "norf")
> x
 foo  bar norf 
   1    2    3 
 ```
 El `[` se utiliza para retornar un un objeto en la misma class que el original.
 El `[[` es usado para extraer elementos de una lista.
 El signo `$` usado para extraer elementos de la lista de los datos POR nombre.
 Ejemplo:
 ```
          > x <- c("a","b","c","c","d","a")
          > x[1]
            [1] "a"
          > x[2]
            [1] "b"
          > x[1:4]
            [1] "a" "b" "c" "c"
          > x[x > "a"]
            [1] "b" "c" "c" "d"
          > u <- x > "a"
          > u
            [1] FALSE  TRUE  TRUE  TRUE  TRUE FALSE
          > x[u]
            [1] "b" "c" "c" "d"
```


