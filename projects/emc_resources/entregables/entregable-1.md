
<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-MML-AM_CHTML' async></script>

# Entregable 1

<br>

Estadística Multivariada Computacional: Entregable 1, Nicolás Mazza.

Docente: Mathias Bourel

Miércoles, 24 de abril de 2019

<br>

<br>

# Práctico 0 Ej 7

Crear un data.frame miejemplo con 5 columnas (4 numéricas y 1 categórica) y 6 observaciones (o sea 6 filas).

`c1 <- c(1,2,3,4,5,6)`

`c5 <- c('a', 'b', 'c', 'd', 'e', 'f')`

`miejemplo <- data.frame(c1, c2=c1*2, c3=c2*2, c4=c3*2, c5)`

```
> miejemplo
  c1 c2 c3 c4 c5
1  1  2  4  8  a
2  2  4  8 16  b
3  3  6 12 24  c
4  4  8 16 32  d
5  5 10 20 40  e
6  6 12 24 48  f
```
```
> typeof(c1)
[1] "double"
> typeof(c5)
[1] "character"
```
## Ej. 7 pt. a)

Dar nombres a las filas y nombres a las columnas.

`colnames(miejemplo) <- c('col_1','col_2','col_3','col_4','col_5')`

`rownames(miejemplo) <- c('row_1','row_2','row_3','row_4','row_5','row_6')`

```
> miejemplo
      col_1 col_2 col_3 col_4 col_5
row_1     1     2     4     8     a
row_2     2     4     8    16     b
row_3     3     6    12    24     c
row_4     4     8    16    32     d
row_5     5    10    20    40     e
row_6     6    12    24    48     f
```

## Ej. 7 pt. b)

Añadir a este objeto una columna que sea la suma de las 3 primeras columnas numéricas y otra columna que indica con 0/1 si el valor numérico de la segunda columna es mayor que 5 o no. Dar un nombre a estas nuevas columnas.

`miejemplo$$sum_1_2_3 <- miejemplo$$col_1 + miejemplo$$col_2 + miejemplo$$col_3`

`miejemplo$$grt_5 <- sapply(miejemplo$$col_2, function(x) if (x>5) return(1) else return(0))`

`names(miejemplo)[names(miejemplo) == "sum_1_2_3"] <- "col_sum"`

`names(miejemplo)[names(miejemplo) == "grt_5"] <- "greater"`

```
> miejemplo
      col_1 col_2 col_3 col_4 col_5 col_sum greater
row_1     1     2     4     8     a       7       0
row_2     2     4     8    16     b      14       0
row_3     3     6    12    24     c      21       1
row_4     4     8    16    32     d      28       1
row_5     5    10    20    40     e      35       1
row_6     6    12    24    48     f      42       1
```
## Ej. 7 pt. c)

Borrar la primera fila y la última columna. Dar un nombre a este nuevo objeto

`nuevo_ejemplo <- miejemplo[-1,-length(miejemplo)]`

```
> nuevo_ejemplo
      col_1 col_2 col_3 col_4 col_5 col_sum
row_2     2     4     8    16     b      14
row_3     3     6    12    24     c      21
row_4     4     8    16    32     d      28
row_5     5    10    20    40     e      35
row_6     6    12    24    48     f      42
```

## Ej. 7 pt. d) 

Hacer un resumen estadístico de los datos de este data frame cuando esto tiene sentido.

*En realidad no tiene mucho sentido hacer un resumen estadístico de estos datos, pero ahí van.*

`summary(miejemplo)`

```
     col_1          col_2          col_3        col_4    col_5    col_sum
 Min.   :1.00   Min.   : 2.0   Min.   : 4   Min.   : 8   a:1   Min.   : 7.00
 1st Qu.:2.25   1st Qu.: 4.5   1st Qu.: 9   1st Qu.:18   b:1   1st Qu.:15.75
 Median :3.50   Median : 7.0   Median :14   Median :28   c:1   Median :24.50
 Mean   :3.50   Mean   : 7.0   Mean   :14   Mean   :28   d:1   Mean   :24.50
 3rd Qu.:4.75   3rd Qu.: 9.5   3rd Qu.:19   3rd Qu.:38   e:1   3rd Qu.:33.25
 Max.   :6.00   Max.   :12.0   Max.   :24   Max.   :48   f:1   Max.   :42.00
    greater
 Min.   :0.0000
 1st Qu.:0.2500
 Median :1.0000
 Mean   :0.6667
 3rd Qu.:1.0000
 Max.   :1.0000
```

