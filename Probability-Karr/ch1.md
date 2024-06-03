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

