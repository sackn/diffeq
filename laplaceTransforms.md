## Higher Order Linear Homogenous Differential Equations

## Laplce Transforms
**Laplce Transform Table:**

Trust me this table will be important later (I did not create this website and I was too lazy to write out my own laplace transform table): https://tutorial.math.lamar.edu/classes/DE/Laplace_Table.aspx
### Laplce Transform Introduction
Laplace transforms allow us to turn a calculus problem into an algebra problem. Before learning how to use the laplace transform to solve ODE's we must define how to even laplace transform some function that might appear in a differential equation. The forward laplace transform take a function of t $f(t)$ and transform into a function with respect to some variable $s$. A forward laplace transform is donated as $\mathcal{L} [f(t)] = F(s)$. The function that turns $f(t)$ into $F(s)$ is:

$$F(s) = \int_{0}^{\infty}e^{-st}f(t)dt$$

Hopefully you remember a little about improper integration. 

**Worked Example**

Find the $\mathcal{L} [e^{at}]$ where $a$ is some constant. Based on the definition of the laplace transform we know that:
$$F(s) = \int_{0}^{\infty} e^{st}e^{at}(dt)$$
Using some algebraic manipulation we can easily integrate the function:
$$F(s) = \left. \int_{0}^{\infty} e^{(a-s)t}(dt) = \frac{e^{(a-s)t}}{a-s}  \right\vert_{0}^{\infty}$$
Working on our limits of integration we get that:
$$F(s) = \frac{1}{a-s} \lim_{t \to \infty} (e^{(a-s)t}-1)$$
It turns out that our integral actually has two possible solutions depending on $a-s$. If $a-s \leq 0$ then our integral will blow up to infinity. However, if $a-s < 0$ then our integral will converge. We want our final transform to converge so our final answer is:
$$\mathcal{L} [e^{at}] = F(s) = \frac{1}{s-a} \quad s>a$$

In a function that will become really important later involves a new function called the heaviside step function. A heaviside step function is basically just a switch. The step functions is defined to have some constant $a$ a where it will be "off" range $(-\infty, a)$ then "on" on the interval $[a, \infty)$. The heaviside step function function is defined as follows:

$$
u(t) = \begin{cases}
0, & \text{if } x < 0, \\
1, & \text{if } x \geq 0.
\end{cases}
$$

Its not a very exiciting function, but it is infinately useful. A graph of the heaviside function is as follows:
<img src="https://hvidberrrg.github.io/deep_learning/activation_functions/assets/step_function.png" alt="Heaviside Step Function Function">

Naturally we can shift the step function so that it turns on at some specific $a$.

$$
u(t-a) = \begin{cases}
0, & \text{if } x < a, \\
1, & \text{if } x \geq a.
\end{cases}
$$

A primary property of the heaviside function is that it play extremely well with the laplace transform.

**Worked Example**

Find $$\mathcal{L} [u(t-a)]$$ for some $$a \geq 0$$. By defintion of laplace transforms we get:
$$F(s) = \int_{0}^{\infty} e^{-st}u(t-a)dt$$
By the very definition of the step function we can simplifying the integral greatly. Integrals get the area under the curve and any time before $a$ $u(t)$ will be equal to 0. Anything before $a$ will have no contribution so we change our limits to go from $a$ to $infty$. Once we get to $a$ our step function will just be one. That makes our integral the following:
$$F(s) = \int_{a}^{\infty} e^{-st}(1)dt$$

Solving the integral we get our laplace transform.

$$\left. \frac{-st}{a}  \right\vert_{0}^{\infty}$$

$$\mathcal{L} [u(t-a)] = \frac{e^{as}}{s}$$

I want to work through one more laplace transform problem. The final example will be the laplace transform of some polynomial $t^{n}$. However, first I want to define the gamma function. We all know the discrete factorial function ( $5! = (5)(4)(3)(2)(1)$ ). It has two main properties:
- $0!$ and $1!$ are 1
- $n! = n(n-1)!$ 

