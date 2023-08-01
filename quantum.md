## Overview

We use probability ampltide which have both magnitudes and a direction (phase). Probability amplitudes have two components and we often write that as complex numbers. We chose to use complex numbers rather than some other system because of the ease of manipulating the phases of complex numbers. If you plot complex number you can notice that a multiplication by $-1$ reflects across the x and y axis and a mutliplcation by $i$ rotates 90 degrees counter clockwise.

Our complex number will have a magnitude (more often called an amplitude in this context) and a phase. The magnitude is not necessarily the probability that an event will happen. The probability of an event happening is actually the square off the amplitude. That means that something that has a 50% chance of happening has a probability amplitude of $\frac{\sqrt{2}}{2}$

A complex number has two components a real portion and an imaginary portion. The state of our qubit $\psi$ can be written as a superposition between the two possible states (either a 0 or 1):

$$\vert \psi \rangle = a_0 \vert 0 \rangle +  a_1 \vert 1 \rangle $$

In the definition above $a_0$ and $a_1$ are the probability amplitudes of getting 0 and 1 respectively. While, the $\vert 0 \rangle$ refers to a qubit in the zero state and $\vert 1 \rangle a qubit in the one state. A qubit with an equal chance to be either in the 0 or 1 state would look like the following:
$$\vert \psi \rangle = \frac{1}{\sqrt{2}} \vert 0 \rangle + \frac{1}{\sqrt{2}} \vert 1 \rangle$$

We can obviously have systems with more that one qubit. In a single qubit there was two possible states $\vert 0 \rangle$ and $\vert 1 \rangle$. If you have two qubits there are four states $\vert 00 \rangle$, $\vert 01 \rangle$, $\vert 10 \rangle$, and $\vert 11 \rangle$. If you have three qubits you would have eight different states. In general for a system of n qubits you have $2^n$ different possible states. Much like the single qubit state we can also write a two qubit state as superposition of all possible measurements (the four listed previously):

$$\vert x \rangle = a_{00} \vert 00 \rangle + a_{01} \vert 01 \rangle + a_{10} \vert 10 \rangle + a_{11} \vert 11 \rangle $$
 
Before continuing its important to note that if we wanted to given allocate an equal probabilty to every state we would not make all the coefficients $\frac{1}{\sqrt{2}}$. If we assign $\frac{1}{\sqrt{2}}$ to our four qubits and we add up all the probabilities we get $4(\frac{1}{\sqrt{2}})^2$ which is equal two. That doesn't make very much sense. Our probabilities are adding up to 200% when they should always be adding up to 100% . In order to give all our states the same possible outcome chance (25%) we would make each coefficent $\frac{1}{2}$ so that way the sum of all probabilities is exactly one.

$$\vert x \rangle = \frac{1}{2} \vert 00 \rangle + \frac{1}{2} \vert 01 \rangle + \frac{1}{2} \vert 10 \rangle + \frac{1}{2} \vert 11 \rangle $$

## Gates

In quantum computing gates can act on these qubits. Some gates operate on a singular bit while other gates operate of a pair/group of bits. Gates can be written as a matrix multiplication or a trasnsformation on the original qubit.

For a single qubit I will often write it in column notation (where $a_0$ and $a_1$ represent the probability amplitudes)
```math
A = \begin{vmatrix}
a_0 \\
a_1
\end{vmatrix}
```
That means that for a qubit which is always in the zero state we have the following column vector
```math
A = \begin{vmatrix}
1 \\
0
\end{vmatrix}
```
or always in the one state 
```math
A = \begin{vmatrix}
0 \\
1
\end{vmatrix}
```

**X Gate**

The most common gate is the X-gate (a NOT/INVERTER gate). The X-gate wil work on a singule qubit. The X-gate will simply swap the state of the qubit. If a qubit is in the zero state it will be swapped to the one state. If a qubit is in the one state it will be swapped to the zero state. The matrix represnetation of the x-gate is the following:

X = ```math
A = \begin{vmatrix}
0 & 1 \\
1 & 0 
\end{vmatrix}
```

Below we can show that through matrix multiplication we can prove that the X-gate will cause $\vert 0 \rangle \implies \vert 1 \rangle$  and $\vert 1 \rangle \implies \vert 0 \rangle$.

``` math
$\vert 0 \rangle \implies \vert 1 \rangle$ \quad
begin{vmatrix}
0 & 1 \\
1 & 0 
\end{vmatrix}
begin{vmatrix}
1 \\
0 
\end{vmatrix}
=
begin{vmatrix}
0 \\
1 
\end{vmatrix}
```
$$a_0 = (0)(1) + (1)(0) = 0$$
$$a_1 = (1)(1) + (0)(1)$$