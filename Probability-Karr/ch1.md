# Chapter 1. Probability
---

## Exercise 1.1
Prove _de Morgan's law_:

$$(A\cup B)^c=A^c\cap B^c$$

and

$$(A\cap B)^c=A^c\cup B^c$$

both directly and using indicator functions.

### Solution
Let's prove $(A\cup B)^c=A^c\cap B^c$, then $(A\cap B)^c=A^c\cup B^c$ can be proved in a similar way.

**Directly**

Part 1 - $\subseteq$

For an element $x\in(A\cup B)^c$, then $x\notin A\cup B=\{y | y\in A \vee y\in B\}$. In this case, $x\notin A$ and $x\notin B$, that is $x\in A^c$ and $x\in B^c$. Hence, $x\in A^c\cap B^c$. Given that this holds for all $x\in(A\cup B)^c$, we have $(A\cup B)^c \subseteq A^c\cap B^c$.

Part 2 - $\supseteq$

For an element $x\in A^c\cap B^c$, it means $x\in A^c$ and $x\in B^c$. In this case, $x\notin A$ and $x\notin B$, hence $x\notin A\cup B$ by definition. Therefore, $x\in (A\cup B)^c$. Given that this holds for all $x\in A^c\cap B^c$, we have $(A\cup B)^c \supseteq A^c\cap B^c$.


**Indicator functions**

$$\begin{align*}
{\bf 1}_{(A\cup B)^c} &= 1 - {\bf 1}_{A\cup B} \\
  &= 1 - \max\{{\bf 1}_{A}, {\bf 1}_{B}\} \\
  &= \min\{1-{\bf 1}_{A}, 1-{\bf 1}_{B}\} \\
  &= \min\{{\bf 1}_{A^c}, {\bf 1}_{B^c}\} \\
  &= {\bf 1}_{A^c\cap B^c}
\end{align*}$$


## Exercise 1.2
Prove that for events $A$ and $B$, $A\Delta B = A^c \Delta B^c$.

### Solution
By definition,

$$\begin{align*}
A\Delta B &= A\setminus B + B\setminus A \\
  &= A\cap B^c + B\cap A^c \\
  &= A^c \cap (B^c)^c + B^c \cap (A^c)^c \\
  &= A^c\setminus B^c + B^c\setminus A^c \\
  &= A^c\Delta B^c
\end{align*}$$


## Exercise 1.3
Let $B$ and $C$ be events $(A_n)$ and let $A_n=B$ if $n$ is odd and $A_n=C$ if $n$ is even. Calculate $\limsup_{n} A_n$ and $\liminf_{n} A_n$.

### Solution
Intuitively, while $n$ goes to $\infty$, $\limsup_{n} A_n$ is the set where $A_n$ will "never leave forever", and $\liminf_{n} A_n$ is the set where $A_n$ will "eventually stay forever". Since $A_n$ is alternating between $B$ and $C$, $\limsup_{n} A_n = B\cup C$ and $\liminf_{n} A_n = B\cap C$.

Now, let's prove it. By definition,

$$\begin{align*}
\limsup_n A_n &= \bigcap_{k=1}^\infty\bigcup_{n=k}^\infty A_n \\
  &= \bigcap_{k=1}^\infty(\bigcup_{n=2k-1}^{\infty}A_n\cup \bigcup_{n=2k}^{\infty}A_n\big) \\
  &= \bigcap_{k=1}^\infty (B\cup C) \\
  &= B \cup C
\end{align*}$$

And,

$$\begin{align*}
\liminf_n A_n &= \bigcup_{k=1}^\infty\bigcap_{n=k}^\infty A_n \\
  &= \bigcup_{k=1}^\infty(\bigcap_{n=2k-1}^{\infty}A_n\cap \bigcap_{n=2k}^{\infty}A_n\big) \\
  &= \bigcup_{k=1}^\infty (B\cap C) \\
  &= B \cap C
\end{align*}$$


## Exerpcise 1.4
Prove part b) of proposition 1.9: Let $A_1,A_2,\ldots$ be subsets of $\Omega$. If $A_1\supseteq A_2\supseteq \cdots$, then $A_n\to A=\cap_{n=1}^\infty A_n$. (This is written as $A_n\downarrow A$)

### Solution
Let $A=\cap_{n=1}^\infty A_n$. To prove $A_n\to A$, we can show 1\) $\liminf_n A_n = A$, and 2\) $\limsup_n A_n = A$.

1\) Given $A_1\supseteq A_2\supseteq \cdots$, for each $k$, $\cap_{n=k}^\infty A_n=A$. Hence by definition,

$$ \liminf_n A_n = \bigcup_{k=1}^\infty\bigcap_{n=k}^\infty A_n=\bigcup_{k=1}^\infty A = A .$$

2\) On the other hand, for each $k$, $\cup_{n=k}^\infty A_n = A_k$, by definition,

$$ \limsup_n A_n = \bigcap_{k=1}^\infty\bigcup_{n=k}^\infty A_n = \bigcap_{k=1}^\infty A_k = A .$$