The gamma function is defined as folows:
$$\Gamma(x) = \int_{0}^{\infty} e^{-t}t^{x-1}dt \qquad \Gamma(1) = 1$$ 
Consider the following:
$$\Gamma(n) = \int_{0}^{\infty} e^{-t}t^{n}dt$$
Through integration by parts $dv = e^{-t}$ and $u = t^n$ we get (note that the $uv$ term goes to 0 so I left it out):
$$-\int_{0}^{\infty}-e^{-t}n t^{n-1}dt$$
Rearranging a little we get that the gamma function is equiavalent to the factorial function:
$$\Gamma(n) n\int_{0}{\infty}-e^{-t}t^{n-1}dt$$
$$\Gamma(n) = n\Gamma(n-1)$$
$$\Gamma(n) = n!$$

Since the gamma function is an integral and not a discrete function like the standard factorial, we can actually evaulate it at anywhere. The gamma function is continuous and allows us to calculate things like $\frac{1}{2}! \approx 0.886$. Below is a picture of the gamma function
<img src="https://www.mathworks.com/help/examples/symbolic/win64/GammaPlotTheGammaFunctionvExample_01.png" alt="Gamma Function">

The gamma function makes it extremely easy to figure out the laplace transform for $t^{n}$

**Worked Example**

Find the laplace transform of $\mathcal{L} [t^{n}]$. Firstly, we start off with the definition of the laplace transform
$$F(s) = \int_{0}^{\infty} e^{-st}t^{n}dt$$
Doing a the u-substituion where $u=st$ will yield the following:
$$F(s) = \int_{0}^{\infty} e^{-u}(\frac{u}{s})^{n}du = \frac{1}{s^{n+1}}\int_{\infty}^{0} e^{-u}u^{n}du$$
Now we realize that the only thing left of our integral is an alternative definition of the gamma function. Note that that the gamma function is technically $(n-1)!$, and the integral we have is the gamma function shifted one to the right so we have $n!$.
$$\mathcal{L} [t^{n}] = \frac{n!}{s^{n+1}}$$

**Linearity of the Lplace Transform**

L:aplace transforms have the following property of linearity. Linearity is defined as a functions ability to fulfill the following statement (for some abitrary constants $a,b$ and arbitray functions $f(x),g(x)$):
$$\mathcal{L} [af(t) + bg(t)] = a \mathcal{L}[f(t)] + b\mathcal{L}[g(t)]$$
The above property should be pretty intuitive since the laplace transform is really just an integral and we already know that integrals have the property of linearity. 

**Inverse Laplace Transforms**
The general workflow of using laplace transforms to solve equations uses involves turning a differential equation into a algebraic equation. We then manipulate that algebraic equation and then transform it back. We already disucssed how to turn it into an algebraic equation via the laplace transform, so now I'm going to talk about how to turn it back from its algebraic equation (in terms of $s$) back into its "normal" equation (in terms of the original varible $t$).

For some given $F(s)$ we want to know the f(t) such that:
$$F(s) = \mathcal{L} [f(t)]$$
In other words we want to find the inverse laplace transmform of F:
$$f(t) = \mathcal{L}^{-1}[F(s)]$$

According to wikipedia the definition of the inverse laplace transform is:
$$\[ \mathcal{L}^{-1} [ F(s)] = \frac{1}{2\pi i} \lim_{{T \to \infty}} \int_{c - iT}^{c + iT} F(s) e^{st} \, ds \]$$

I'm pretty sure this integral is a line integral over the complex plane. To be honest I have never dealt with it, so I wont't really talk about it. Almost all your inverse laplace transform take some form of one of the things on this laplace trasnform table (I do not own this website): https://tutorial.math.lamar.edu/classes/DE/Laplace_Table.aspx

However, what you don't want to forget is that the inverse laplace transform is also defined as an integral. That means that it has the same properties of linearity like forward laplace transform.
$$\mathcal{L}^{-1} [af(t) + bg(t)] = a \mathcal{L}^{-1} [f(t)] + b\mathcal{L}^{-1}[g(t)]$$

**Worked Example (Inverse Laplace Transform)**

Find $\mathcal{L}^{-1} [\frac{3}{s}  + \frac{1}{5s^{2}} + \frac{1}{2s^{3}} + \frac{12}{s^{4}}]$. Through linearity we can break the inverse laplace transform into four inverse laplace transforms over each of its terms.

$$f(t) = \mathcal{L}^{-1}[\frac{3}{s}] + \mathcal{L}^{-1} [\frac{1}{5s^{2}}] + \mathcal{L}^{-1} [\frac{1}{2s^{3}}] + \mathcal{L}^{-1}[\frac{12}{s^{4}}]$$

