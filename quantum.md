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
A = \begin{bmatrix}
a_0 \\
a_1
\end{bmatrix}
```
That means that for a qubit which is always in the zero state we have the following column vector
```math
A = \begin{bmatrix}
1 \\
0
\end{bmatrix}
```
or always in the one state 
```math
A = \begin{bmatrix}
0 \\
1
\end{bmatrix}
```

**X Gate**

The most common gate is the X-gate (a NOT/INVERTER gate). The X-gate wil work on a singule qubit. The X-gate will simply swap the state of the qubit. If a qubit is in the zero state it will be swapped to the one state. If a qubit is in the one state it will be swapped to the zero state. The matrix represnetation of the x-gate is the following:

```math
X = \begin{bmatrix}
0 & 1 \\
1 & 0 
\end{bmatrix}
```

Below we can show that through matrix multiplication we can prove that the X-gate will cause $\vert 0 \rangle \implies \vert 1 \rangle$  and $\vert 1 \rangle \implies \vert 0 \rangle$.

```math
\vert 0 \rangle \implies \vert 1 \rangle \quad
\begin{bmatrix}
0 & 1 \\
1 & 0 
\end{bmatrix}
\begin{bmatrix}
1 \\
0 
\end{bmatrix}
=
\begin{bmatrix}
0 \\
1 
\end{bmatrix}
```

$$a_0 = (0)(1) + (1)(0) = 0$$

$$a_1 = (1)(1) + (0)(1) = 1$$


```math
\vert 1 \rangle \implies \vert 0 \rangle \quad
\begin{bmatrix}
0 & 1 \\
1 & 0 
\end{bmatrix}
\begin{bmatrix}
0 \\
1 
\end{bmatrix}
=
\begin{bmatrix}
1 \\
0 
\end{bmatrix}
```

$$a_0 = (0)(0) + (1)(1) = 1$$

$$a_1 = (1)(0) + (0)(1)$$


**Z-Gate** 

The Z-gate is another simple unitary opertation. All the z-gate does is it changes the sign of the of the probability amplitude of a qubit being in $\vert 1 \rangle$. The matrix representation is following:

```math
Z = \begin{bmatrix}
1 & 0 \\
0 & -1 
\end{bmatrix}
```

The Z-gate rotates the probability vector over by $\pi$. The Z-gate isn't important right now, but it will be when we get to entangled states.

**H - Gate**

We been talking about a lot of scenarios that have a 100% of being a single outcome. How do we make a single qubit exist in a state where it has a mulitude of outcomes. Consider the H-Gate which has the following the matrix definition:


```math
H = \frac{1}{\sqrt{2}}\begin{bmatrix}
1 & 1 \\
1 & -1 
\end{bmatrix}
```

Noitce the factor of $\frac{1}{\sqrt{2}}$ on the outside. Remeber that the total sum of probabilities of a qubit must be one, and transformation should not alter that fact the factor on the outside "noramlizes" the transformation. Notice what happens when the H-Gate is applied onto a qubit in the zeroth state:

```math
\frac{1}{\sqrt{2}}\begin{bmatrix}
1 & 1 \\
1 & -1 
\end{bmatrix}
\begin{bmatrix}
1 \\
0
\end{bmatrix}
= \frac{1}{\sqrt{2}} \vert 0 \rangle + \frac{1}{\sqrt{2}} \vert 1 \rangle
```
The H-gate gate will turn a qubit in a zero "deterministic" state into a probabilistic state. When measured it has a 50% chance to be 0 and a 50% chance to be a 1.  Now consider what happens when the H-gate operates on a qubit with the a 1 state.

```math
\frac{1}{\sqrt{2}}\begin{bmatrix}
1 & 1 \\
1 & -1 
\end{bmatrix}
\begin{bmatrix}
0 \\
1
\end{bmatrix}
= \frac{1}{\sqrt{2}} \vert 0 \rangle + -\frac{1}{\sqrt{2}} \vert 1 \rangle
```
Since probability is the sum of the squares of the amplitudes the qubit still has a 50% chance of being a 0 and a 50% chance to be a 1. The only difference between the scenario with $\vert 1 \rangle$ and $\vert 0 \rangle$ is that in this case the phase was rotated by a factor of $\pi$. The fact that the phase shifted slightly will help describe the behavior when we link two H-gates together. Refer to the following:

```math
\frac{1}{2}
\begin{bmatrix}
1 & 1 \\
1 & -1 
\end{bmatrix}
\begin{bmatrix}
1 & 1 \\
1 & -1 
\end{bmatrix}
=
\begin{bmatrix}
0 & 1 \\
1 & 0 
\end{bmatrix}
```
If we combine two H-gates together we end up with the same matrix operation as an X-gate. That means the two h-gates diretly after each other will just swap the state of the qubit ($\vert 0 \rangle \implies \vert 1 \rangle, \vert 1 \rangle \implies \vert 0 \rangle $). The offset phases from the first H-gate are what causes this cancellation leading to a non-probabilistic output.

**Controlled Not Gate (CNOT)**

Controlled gates take in a pair of qubits rather than just a singular qubit. In a controlled gate one of the qubits is a control and one is a target. The control qubit won't change and will instead act as a "trigger" for whhat the target qubit to should change to. You may have noticed that all operation that happen on a single qubit are 2x2 matrices which should make sense if you draw out what exactly each entry is doing. Each entry is describing a different possible scenario refer to the 2x2 matrix below:

```math
\begin{bmatrix}
a_{0 \implies 0} & a_{0 \implies 1} \\
a_{1 \implies 0} & a_{1 \implies 1} 
\end{bmatrix}
```
Each entry controls a different possible input and its corresponding output. It should be pretty intuitive that an n qubit will require a $2^n \times 2^n$ to cover all possbible input combination. Below is a generic 4x4 matrix operation:
```math
\begin{bmatrix}
a_{00 \implies 00} & a_{01 \implies 00} & a_{10 \implies 00} & a_{11 \implies 00} \\
a_{00 \implies 01} & a_{01 \implies 01} & a_{10 \implies 01} & a_{11 \implies 01} \\
a_{00 \implies 10} & a_{01 \implies 10} & a_{10 \implies 10} & a_{11 \implies 10} \\
a_{00 \implies 11} & a_{01 \implies 11} & a_{10 \implies 11} & a_{11 \implies 11} \\
\end{bmatrix}
```
The matrix definition for a controlled not gate is the following:
```math
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 
\end{bmatrix}
```

That is a 4x4 matrix, so it would only make sense to multiply it against a 4x1 vector. We can express a two qubits all possible qunaities as either a column vector or a sum like the following:

```math
\vert X \rangle =
\begin{bmatrix}
a_{00} \\
a_{01} \\
a_{10} \\
a_{11} 
\end{bmatrix}
= a_{00} \vert 00 \rangle + a_{01} \vert 01 \rangle + a_{10}  \vert 10 \rangle + a_{11} \vert 11 \rangle
```

Lets pass a generic two qubit state $\vert X \rangle$ through a controlled not gate. Lets assume that the qubit in the rightmost most position is the control bit and the qubit in the left is the target qubit (the thing actually changing) :

```math
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 
\end{bmatrix}
\begin{bmatrix}
a_{00} \\
a_{01} \\
a_{10} \\
a_{11} 
\end{bmatrix}
=
\begin{bmatrix}
a_{00} \\
a_{11} \\
a_{10} \\
a_{01}  
\end{bmatrix}
```
The controlled not gate has the effect of making $a_{01} \implies a_{11}$ and $a_{11} \implies a_{01}$. The Controlled Not gate works as a X-gate (NOT gate) on a target gate, but only when controlled bit is in 1 state. Also note that when we apply to CNOT gates in sequence we end up with an identitiy matrix which means it equivaelnt to no operation at all
```math
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 
\end{bmatrix}
=
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 
\end{bmatrix}
```

## Entanglement

Refer to the following probability amplitude of a pair of qubits.
```math
\vert X \rangle = \begin{bmatrix}
0 \\
\frac{1}{\sqrt{2}} \\
0 \\
\frac{1}{\sqrt{2}} 
\end{bmatrix} = \frac{1}{\sqrt{2}} \vert 01 \rangle + \frac{1}{\sqrt{2}} \vert 11 \rangle
```

You may have noticed that we can actual describe this pair of bits as two seperate qubits with there own probabilities. The two possible states are $\vert 01 \rangle$ and $\vert 11 \rangle$. Notice that the zeroth qubit is always one, so we can represent it as own qubit:
```math
\vert X_0 \rangle = \begin{bmatrix}
0 \\
1
\end{bmatrix}
```
Since the zeroth qubit is always one and the probability of getting  $\vert 01 \rangle$ and $\vert 11 \rangle$ is 50% that implies that qubit one must have the following state
```math
\vert X_1 \rangle = \begin{bmatrix}
\frac{1}{\sqrt{2}} \\
\frac{1}{\sqrt{2}}
\end{bmatrix}
```

We have successfully broken up our pair into two seperate qubits with there own probabilities. In other words, each qubit is independent and does not require input from the other qubit. This scenario is called a product state where the possiblites can be written as the product of two INDEPENDENT qubit probabilities. We define product between two qubits as following:

```math
\vert ba \rangle = \begin{bmatrix}
b_0a_0 \\
b_0a_1 \\
b_1a_0 \\
b_1 a_2
\end{bmatrix} 
```

Notice that if we combine the two indivudal results for the qubits we get the original 4x1 state vector.
```math
\vert X \rangle = \begin{bmatrix}
0(\frac{1}{\sqrt{2}}) \\
1(\frac{1}{\sqrt{2}}) \\
0 (\frac{1}{\sqrt{2}})\\
1(\frac{1}{\sqrt{2}})
\end{bmatrix}
=
\begin{bmatrix}
0 \\
\frac{1}{\sqrt{2}} \\
0\\
\frac{1}{\sqrt{2}}
\end{bmatrix}
```

Now consider a the following scenario and try to break it up into two seperate indepdent qubit probability amplitudes

```math
\vert \phi_{+} \rangle =  \begin{bmatrix}
\frac{1}{\sqrt{2}} \\
0 \\
0 \\
\frac{1}{\sqrt{2}}
\end{bmatrix} 
```

If tried you tried a little you probably realized that its not actually possible to break this up into two indepdent qubits states. As a pair each qubit has a possiblity to be zero or a one. However, if each qubit individually had the ability to be a 0 or 1 we would have the following vector:
```math
 \begin{bmatrix}