## Ej. 7 pt. e)

Escribir miejemplo en un archivo de texto miejemplo.txt. Borrar el objeto de R. Cargar este archivo en el objeto miejemplo2.

`write.table(miejemplo, 'miejemplo.csv', append = FALSE, sep = ",", dec = ".", row.names = TRUE, col.names = TRUE)`

`rm(miejemplo)`

```
> miejemplo
Error: object 'miejemplo' not found
```

`miejemplo2 <- read.csv(file="./miejemplo.csv", header=TRUE, sep=",")`

```
> miejemplo2
      col_1 col_2 col_3 col_4 col_5 col_sum greater
row_1     1     2     4     8     a       7       0
row_2     2     4     8    16     b      14       0
row_3     3     6    12    24     c      21       1
row_4     4     8    16    32     d      28       1
row_5     5    10    20    40     e      35       1
row_6     6    12    24    48     f      42       1
```

## Ej. 7 pt. f)

Repetir el paso anterior con la base de datos de Iris.

`write.table(iris, 'iris.csv', append = FALSE, sep = ",",dec = ".", row.names = TRUE,col.names = TRUE)`

`iris2 <- read.csv(file="./iris.csv", header=TRUE, sep=",")`

```
> iris2
    Sepal.Length Sepal.Width Petal.Length Petal.Width    Species
1            5.1         3.5          1.4         0.2     setosa
2            4.9         3.0          1.4         0.2     setosa
3            4.7         3.2          1.3         0.2     setosa
4            4.6         3.1          1.5         0.2     setosa
5            5.0         3.6          1.4         0.2     setosa
6            5.4         3.9          1.7         0.4     setosa
...
149          6.2         3.4          5.4         2.3  virginica
150          5.9         3.0          5.1         1.8  virginica
```

# Práctico 1 Ej 8

Sean x e y vectores aleatorios, A y B matrices y c un vector fijo (no aleatorio) real.

<br>
<br>

## Pruebe que E(Ax) = AE(x)

<br>

$$\mathbb{E}(Ax)=\frac{1}{n}\sum_{i=1}^{n}Ax_i=A\frac{1}{n}\sum_{i=1}^{n}x_i=A\mathbb{E}(x)$$

<br>
<br>

## Pruebe que Cov(Ax, By) = ACov(x, y)B'

<br>

$$Cov(Ax,By)=\mathbb{E}((Ax-\bar{x})(By-\bar{y})')=\mathbb{E}(A(x-\bar{x})(y-\bar{y})'B')=A\mathbb{E}((x-\bar{x})(y-\bar{y})')B'=ACov(x,y)B'$$

<br>
<br>

## Pruebe que Var(Ax) = AVar(x)A'


<br>

