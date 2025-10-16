Tags: [[Analisi 2 e Probabilità]]

# Calcolo Combinatorio
### Permutazioni
Le permutazioni (semplici) di un gruppo di $n$ elementi distinti sono le sequenze ordinate degli $n$ oggetti
$$\text{Permutazioni di un insieme di }n\text{ elementi} = n!$$
Se sono presenti elementi indistinguibli:
$$\frac{n!}{n_1!n_2!\ldots}$$ $n_i$ rappresenta il numero di elementi uguali tra di loro.
### Disposizioni
La disposizione (semplice) di $n$ elementi di classe $k$ ($0\le k\le n$) è ogni sottoinsieme ordinato di $k$ elementi diversi tra loro selezionati da un insieme avente $n$ elementi.
Due disposizioni sono diverse se cambia almeno uno degli elementi oppure se gli stessi elementi compaiono in ordine differente (l'ordine conta)
$$\text{Disposizioni di }n\text{ elementi di classe }k = \frac{n!}{(n-k)!}$$
### Combinazioni
Una combinazione (semplice) di $n$ elementi di classe $k$ ($0\le k\le n$) è ogni sottoinsieme di $k$ elementi distinti estratti da un insieme di partenza di $n$ element (non conta l'ordine) 
$$\text{Combinazioni di }n\text{ elementi di classe }k = \frac{n!}{k!(n-k)!}=\begin{pmatrix}
n \\
 k
\end{pmatrix}$$