We can look at the laplace transform table to see that our laplace transform is most likely going to be a polynomial since $\mathcal{L}^{-1} [\frac{n!}{s^{n+1}}] = t^{n}$ and  $\mathcal{L}^{-1} [1] = \frac{1}{s}$. Our terms aren't in the exact form that we need them to be in before we apply the laplace transform. By manipulating the constants (remeber it obeys linearity so I can pull the constant out of the function) we get:

$$f(t) =  3 \mathcal{L}^{-1} [\frac{1}{s}] +\frac{1}{5} \mathcal{L}^{-1} [\frac{1}{s^2}] + \frac{1}{4} \mathcal{L}^{-1} [\frac{2}{s^3}] + 2 \mathcal{L}^{-1} [\frac{6}{s^4}]$$

The inverse laplace transforms can be looked for directly off the table. After applying the inverse laplace transforms we get our function in terms of $t$.

$$f(t) = 3 + \frac{1}{5}t + \frac{1}{4}t^{2} + 2t^{3} $$


**Translations and Inverse Laplace Transforms**

Some functions could be like other functions but slightly translated to the left or right. They might be super close, but one is just shifted over to the right 1 unit. For example what if I have:
$$\frac{(s-2)}{(s-2)^{2} + 9}$$
If you look at your laplace transform table the inverse laplace transform for $\frac{s}{s^{2} - 9} = cos(3t)$. That isn't exactly what we have. Our expression is the same, but every $s$ is replaced with $s-2$ corresponding with a shift to the right two units. If you know the function is shifted over there is an extremely easily solution to it. By the way the answer is $e^{2t}cos(3t)$ and I will explain why this is the case.

**Worked Proof for the Translational Property**

Consider some the forward laplace transform $\mathcal{L} [e^{at}f(t)]$ where $a$ is some constant and $f(t)$ is some function. By the defintion of the laplace transform we get:
$$F(s) = \int_{0}^{\infty} e^{-st}e^{at}f(t) dt$$
Through some algebraic manipultion we can get:
$$F(s) = \int_{0}^{\infty} e^{-(s-a)t}e^{at}f(t) dt$$
You might notice that the above is just another laplace transform. In fact its the laplace transform of f(t) just shifted over by units of $a$ to the right.
$$F(s) = \int_{0}^{\infty} e^{-(s-a)t}e^{at}f(t) dt = F(s-a)$$

That would explain why I added the $e^{2t}$ onto the original laplace transform of $cos(3t)$. The expoential term was just there to shift the netire function to the righ two, so that it fits our original expression.

**Worked Example**

Find $\mathcal{L}^{-1} [ \frac{18}{(s+3)^4} ]$. From the laplace transform table we know that $t^{3} = \frac{6}{s^4}$. We can move out some of our constant to get it a little bit closer.
$$3 \mathcal{L}^{-1} [ \frac{6}{(s+3)^4} ]$$
The argument of our laplace transform is the exact same as the table except for the fact that we have $s+3$ rather than simply $s$. That addition of three to all variables of $s$ correspondsto a translation 3 units to the left and can get be dealt with an exponential. Accounting for the translation we get:
$$3e^{-3t}t^3$$

### Problems with Solutions
I take questions from a open source textbook and give full solutions. I'm not going to put many forward laplace transform questions since they don't have any work. Here is the open source textbook I pull from https://web.uvic.ca/~tbazett/diffyqs/laplace_section.html

However, I need content for forward laplace transforms I have the work for how inverse laplace transform them.

**Lebl Question 3.1.5:** Find $\mathcal{L}^{-1} [\frac{3}{s} + \frac{120}{s^{6}} + \frac{\pi}{s^2 + \pi^2}]$ 
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/laplace1/image3.png" alt="Lebl 3.1.5">
</details>