\frac{1}{2} \\
\frac{1}{2}  \\
\frac{1}{2}  \\
\frac{1}{2}
\end{bmatrix} 
```

It's impossible to write as a product state and thus we call this scenario an entangled state. The qubits in some way rely on each other. The state of one qubit can't be confimed without the state of the other qubit. You may regonize that gates that act on a single qubit won't cause a pair of qubits to become entangled. However, gates that act on multiple qubits like the controlled not gate will cause bits to become entangled. 

**Bell Basis**

A 2 qubit pair is a vector in 4-dimensional hilbert space. The bell basis is a common basis for the hilbert space. The four basis vectors are the "maximally entangled" states and every possible 2 qubit pair can be described as a super position of them. The four maximally entangled states / bell basis vectors are the following:

$$\vert \phi_{+} \rangle = \frac{1}{\sqrt{2}} \vert 00 \rangle + \frac{1}{\sqrt{2}} \vert 11 \rangle$$

$$\vert \phi_{-} \rangle = \frac{1}{\sqrt{2}} \vert 00 \rangle - \frac{1}{\sqrt{2}} \vert 11 \rangle$$

$$\vert \psi_{+} \rangle = \frac{1}{\sqrt{2}} \vert 01 \rangle + \frac{1}{\sqrt{2}} \vert 10 \rangle$$

$$\vert \psi_{-} \rangle = \frac{1}{\sqrt{2}} \vert 01 \rangle - \frac{1}{\sqrt{2}} \vert 10 \rangle$$

One of the key properties of the bell basis is when they are passed through a very specific circuit called the bell analyzer. You probably know that qubits can be measured it turns out that when you measure the two qubits present in each bell basis vector they will always give a distinct answer. The bell analyzer circuit looks like the following:

<img src="https://github.com/sackn/diffeq/blob/main/Images/quantum/image2.png" alt="bell analyzer">

For each of the bell basis they have a certain classical output after passing through the bell analyzer:
- $\vert \phi_{+} \rangle \implies \text{m0 = 0, m1 = 0}$
- $\vert \phi_{-} \rangle \implies \text{m0 = 1, m1 = 0}$
- $\vert \psi_{+} \rangle \implies \text{m0 = 0, m1 = 1}$
- $\vert \psi_{-} \rangle \implies \text{m0 = 1, m1 = 1}$

If you don't trust me just telling you you can run through the matrix algebra. Take the $\vert \phi_{-} \rangle$. First pass is through a controlled not gate which effectively untangles the pair of qubits:
```math
\frac{1}{\sqrt{2}}
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 
\end{bmatrix}
\begin{bmatrix}
1 \\
0 \\
0 \\
-1
\end{bmatrix}
=
\begin{bmatrix}
\frac{1}{\sqrt{2}} \\
-\frac{1}{\sqrt{2}} \\
0 \\
0
\end{bmatrix}
```
Now that the qubits are untangled we can properly write this pair probability amplitude as two seperate indepdent qubits of the following:
```math
\vert X_0 \rangle = 
\begin{bmatrix}
\frac{1}{\sqrt{2}} \\ 
-\frac{1}{\sqrt{2}}
\end{bmatrix}
\qquad
\vert X_1 \rangle = 
\begin{bmatrix}
0 \\
1
\end{bmatrix}
```
We know that $\vert X_1 \rangle$ will always be a one and thus $m_1 = 1$.To find the classical value of the other qubit we need to pass $\vert X_0 \rangle$ through a H-gate. 
```math
\frac{1}{2}
\begin{bmatrix}
1 & 1 \\
1 & -1
\end{bmatrix}
\begin{bmatrix}
1 \\
-1
\end{bmatrix}
=
\begin{bmatrix}
1 \\
0
\end{bmatrix}
```
After passing the zeroth qubit through a H-gate we geta deterministic result. $\vert X_0 \rangle$ will always evalulate to zero and thus $m_0$ = 0. In total,
$$\vert \phi_{-} \rangle \implies \text{m0 = 1, m1 = 0}$$

We are able to analyze things that maximally entangled, but how do we even get to this point in the first place. We can reach one of these four states by starting off with the following circuit:

<img src="https://github.com/sackn/diffeq/blob/main/Images/quantum/image3.png" alt="Entangled State 1">

If you run through all the math you will notice that this specific circuit will yield the maximally entangled state $\vert \phi_{+} \rangle$. From the state $\vert \phi_{+} \rangle$ it is possible to reach all other maximally entangled scenarios through unitary operators (the x-gate and z-gate discussed earlier) to the first qubit. For example to obtain the maximally entangled state $\vert \phi_{- } \rangle$ the circuit would look like:
<img src="https://github.com/sackn/diffeq/blob/main/Images/quantum/image4.png" alt="Entangled State 2">

For $\vert \psi_{+} \rangle$
<img src="https://github.com/sackn/diffeq/blob/main/Images/quantum/image4.png" alt="Entangled State 3">

For $\vert \psi_{-} \rangle$
<img src="https://github.com/sackn/diffeq/blob/main/Images/quantum/image4.png" alt="Entangled State 4">

I'm going to run through the matrix algebra for the $\vert \psi_{-} \rangle$ scenario. Both qubit initially start in the zero state. The zeroth qubit is then passed through an H-gate yielding:
```math
\frac{1}{\sqrt{2}}
\begin{bmatrix}
1 & 1 \\
1 & -1
\end{bmatrix}
\begin{bmatrix}
1 \\
0
\end{bmatrix}
\implies
\vert X_0 \rangle =
\begin{bmatrix}
\frac{1}{\sqrt{2}} \\
\frac{1}{\sqrt{2}}
\end{bmatrix}
```
Combining this with the other qubit we get the pair state. Passing it through a controlled not gate we get:
```math
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 
\end{bmatrix}
\begin{bmatrix}
\frac{1}{\sqrt{2}} \\
\frac{1}{\sqrt{2}}  \\
0\\
0
\end{bmatrix}
=
\begin{bmatrix}
\frac{1}{\sqrt{2}} \\
0 \\
0\\
\frac{1}{\sqrt{2}}
\end{bmatrix}
```
Applying a modified z-gate such that the only the $\vert 11 \rangle$ becomes negative we get:
```math
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & -1
\end{bmatrix}
\begin{bmatrix}
\frac{1}{\sqrt{2}} \\
0 \\
0\\
\frac{1}{\sqrt{2}}
\end{bmatrix}
=
\begin{bmatrix}
\frac{1}{\sqrt{2}} \\
0 \\
0\\
-\frac{1}{\sqrt{2}}
\end{bmatrix}
```
As a sidenote before continuing you might have realize on our path to get to $\vert \psi_{-} \rangle$ we created the $\vert \phi_{+} \rangle$. Now apply a modified z-gate to our output:
```math

