<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-MML-AM_CHTML' async></script>

# Practico 1


## 1.

Dada la matriz $$A =
\begin{pmatrix}
 1 &1 \\ 
 0 &1 \\ 
 2 &2
\end{pmatrix}$$, calcule $${A}'A$$, halle su determinante, su traza y su inversa. Hacer lo mismo
para la matriz $$A{A}'$$.

### $${A}'A$$

$$
A=\begin{pmatrix}
 1 &1 \\ 
 0 &1 \\ 
 2 &2
\end{pmatrix}\Rightarrow
{A}'=\begin{pmatrix}
 1 &0 &2 \\ 
 1 &1 &2 
\end{pmatrix}
$$

$$
{A}'A=\begin{pmatrix}
 1 &0 &2 \\ 
 1 &1 &2 
\end{pmatrix}\begin{pmatrix}
 1 &1 \\ 
 0 &1 \\ 
 2 &2
\end{pmatrix}=
\begin{pmatrix}
 1*1+0*0+2*2 &1*1+0*1+2*2 \\
 1*1+0*1+2*2 &1*1+1*1+2*2
\end{pmatrix}=
\begin{pmatrix}
5 &5 \\
5 &6
\end{pmatrix}
$$

### Determinante $${A}'A$$

$$
{A}'A=\begin{pmatrix}
5 &5 \\
5 &6
\end{pmatrix}
$$

$$
\left | {A}'A \right | =
\left | 
\begin{matrix}
5 &5 \\
5 &6
\end{matrix}
\right | = 5*6-5*5=5
$$

### Traza $${A}'A$$

$$
{A}'A=\begin{pmatrix}
5 &5 \\
5 &6
\end{pmatrix}
$$

$$
tr({A}'A)=tr\begin{pmatrix}
5 &5 \\
5 &6
\end{pmatrix}=5+6=11
$$

### Inversa $${A}'A$$

$$
{A}'A=\begin{pmatrix}
5 &5 \\
5 &6
\end{pmatrix}
$$
$$({A}'A)^{-1}=\begin{pmatrix}
5 &5 \\
5 &6
\end{pmatrix}^{-1}\Rightarrow$$
$$
\Rightarrow
\begin{pmatrix}
5 & 5 & |\ \ 1 & 0\\
5 & 6 & |\ \ 0 & 1
\end{pmatrix}\Rightarrow
\begin{pmatrix}
5 & 5 & |\ \ \ \ \ \ 1 & 0\\
0 & 1 & |\ -1 & 1
\end{pmatrix}\Rightarrow
\begin{pmatrix}
1 & 1 & |\ \ \ \ \ \ \frac{1}{5} & 0\\
0 & 1 & |\ -1 & 1
\end{pmatrix}\Rightarrow
\begin{pmatrix}
1 & 0 & |\ \ \ \ \ \ \frac{6}{5} & -1\\
0 & 1 & |\ -1 & 1
\end{pmatrix}
$$

### $$A{A}'$$

$$
A=\begin{pmatrix}
 1 &1 \\ 
 0 &1 \\ 
 2 &2
\end{pmatrix}\Rightarrow
{A}'=\begin{pmatrix}
 1 &0 &2 \\ 
 1 &1 &2 
\end{pmatrix}
$$

$$
A{A}'=\begin{pmatrix}
 1 &1 \\ 
 0 &1 \\ 
 2 &2
\end{pmatrix}\begin{pmatrix}
 1 &0 &2 \\ 
 1 &1 &2 
\end{pmatrix}=
\begin{pmatrix}
1*1+1*1 &1*0+1*1 &1*2+1*2 \\
0*1+1*1 &0*0+1*1 &0*2+1*2 \\
2*1+2*1 &2*0+2*1 &2*2+2*2
\end{pmatrix}=
\begin{pmatrix}
2 &1 &4 \\
1 &1 &2 \\
4 &2 &8
\end{pmatrix}
$$

### Determinante $$A{A}'$$

$$
A{A}'=
\begin{pmatrix}
2 &1 &4 \\
1 &1 &2 \\
4 &2 &8
\end{pmatrix}
$$

$$
\left | A{A}' \right | =
\left | 
\begin{matrix}
2 &1 &4 \\
1 &1 &2 \\
4 &2 &8
\end{matrix}
\right | =
2*1*8+1*2*4+2*1*4-(4*1*4+2*2*2+1*1*8)
$$

$$
=16+8+8-(16+8+8)=32-32=0
$$

### Traza $$A{A}'$$

$$
A{A}'=
\begin{pmatrix}
2 &1 &4 \\
1 &1 &2 \\
4 &2 &8
\end{pmatrix}
$$

$$
tr(A{A}')=
tr\begin{pmatrix}
2 &1 &4 \\
1 &1 &2 \\
4 &2 &8
\end{pmatrix}=2+1+8=11
$$

### Inversa $$A{A}'$$

$$
\left | A{A}' \right | = 0 \Rightarrow A{A}'\ \text{no tiene inversa}
$$

## 2.

## 3.

###  Calcule los valores y los vectores propios de A y de su inversa

$$ A =
\begin{pmatrix}
2 &1 \\
1 &2 
\end{pmatrix}
\ \ \ \ \ \ 
A^{-1} =
\begin{pmatrix}
\frac{2}{3} &\frac{-1}{3} \\
\frac{-1}{3} &\frac{2}{3}
\end{pmatrix}
$$

Valores y los vectores propios de A:

$$\left | A-\lambda I \right | = 0 \Rightarrow$$

$$
\left |
\begin{pmatrix}
2 &1 \\
1 &2 
\end{pmatrix}-
\begin{pmatrix}
\lambda &0 \\
0 &\lambda
\end{pmatrix}
\right |=0\Rightarrow
$$

$$
\left |
\begin{matrix}
2-\lambda &1 \\
1 &2-\lambda
\end{matrix}
\right | = (2-\lambda)^2-1\Rightarrow
\left\{\begin{matrix}
\lambda_{1}\rightarrow &1 \\
\lambda_{2}\rightarrow &3
\end{matrix}\right.
$$

$$\text{valores propios de }A=\{1,3\}$$