**Lbel Question 3.1.6:** Find $\mathcal{L}^{-1} [\frac{a}{s} + \frac{b}{s^2} + \frac{2c}{s^3}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/laplace1/image5.png" alt="Lebl 3.1.6">
</details>

**Lebl Question 3.1.9:** Find $\mathcal{L}^{-1} [\frac{8}{s^3} + \frac{8}{s^2} + \frac{4}{s}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/laplace1/image4.png" alt="Lebl 3.1.9">
</details>

**Lebl Question 3.1.7:** Find $\mathcal{L}^{-1} [\frac{As + B \omega}{s^{2} + \omega^{2}}]$ 
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/laplace1/image2.png" alt="Lebl 3.1.7">
</details>

**Lebl Question 3.1.10:** Find $\mathcal{L} [te^{-t}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/laplace1/image1.png" alt="Lebl 3.1.10">
</details>

**Lebl Question 3.1.17:** Find $\mathcal{L} [2t^{2} - 2t + 1 - e^{-2t}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/laplace1/image7.png" alt="Lebl 3.1.17">
</details>

**Lebl Question 3.1.18:** Find $\mathcal{L}^{-1} [\frac{s+1}{s^2 + 2s + 10} + \frac{3}{s^2 + 2s + 10}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/laplace1/image7.png" alt="Lebl 3.1.18">
</details>

**My Question 1:** Find $\mathcal{L} [u(t-6)]$
<details>
  <summary>Solution (Ignore Horrible Cropping)</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/laplace1/image6.png" alt="Laplace1">
</details>

### Partial Fractions and Laplace transforms of derivaitves

**Laplace Transform of the First Deriative**

If we are going to use the laplace transform to solve differential equatins its probably in our best interest to know how to take the laplace transforms of the derivative of a function. Assume some well behaving first derivative $\dot{f}(t)$ and plug it into the definition of the laplace transform.
$$\mathcal{L} [\dot{f}(t)] = \int_{0}^{\infty}e^{-st}\dot{f}(t)dt$$
We can integrate by parts by choosing $u=e^{st}$ and $dv = \dot{f}(t)$. Doing so will get us:
$$\left. \frac{-st}{a}  \right\vert_{0}^{\infty} + s\int_{0}^{\infty}-e^{-st}f(t)dt$$

Under exponential order the first term will evaluate to $-f(0)$ and the integral is the laplace definition of $s \mathcal{L} [f(t)]$ (we are allowed to factor out the $s$ since the integral is with respect to t). That leaves us with the following laplace transform for the first derivative
$$\mathcal{L} [\dot{f}(t)] = s \mathcal{L}[f(t)] - f(0) \quad \square$$

Alternatively,
$$\mathcal{L} [\dot{f}(t)] = sF(s) - f(0)$$
The $f(0)$ that comes out of the laplace transforms will take the place of constants when we solve using laplace transforms. 

**Laplace Transform of the Second Deriative**

Let $h(t) = \dot{f}(t)$. We then know the followng to be true
$$\mathcal{L}[\ddot{f}(t)] = \mathcal{L}[\dot{h}(t)]$$
We already have the general form of the first derivativ, so we can expand the right side into,
$s \mathcal{L} [h(t)] - g(0)$
By resubstiting in $h(t)= \dot{f}(t)$ we get,
$$s\mathcal{L}[\dot{f}(t)] - \dot{f}(0)$$
We have another first dervivative this time with respect to just f(t). If we apply the formula for the first deravative again we get:
$$s( s \mathcal{L} [f(t)] - f(0)) - \dot{f}(0)$$
Simplfying we get that the derivative of the 2nd derivative is (where $f(0)$ and $\dot{f}(0)$ are initial values),
$$\mathcal{L}[\ddot{f(t)}] = s^{2}F(s) - sf(0) - \dot{f}(0) \quad \square$$

Any higher order derivatives will follow a similar pattern. The pattern can be seen on the laplace transform table. For example the laplace transform of the third derivative is:
$$\mathcal{L}[\dddot{f}(t)] = s^3 F(s) - s^2f(0) - s\dot{f}(0) - \ddot({f}(0)$$

**Laplace Transforms and Partial Fractions**

Most of the time when dealing with laplace transforms to solve ODE's we run into fractions with a polynomial of in the numerator and denominator each with respect to the new varible $s$ (it will become obvious why this happens so much when you start solving). In order to solve the differential equation we need to apply the inverse laplace transform, but most of the time the rationals aren't in the ideal form. In order to get them into the ideal form we use the concept of partial fractions. 

**Worked Example 1**
Assume we want to take the laplace transform of the following expression:
$$\frac{1}{(s-1)(s-2)}$$
Nothing immediately jumps out, but if we apply partial fractions we know that its also possible to write the single fraction in terms of the sum of two seperate ones like the following,
$$\frac{1}{(s-1)(s-2)} = \frac{A}{s-1} + \frac{B}{s-2}$$
The fractions on the right look like we could inverse laplace transform them into exponentials however, we don't know the constants A and B. If we multiple both sides by $$(s-1)(s-2)$$ to clear the denominator we get,
$$1 = A(s-2) + B(s-1)$$
We can choose strategies values of $s$ to figure out our constants. If we plug in $s=2$ we get that $B=1$,
$$1 = A(2-2) + B(2-1)$$
$$B = 1$$
Now if we plug in $s=1$ we get that $A = -1$,
$$1 = A(1-2) + B(1-1)$$
$$A = -1$$
After we solve for the constants we know that our single fraction is equivalent to the following two fractions,
$$\frac{1}{(s-1)(s-2)}= -\frac{1}{s-1} + \frac{1}{s-2}$$
We are now free to use the inverse laplace transforms for expoentials to get:
$$f(t) = -e^{t} + e^{2t}$$

Partial fractions is something that you should have learned when you were studying integration techniques, so I won't go into much detail. If you forgot how to do them I would recommend watching this video (which I did not create): [https://www.youtube.com/watch?v=2bMndF92Oqo](url)

<img src="https://github.com/sackn/diffeq/blob/main/Images/laplace1/partialFractionTable.png" alt="partialFractionTable">


**Worked Example 2**

Assume we want to find the inverse laplace transform of the following expression:
$$\frac{s}{(s^2+4)(s+1)}$$
According to the table above we had decompose the one big fraction into two fractions of the following form where we have three unknown constants,
$$\frac{s}{(s^2+4)(s+1)} = \frac{As + B}{s^2 + 4} + \frac{C}{s+1}$$
Multiplying the equation through by $(s^2 + 4)(s+1)$ we get,
$$s = (As+B)(s+1) + C(s^2+4)$$
Plugging into the equation $s=-1$ we get that $C=-\frac{1}{5}$,
$$-1 = 0 + C(5) \quad \implies c = -\frac{1}{5}$$
Knowing the that $C = -\frac{1}{5}$ we can then plug in $s = 0$ to get that $B = \frac{4}{5}$,
$$0 = B(1)- \frac{4}{5}$$
Knowing that $C = -\frac{1}{5}$ and $B = \frac{4}{5}$ we can plug in $s=1$ to get that $A = \frac{1}{5}$,
$$1 = (A + \frac{4}{5})(2) - 1 \quad \implies A = \frac{1}{5}$$
Our original fraction can now be written as the following,
$$\frac{s}{(s^2+4)(s+1)} = \frac{1}{5} (\frac{s+4}{s^2 + {4}}) - \frac{1}{5}\frac{1}{s+1}$$
Splitting up the fraction even further to make it easier to see inverse laplace transforms.
$$\frac{1}{5}(\frac{s}{s^2 + 4}) + \frac{2}{5}(\frac{2}{s^2+4}) - \frac{1}{5}(\frac{1}{s+1})$$
Using the inverse laplace transfroms from a table we get the final solution,
$$\frac{1}{5}cos(2t) + \frac{2}{5}sin(2t) + e^{-t} \quad \square$$


**Worked Example 2.5**

Once you get to harder partial fraction problems it may be difficult to simply plug in a value and solve for a single varible. In more difficult problems it unlikely that all but one varible is left. There exist an alternative to getting the constants through a system of linear equations. Consider the same scenario from example 2:
$$s = (As+B)(s+1) + C(s^2+4)$$
First lets mutliply everything out and then group by the degree of each term.
$$s = As^{2} + As + Bs + B + Cs^{2} + 4C$$
$$s = s^{2}(A + C) + s(A + B) + (B+4C)$$
We can think of it as a balancing act between the the two sides. For the right side to equal the left side we need $A+C = 0$ since we don't want any $s^{2}$, we need $A+B = 1$ since we have a single $s$ on the other side, and we need $B + 4C = 0$ since there are no constants terms on the other side. We could these three equation as a system like the following:
$$A + 0B + 1C = 0$$
$$A + B + 0C = 1$$
$$0A + B + 4C = 0$$

Solving the system will using matrices or whatever method you like will get us $A = \frac{1}{5}$,$B = \frac{4}{5}$, and $C = -\frac{1}{5}$ which are the same answers as we got above. For the harder problems I will almost always use this method.

### Problems and Solutions

**Question 1:** Find $\mathcal{L}^{-1} [\frac{s+1}{s^2 + 6s + 9}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image4.png" alt="Question 1">
</details>

**Question 2:** Find $\mathcal{L}^{-1} [\frac{2s}{s+1}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image8.png" alt="Question 2">
</details>

**Question 3:** Find $\mathcal{L}^{-1} [\frac{3}{s^{2}+9}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image9.png" alt="Question 3">
</details>

**Question 4:** Find $\mathcal{L}^{-1} [\frac{1}{s(s+1)}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image5.png" alt="Question 4">
</details>

**Question 5:** Find $\mathcal{L}^{-1} [\frac{3s+2}{s^2+ 4s + 4}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image1.png" alt="Question 5">
</details>

**Question 6:** Find $\mathcal{L}^{-1} [\frac{3s+1}{(s^2 + 2s + 2)(s+1)}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image11.png" alt="Question 6">
</details>

**Question 7:** Find $\mathcal{L}^{-1} [\frac{3s^2+2s+4}{s^3+4s^2+5s}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image7.png" alt="Question 7">
</details>

**Question 8:** Find $\mathcal{L}^{-1} [\frac{3s^2+2s+4}{s^3+4s^2+5s}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image10.png" alt="Question 8">
</details>

**Question 9:** Find $\mathcal{L}^{-1} [\frac{s+1}{(s^2+ 9)(s^2 +4s + 8)}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image6.png" alt="Question 9">
</details>

**Question 10:** Find the laplace trasnform of $\dot{f}(t) = cos(3t)$ where $f(0) = -10$:
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image3.png" alt="Question 10">
</details>

**Question 11:** Find the laplace transform of $\ddot{f}(t) = t^3$ where $f(0) = 2$ and $\dot{f}(0) = 3$:
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image2.png" alt="Question 11">
</details>

**Question 12:** Write the formula for the laplace transform of the 5th derivative
<details>
  <summary>Solution</summary>
  $$\mathcal{L} [f^{(5)}(t)] = s^{5} F(s) - s^{4}f(0) - s^{3}\dot{f}(0) - s^{2}\ddot{f}(0) -s \dddot{f}(0) - f^{4}(0)$$
</details>


### Laplace Transform for Solving Differential Equations

Now that we have everything in place we can finally start solving differential equations with laplace transforms. The general workflow of solving goes as following:
- Laplace transform both sides of the equation and apply the initial conditions
- Isolate $F(s)$ in the equation
- Use algebraic manipulation to get the expression into the correct format for inverse laplace transforms
- Apply the inverse Laplace Transform
- Final Solution
  
**Worked Example 1**

Find the solutiont to the following initial value problem:
$$\ddot{y} - 6\dot{y} + 9y = e^{3t} \quad y(0) = 1 \quad \dot{y}(0) = 2$$
If we Laplace transform both sides:
$$(s^{2}Y(s) -sY(0) -\dot{Y}(0)) -6(sY(s) -Y(0)) + 9Y(s) = \frac{1}{s-3}$$
Mulitplying out the factor and applying the initial conditions we get:
$$s^{2}Y(s) - s - 2 - 6sY(s) + 6 + 9Y(s) = \frac{1}{s-3}$$
With some algerbraic manipulation we can get $Y(s)$ alone,
$$Y(s)(s^2 -6s + 9) = \frac{1}{s-3} + s - 4$$
$$Y(s) = \frac{s^2 -7s + 13}{(s-3)(s-3)^2}$$
I'm not going to show all the work for the partial fractions, but if you follow through the entire process you will get,
$$Y(s) = \frac{1}{s-3} - \frac{1}{(s-3)^2} + \frac{1}{(s-3)^3}$$
Now taking the inverse laplace transform to both sides fo the equation (note the manipuatlion on the last term),
$$y(t) = \mathcal{L}^{-1}[\frac{1}{s-3}] - \mathcal{L}^{-1}[\frac{1}{(s-3)^2}] + \frac{1}{2}\mathcal{L}^{2}[\frac{1}{(s-3)^3}]$$
Applying the inverse laplace transform we get the final solution
$$y(t) = e^{3t} -te^{3t} + \frac{1}{2}t^2e^{3t}$$

**Worked Example 2**
Find the solution to the following initial value problem:
$$\ddot{y} + 2 \dot{y} + 2y = 3u(t-6) \quad y(0) = 0 \quad \dot{y} = 1$$
In this problem we have a step function. Our solution will have a step function, however the general process will not change. If we laplace transform both sides and apply initial conditions (look up the laplace transform of u(t-6) in the laplace transform table if you need):
$$Y(s)s^{2} -1 2sY(s) + 2Y(s) = \frac{3e^{6s}}{s}$$
Isolating the function Y(s):
$$Y(s) = \frac{3e^{-6s} + s}{s(s^2+2s+2)}$$
Seperating the big fraction into two smaller fraction. Note that only the left side is attached to the step function while the right side is "on" regardless of the status of the step function.
$$Y(s) = \frac{3}e^{-6s}(\frac{1}{s(s^{2}+2s+2)}) + \frac{1}{s^2+2s+2}$$
We can partial fraction the inside of the left term
$$Y(s) = \frac{3}{2}e^{-6s}(\frac{1}{s}-\frac{s+2}{s^2+2s+2}) + \frac{1}{s^2+2s+2}$$
Completeing the square for the polynomial $s^2 + 2s+ 2$ and splitting $s+2$ into $s+1$ and $1$ we get:
$$Y(s) = \frac{3}{2}e^{-6s}(\frac{1}{s} - \frac{s+1}{(s+1)^2}+1) + \frac{1}{(s+1)^2}+1$$
Before we need apply the inverse laplace transform I want to talk a little bit about how the left term (more specifically the things attached to the thing that will inverse laplace into the step function) will change. $e^{-6s}$ will become $u(t-6)$ which is a step function that turns on at $t=6$. We want to also apply this t=6 delay to the things its attached to. In order to do this we define a new function $h(t-6)$ ($t-6$ to set it back 6 like the step function) where h(t) is the inverse laplace transform of everything multiplied by that specific step function. Applying the laplace transform to everything we get the following two lines as our solution:
$$y(t)=\frac{3}{2}u(t-6)h(t-6) + e^{-t}sin(t)$$
$$h(t) = 1 - e^{-t}cos(t) + e^{-t}sin(t) \quad \square$$

Firstly a short analysis of the solution at $t<6$ the solution will behave as:
$$y(t) = e^{-t}sin(t)$$
For any $t \geq 6$ the solution will behave as:
$$y(t) = \frac{3}{2} -\frac{3}{2}e^{-t}cos(t) + \frac{5}{2}e^{-t}sin(t)$$


**Question 1:** Find the solution to the IVP $\ddot{y} + 4\dot{y} + 3y =0$ with the conditions $y(0) = 1$ and $\dot{y}(0) = 2$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image2.png" alt="Question 11">
</details>

**Question 2:** Find the solution to the IVP $\ddot{y} + 2\dot{y} + 2y =sin(2t)$ with the conditions $y(0) = 1$ and $\dot{y}(0) = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image2.png" alt="Question 11">
</details>

**Question 3:** Find the solution to the IVP $\ddot{y} - 5\dot{y} + 6y =4e^{2t}$ with the conditions $y(0) = 2$ and $\dot{y}(0) = 1$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image2.png" alt="Question 11">
</details>

**Question 4:** Find the solution to the IVP $\ddot{y} + 3\dot{y} + 2y = cos(4t)$ with the conditions $y(0) = 0$ and $\dot{y}(0) = -2$

<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image2.png" alt="Question 11">
</details>

**Question 5:** Find the solution to the IVP $\ddot{y} + 4\dot{y} + 4y = u(t-1) + 2u(t-3)$ with the conditions $y(0) = 0$ and $\dot{y}(0) = 1$
<details>
  <summary>Solution</summary>
  When you have two step functions most of the time you would need to create two different funtions however, if our scenario we only need h(t) to describe both. Try writing out what the solution will be at any point in time.
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image2.png" alt="Question 11">
</details>

With laplace transforms you could theoretically do a differential equation of any order however, the complexity of the algebra and inverse transforms will grow quickly. 

**Question 6:** Find the solution to the IVP $\dddot{y}+ \dot{y}= 3$ with the conditions $y(0) = 0$, $\dot{y}(0) = 0$ , and $\ddot{y}=0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/partialFrac/image2.png" alt="Question 11">
</details>