\begin{bmatrix}
0 & 1 & 0 & 0 \\
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0
\end{bmatrix}
\begin{bmatrix}
\frac{1}{\sqrt{2}} \\
0 \\
0\\
-\frac{1}{\sqrt{2}}
\end{bmatrix}
=
\begin{bmatrix}
0 \\
\frac{1}{\sqrt{2}} \\
-\frac{1}{\sqrt{2}} \\
0
\end{bmatrix}
```
 We finally obtains the $\vert \psi_{-} \rangle$ state which has the superposition $\frac{1}{\sqrt{2}} \vert 01 \rangle - \frac{1}{\sqrt{2}}\vert 10 \rangle$. Since we were using linear operations we really could have done this all in one step by combining all of our gates starting from the controlled not gate all in a singular matrix operation by multiplying them all together and then operating on our pair of qubits:

 ```math
\begin{bmatrix}
0 & 1 & 0 & 0 \\
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & -1
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 
\end{bmatrix} 
=
\begin{bmatrix}
0 & 0 & 0 & 1 \\
1 & 0 & 0 & 0 \\
0 & -1 & 0 & 0 \\
0 & 0 & 1 & 0
\end{bmatrix}
```

```math
\begin{bmatrix}
0 & 0 & 0 & 1 \\
1 & 0 & 0 & 0 \\
0 & -1 & 0 & 0 \\
0 & 0 & 1 & 0
\end{bmatrix}
\begin{bmatrix}
1 \\
1\\
0\\
0
\end{bmatrix}
=
\begin{bmatrix}
0\\
1\\
-1\\
0
\end{bmatrix} = \vert \psi_{-} \rangle
```

### Superdense Coding

Superdense coding relies on the capabilities of the bell basis vectors and entanglement. In superdense coding it is possible to use a singular qubit to send two classical bits worth of information. Observe the circuit digram that I stole from this video (which I do not own obviously): [https://www.youtube.com/watch?v=UrAZHBwIAFQ](url)
<img src="https://github.com/sackn/diffeq/blob/main/Images/quantum/image7.png" alt="Entangled State 4">

In the above scenario Bob wishes to send a message to Alice. Alice is aware of this and she generates two qubits and she entangles them (using the h-gate and controlled not). Now the qubits are entangled she hands only one of th qubit to Bob. Bob then encodes this qubit then sends is back to Alice. Alice will then take her qubit from earlier and the qubit she got from Bob and will be able to decipher the message. She will get a total of two classical bits of information despite the fact that Bob only ever saw/edited one of the qubits. 

If we bring this back to what we learned earlier. Effectively Alice and Bob first create an entangled pair and then Bob uses unitary operation on his qubit in order to get encodes his message. That involves swapping to one of the four different vectors in the bell basis $\vert \phi_{+}\rangle$,  $\vert \phi_{-}\rangle$, $\vert \psi_{+}\rangle$, or $\vert \psi_{-}\rangle$. Bob knows that if he choose a specific maximally entangled pair that Alice will be able to untangle them through the use of a bell analyzer (discussed earlier). Depending on the input to the bell analyzer it will always output a UNIQUE classical binary string for each maximally entangled pair possiblity. 

For example if Bob causes the maximally entangled pair to be $\vert \psi_{+} \rangle = \frac{1}{\sqrt{2}}(\vert 01 \rangle + \vert 10 \rangle)$, Alice will decipher the classical bits $m_0 = 0$ and $m_1 = 1$. If you forgot what bell basis corresponds to which classical output:
- $\vert \phi_{+} \rangle \implies \text{m0 = 0, m1 = 0}$
- $\vert \phi_{-} \rangle \implies \text{m0 = 1, m1 = 0}$
- $\vert \psi_{+} \rangle \implies \text{m0 = 0, m1 = 1}$
- $\vert \psi_{-} \rangle \implies \text{m0 = 1, m1 = 1}$

### Uncertainity Principle

Before getting to the uncertainity principle I want to introduce another gate that will help with a futur example. I present Ry gate which effectively rotates your qubits state by some $\theta$. The Ry gate has the following matrix definition:
```math
\begin{bmatrix}
cos(\frac{\theta}{2}) & -sin(\frac{\theta}{2}) \\
sin(\frac{\theta}{2}) & cos(\frac{\theta}{2})
\end{bmatrix}
```

The uncertainity principle states that for some pairs of properties it is impossible to know both with certainity. More specifically the more certain you are about a single property the less certain you are about the other property. For example consider two different wayas to measure a qubit (call one x-measurement and other z-measurement):
<img src="https://github.com/sackn/diffeq/blob/main/Images/quantum/image8.png" alt="Entangled State 4">

Notice that we know the x-measurement is going to be zero with a 100% certainity while the z-measurement is a complete 50/50 between 0 and 1. 

More formally define the following for a certain measurement method:
$$\langle X \rangle = P_x(0) - P_x(1)$$
Read out in English: The expected value of X is the difference between the proability of being zero and the probability of it being 1. We can have any values between -1 and 1. A certain zero will be a 1 and a certain one will be a -1. However, if know for certain either its a 0 or a 1 then we know that $\langle X \rangle^2$ is 1. If we define something similar in the case of $\langle Z \rangle$ the uncertainity principle can be written as the following inequliaty:
$$\langle X \rangle^{2} + \langle Z \rangle^2 \leq 1$$
It formally describes that if you know X for certain you know nothing about Z. The more you know about one thing the less you know about other thing. Consider these adjusted X-measurement and Z-measurements where I just tacked on a H-gate to them:
<img src="https://github.com/sackn/diffeq/blob/main/Images/quantum/image9.png" alt="Entangled State 4">
Notice that we can now have no clue about the x-measurement and we know the z-measurement for certain thus maintaing the uncertainity principle. This will hold regarldess of what operations come prior to the x-measurements and z-measurements, the uncertain principle is something fundamnental.

Lets consider the following gates to be our x-measurement and our z-measurement. According to the uncertainity principle the following relationship should hold $\langle X \rangle^{2} + \langle Z \rangle^2 \leq 1$
<img src="https://github.com/sackn/diffeq/blob/main/Images/quantum/image10.png" alt="Entangled State 4">

First looking at the x-measurement we can calculate its probability by first applying the $\frac{\pi}{5}$ through the use of a Ry gate giving us the following:
```math
\begin{bmatrix}
cos(\frac{\pi}{10}) & -sin(\frac{\pi}{10}) \\
sin(\frac{\pi}{10}) & cos(\frac{\pi}{10})
\end{bmatrix}
\begin{bmatrix}
1 \\
0
\end{bmatrix}
=
\begin{bmatrix}
0.9511 \\
0.3090
\end{bmatrix}
```

The first component is the probability amplitude of getting a zero and the second component is the probabiity amplitude of getting a one. We can square these values to get the classical definition probability for 0 and 1.
$$P_x(0) = 0.9046$$
$$P_x(1) = 0.0954$$
With this information we can then calculate the square of the expected value of the x measurement, $\langle X \rangle^{2}$
$$\langle X \rangle^{2} = 0.6548 $$

Now looking at the z-measurement we can calculate its probability by first apply a $\frac{\pi}{5}$ rotation and then passing it through an H-gate.
```math
\frac{1}{\sqrt{2}}
\begin{bmatrix}
1 & 1 \\
1 & -1
\end{bmatrix}
\begin{bmatrix}
cos(\frac{\pi}{10}) & -sin(\frac{\pi}{10}) \\
sin(\frac{\pi}{10}) & cos(\frac{\pi}{10})
\end{bmatrix}
\begin{bmatrix}
1 \\
0
\end{bmatrix}
=
\begin{bmatrix}
0.8910 \\
0.4540
\end{bmatrix}
```
We can square to get our probabilities for the z-measurement:
$$P_z(0)=0.7939$$
$$-_z(1) = 0.2061$$
Calculating the square of the expected value we get, $\langle Z \rangle^2$:
$$\langle Z \rangle^2 = 0.3455$$

If we combine our two results $\langle X \rangle^{2}$ and $\langle Z \rangle$^{2} we can see that it obeys the uncertainity principle (ignoring my rounding):
$$\langle X \rangle+ \langle Z \rangle \leq 1$$
$$0.6548 + .3455 \leq 1$$





