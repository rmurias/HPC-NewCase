
```pseudo
    \begin{algorithm}
    \caption{Quicksort}
    \begin{algorithmic}
    \Comment{This is a test}
      \Procedure{Quicksort}{$A, p, r$}
        \If{$p < r$}
          \State $q \gets $ \Call{Partition}{$A, p, r$}
          \State \Call{myThing}{$A, p, q - 1, c, d, e, f$}
          \State \Call{Quicksort}{$A, q + 1, r$}
          \State $i \gets pstuff$
        \EndIf
      \EndProcedure
      \Function{MyThing}{$ \\
		      \hspace*{1em}A, \\
		      \hspace*{1em}p, \\
		      \hspace*{1em}q - 1, \\
		      \hspace*{1em}c, \\
		      \hspace*{1em}d, \\
		      \hspace*{1em}e, \\
		      \hspace*{1em}f$}
        \State $x \gets A[r]$
        \State $i \gets p - 1$
        \For{$j \gets p$ \To $r - 1$}
          \If{$A[j] < x$}
            \State $i \gets i + 1$
            \State exchange
            $A[i]$ with $A[j]$
          \EndIf
        \State exchange $A[i]$ with $A[r]$
        \EndFor
		\ForAll{$p_i$ in $P$}
		    \State $d_{exp} \gets$ get\_data($p_i$, $X_{d_{exp}}$)
		\EndFor 
      \EndFunction
      \end{algorithmic}
    \end{algorithm}
```
