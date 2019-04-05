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
$
\Rightarrow
\begin{pmatrix}
5 & 5 & \vline 1 & 0\\
5 & 6 & \vline 0 & 1
\end{pmatrix}
$


### Determinante $$A{A}'$$

### Traza $$A{A}'$$

### Inversa $$A{A}'$$