$$Var(Ax)=Cov(Ax,Ax)=\mathbb{E}((Ax-\bar{x})(Ax-\bar{x})')=\mathbb{E}(A(x-\bar{x})(x-\bar{x})'A')$$

$$=A\mathbb{E}((x-\bar{x})(x-\bar{x})')A'=ACov(x,x)A'=AVar(x)A'$$

<br>
<br>

## Pruebe que Cov(x, y) = E(xy') − E(x)E(y)'

<br>

$$Cov(x,y)=\mathbb{E}((x-\mathbb{E}(x))(y-\mathbb{E}(y))')=\mathbb{E}(xy'-x\mathbb{E}(y)'-\mathbb{E}(x)y'+\mathbb{E}(x)\mathbb{E}(y)')$$

$$=\mathbb{E}(xy')-\mathbb{E}(x)\mathbb{E}(y)'-\mathbb{E}(x)\mathbb{E}(y)'+\mathbb{E}(x)\mathbb{E}(y)'=\mathbb{E}(xy')-\mathbb{E}(x)\mathbb{E}(y)'$$

<br>
<br>

## Pruebe que Var(x − c) = Var(x)


<br>

$$Var(x-c)=\mathbb{E}((x-c)^2)-(\mathbb{E}(x-c))^2=\mathbb{E}(x^2-2xc+c^2)-(\mathbb{E}(x)-\mathbb{E}(c))^2=\mathbb{E}(x^2)-\mathbb{E}(2xc)+\mathbb{E}(c^2)-(\mathbb{E}(x)-\mathbb{E}(c))^2$$

$$=\mathbb{E}(x^2)-\mathbb{E}(2xc)+\mathbb{E}(c^2)-(\mathbb{E}(x)^2-2\mathbb{E}(x)\mathbb{E}(c)+\mathbb{E}(c)^2)=\mathbb{E}(x^2)-\mathbb{E}(2xc)+c^2-(\mathbb{E}(x)^2-2\mathbb{E}(x)c+c^2)$$

$$=\mathbb{E}(x^2)-2c\mathbb{E}(x)+c^2-(\mathbb{E}(x)^2-2c\mathbb{E}(x)+c^2)=\mathbb{E}(x^2)-2c\mathbb{E}(x)+c^2-\mathbb{E}(x)^2+2c\mathbb{E}(x)-c^2=\mathbb{E}(x^2)-\mathbb{E}(x)^2=Var(x)$$

<br>
<br>

## Pruebe que Si x ∼ (µ, Σ) entonces E(x'Ax) = tr(AΣ) + µ'Aµ

<br>

$$X'AX=(X-\mu)'AX+\mu'AX=(X-\mu)'A(X-\mu)+\mu'AX+(X-\mu)'A\mu$$

$$\Rightarrow \mathbb{E}(X'AX)=\mathbb{E}((X-\mu)'A(X-\mu))+\mu'A\mu$$

$$=(\sum_{i=1}^{n}\sum_{j=1}^{n}\mathbb{E}[(X-\mu)_i'A_{ij}(X-\mu)_i])+\mu'A\mu=(\sum_{i=1}^{n}\sum_{j=1}^{n}A_{ij}Var(X-\mu)_{ij})+\mu'A\mu=(\sum_{i=1}^{n}\sum_{j=1}^{n}A_{ij}Σ_{ij})+\mu'A\mu$$

$$(\sum_{i=1}^{n}\sum_{j=1}^{n}A_{ij}Σ_{ji})+\mu'A\mu=(\sum_{i=1}^{n}\sum_{j=1}^{n}(AΣ)_{ii})+\mu'A\mu=tr(AΣ)+\mu'A\mu$$

<br>
<br>

# Práctico 1 Ej 14 

Se considera la función de densidad dada por

<br>

$$
f(x, y) =
\left\{\begin{matrix}
Kx & si\ \ 0 < x < 1,\ 0 < y < 1 - x\\ 
0  & \text{en otro caso}
\end{matrix}\right.
$$

<br>
<br>

## Halle K 

<br>

Para que sea una función de densidad se tiene que cumplir:

$$\int_{0}^{1} \int_{0}^{1-x}f(x,y)\ dydx=1$$

<br>

$$\int_{0}^{1} \int_{0}^{1-x}Kx\ dydx = \int_{0}^{1} Kxy\ \vert_{0}^{1-x} \ dx=\int_{0}^{1} Kx(1-x)-Kx(0) \ dx=\int_{0}^{1} Kx-Kx^2\ dx$$

$$=\int_{0}^{1} Kx\ dx-\int_{0}^{1}Kx^2\ dx= K\frac{x^2}{2} \vert_{0}^{1}- K\frac{x^3}{3} \ \vert_{0}^{1}$$

$$=K\frac{1^2}{2}-K\frac{0}{2} -( K\frac{1^3}{3} -K\frac{0}{3})=K\frac{1}{2} - K\frac{1}{3})=\frac{K}{6}$$

$$\Rightarrow \frac{K}{6}=1\Rightarrow K=6$$

<br>

$$
f(x, y) =
\left\{\begin{matrix}
6x & si\ \ 0 < x < 1,\ 0 < y < 1 - x\\ 
0  & \text{en otro caso}
\end{matrix}\right.
$$

<br>
<br>

## Halle las funciónes de densidad marginales

<br>

$$f_x(x)=\int_{-\infty}^{+\infty} f_{xy}(x,y)\ dy=\int_{-\infty}^{-0} 0\ dy+\int_{0}^{1-x} 6x\ dy+\int_{1-x}^{+\infty}0\ dy=\int_{0}^{1-x} 6x\ dy=6xy\vert_{0}^{1-x}=6x(1-x)=6x-6x^2$$

<br>

$$
\int_{-\infty}^{+\infty} f_x(x)\ dx=1
$$

$$
 \Rightarrow \int_{-\infty}^{0}0\ dx+\int_{0}^{1} 6x-6x^2\ dx + \int_{1}^{+\infty}0\ dx=\int_{0}^{1} 6x-6x^2\ dx
$$

$$
=\int_{0}^{1} 6x\ dx-\int_{0}^{1} 6x^2\ dx = 3x^2\vert_{0}^{1}-2x^3\vert_{0}^{1}=3-2=1
$$

<br>

$$
f_y(y)=\int_{-\infty}^{+\infty} f_{xy}(x,y)\ dx=\int_{-\infty}^{0} 0\ dx+\int_{0}^{1-y} 6x\ dx+\int_{1-y}^{+\infty} 0\ dx=\int_{0}^{1-y} 6x\ dx=3x^2\vert_{0}^{1-y}
$$

$$
=3(1-y)^2=3(1-2y+y^2)=3-6y+3y^2
$$

<br>

$$
\int_{-\infty}^{+\infty} f_y(y)\ dy=1
$$

$$
 \Rightarrow \int_{-\infty}^{0}0\ dy +\int_{0}^{1}3-6y+3y^2\ dy+\int_{1}^{+\infty}0\ dy=\int_{0}^{1}3-6y+3y^2\ dy
$$

$$
=\int_{0}^{1}3\ dy- \int_{0}^{1}6y\ dy+ \int_{0}^{1}3y^2\ dy=3y\vert_{0}^{1}-3y^2\vert_{0}^{1}+y^3\vert_{0}^{1}=3-3+1=1
$$

<br>
<br>

## Halle las densidades condicionales

<br>

$$
f_{xy}(x|y)=\frac{f_{xy}(x,y)}{f_y(y)}=
\left\{\begin{matrix}
\frac{6x}{3(1-2y+2y^2)} & si\ \ 0 < x < 1,\ 0 < y < 1 - x\\ 
0  & \text{en otro caso}
\end{matrix}\right.=
\left\{\begin{matrix}
\frac{2x}{1-2y+2y^2} & si\ \ 0 < x < 1,\ 0 < y < 1 - x\\ 
0  & \text{en otro caso}
\end{matrix}\right.
$$

<br>

$$
f_{xy}(y|x)=\frac{f_{xy}(x,y)}{f_x(x)}=
\left\{\begin{matrix}
\frac{6x}{6(x-x^2)} & si\ \ 0 < x < 1,\ 0 < y < 1 - x\\ 
0  & \text{en otro caso}
\end{matrix}\right.=
\left\{\begin{matrix}
\frac{1}{1-x} & si\ \ 0 < x < 1,\ 0 < y < 1 - x\\ 
0  & \text{en otro caso}
\end{matrix}\right.
$$

<br>
<br>

## Halle el vector de medias

<br>

$$
\begin{pmatrix}
 \mathbb{E}(x)\\
 \mathbb{E}(y)
\end{pmatrix}=
\begin{pmatrix}
 \int_{-\infty}^{+\infty} xf_x(x)\ dx\\
 \int_{-\infty}^{+\infty} yf_y(y)\ dy
\end{pmatrix}
$$

<br>

$$
\int_{-\infty}^{+\infty} xf_x(x)\ dx=\int_{-\infty}^{0} 0\ dx+\int_{0}^{1} x(6x-6x^2)\ dx+\int_{1}^{+\infty} 0\ dx=\int_{0}^{1} x(6x-6x^2)\ dx=\int_{0}^{1} 6x^2\ dx-\int_{0}^{1} 6x^3\ dx
$$

$$
=2x^3\vert_{0}^{1}-\frac{3x^4}{2}\vert_{0}^{1}=2-\frac{3}{2}=\frac{1}{2}
$$

<br>

$$
\int_{-\infty}^{+\infty} yf_y(y)\ dy=\int_{-\infty}^{0} 0\ dy+\int_{0}^{1} y(3-6y+3y^2)\ dy+\int_{1}^{+\infty} 0\ dy=\int_{0}^{1} y(3-6y+3y^2)\ dy=\int_{0}^{1} 3y-6y^2+3y^3\ dy
$$

$$
\int_{0}^{1} 3y\ dy-\int_{0}^{1} 6y^2\ dy+\int_{0}^{1} 3y^3\ dy=\frac{3y^2}{2}\vert_{0}^{1}-2y^3\vert_{0}^{1}+\frac{3y^4}{4}\vert_{0}^{1}=\frac{3}{2}-2+\frac{3}{4}=\frac{1}{4}
$$

<br>

$$
\begin{pmatrix}
 \mathbb{E}(x)\\
 \mathbb{E}(y)
\end{pmatrix}=
\begin{pmatrix}
 \frac{1}{2}\\
 \frac{1}{4}
\end{pmatrix}
$$

<br>
<br>

## Halle la matriz de Varianzas-Covarianzas

<br>

$$
\begin{pmatrix}
Var(X) & Cov(X,Y)\\
Cov(X,Y) & Var(Y) 
\end{pmatrix}
$$

<br>

$$
Var(X)=\mathbb{E}[X^2]-(\mathbb{E}[X])^2
$$

<br>

$$
\mathbb{E}[X^2]=\int_{-\infty}^{+\infty} x^2f_x(x)\ dx=\int_{-\infty}^{+\infty} x^2(6x-6x^2)\ dx=\int_{-\infty}^{0} 0\ dx +\int_{0}^{1} x^2(6x-6x^2)\ dx +\int_{1}^{+\infty} 0\ dx =\int_{0}^{1} x^2(6x-6x^2)\ dx
$$

$$
=\int_{0}^{1} 6x^3-6x^4\ dx=\int_{0}^{1} 6x^3\ dx-\int_{0}^{1} 6x^4\ dx=\frac{3x^4}{2}\vert_{0}^{1}-\frac{6x^5}{5}\vert_{0}^{1}=\frac{3}{2}-\frac{6}{5}=\frac{3}{10}
$$

<br>

$$
Var(X)=\mathbb{E}[X^2]-(\mathbb{E}[X])^2=\frac{3}{10}-
\left(
 \frac{1}{2}
\right)^2
=\frac{1}{20}=0.05
$$

<br>
<br>

$$
Var(Y)=\mathbb{E}[Y^2]-(\mathbb{E}[Y])^2
$$

<br>

$$
\mathbb{E}[Y^2]=\int_{-\infty}^{+\infty} y^2f_y(y)\ dy=\int_{-\infty}^{+\infty} y^2(3-6y+3y^2)\ dy=\int_{-\infty}^{0} 0\ dy +\int_{0}^{1} y^2(3-6y+3y^2)\ dy +\int_{1}^{+\infty} 0\ dy 
$$

$$
=\int_{0}^{1} y^2(3-6y+3y^2)\ dy=\int_{0}^{1} y^2(3-6y+3y^2)\ dy=\int_{0}^{1} 3y^2-6y^3+3y^4\ dy
$$

$$
=\int_{0}^{1}3y^2\ dy-\int_{0}^{1}6y^3\ dy+\int_{0}^{1}3y^4\ dy = y^3\vert_{0}^{1}-\frac{3y^4}{2}\vert_{0}^{1}+\frac{3y^5}{5}\vert_{0}^{1}=1-\frac{3}{2}+\frac{3}{5}=\frac{1}{10}
$$

<br>

$$
Var(Y)=\mathbb{E}[Y^2]-(\mathbb{E}[Y])^2=\frac{1}{10}-
\left(
 \frac{1}{4}
\right)^2
=\frac{3}{80}=0.0375
$$

<br>
<br>

$$
Cov(X,Y)=\mathbb{E}[XY]-\mathbb{E}[X]\mathbb{E}[Y]
$$

<br>

$$
\mathbb{E}[XY] = \int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty} xyf_{xy}(xy)\ dydx=\int_{-\infty}^{0}\int_{-\infty}^{0} 0\ dydx+\int_{0}^{1}\int_{0}^{1-x}xy(6x)\ dydx+\int_{-\infty}^{0}\int_{-\infty}^{0} 0\ dydx=\int_{0}^{1}\int_{0}^{1-x}xy(6x)\ dydx
$$

$$
=\int_{0}^{1}\int_{0}^{1-x}xy(6x)\ dydx=\int_{0}^{1}\int_{0}^{1-x}6x^2y\ dydx=\int_{0}^{1}3x^2y^2 \vert_{0}^{1-x}\ dx=\int_{0}^{1}3x^2(1-x)^2\ dx=\int_{0}^{1}3x^2(1-2x+x^2)\ dx
$$

$$
=\int_{0}^{1}3x^2-6x^3+3x^4\ dx=\int_{0}^{1}3x^2\ dx-\int_{0}^{1}6x^3 dx+\int_{0}^{1}3x^4\ dx=x^3\vert_{0}^{1}-\frac{3x^4}{2}\vert_{0}^{1}+\frac{3x^5}{5}\vert_{0}^{1}=1-\frac{3}{2}+\frac{3}{5}=\frac{1}{10}
$$

<br>

$$
Cov(X,Y)=\mathbb{E}[XY]-\mathbb{E}[X]\mathbb{E}[Y]=\frac{1}{10}-\frac{1}{2}*\frac{1}{4}=-\frac{1}{40}=-0.025
$$

<br>

$$
\begin{pmatrix}
Var(X) & Cov(X,Y)\\
Cov(X,Y) & Var(Y) 
\end{pmatrix}=
\begin{pmatrix}
\frac{1}{20} & -\frac{1}{40}\\
-\frac{1}{40} & \frac{3}{80} 
\end{pmatrix}=
\begin{pmatrix}
0.05 & -0.025\\
-0.025 & 0.0375 
\end{pmatrix}
$$

<br>
<br>

## Halle el coeficiente de correlación

<br>

$$
\rho = \frac{Cov(X,Y)}{\sigma_x\sigma_y}
$$

<br>

$$
\sigma_x = \sqrt{Var(x)}=\sqrt{\frac{1}{20}} = \frac{\sqrt{5}}{10}
$$

$$
\sigma_y = \sqrt{Var(y)}=\sqrt{\frac{3}{80}} = \frac{\sqrt{15}}{20}
$$

$$
\sigma_x \sigma_y= \frac{\sqrt{5}}{10}*\frac{\sqrt{15}}{20}=\frac{\sqrt{3}}{40}
$$

<br>

$$
\rho = \frac{Cov(X,Y)}{\sigma_x\sigma_y}=\frac{-0.025}{\frac{\sqrt{3}}{40}}=-\frac{\sqrt{3}}{3}\approx-0.57
$$

<br>
<br>

# Práctico 2 Ej 1

<br>

Se extraen sucesivamente, sin reemplazamiento, dos bolas de una urna que contiene tres blancas y dos negras. En relación a este experimento, se definen las siguientes variables:

$$
X=
\left\{\begin{matrix}
0 & \text{si la primera bola es blanca}\\
1 & \text{si la primera bola es negra}
\end{matrix}\right.
\ \ \ \ \ \ \ \ \ \ \ \ \ 
Y=
\left\{\begin{matrix}
0 & \text{si la segunda bola es blanca}\\
1 & \text{si la segunda bola es negra}
\end{matrix}\right.
$$

Descomponer la varianza de la variable X teniendo en cuenta el condicionamiento a Y

<br><br><br>