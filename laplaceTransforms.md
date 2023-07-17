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
$$F(s) = \left. \int_{0}^{\infty} e^{(a-s)t}(dt) = \frac{e^{(a-s)t}}{a-s}  \right\vert_{\infty}^{0}$$
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

$$\left. \frac{-st}{a}  \right\vert_{\infty}^{0}$$


$$\mathcal{L} [u(t-a)] = \frac{e^{as}}{s}$$

I want to work through one more laplace transform problem. The final example will be the laplace transform of some polynomial $t^{n}$. However, first I want to define the gamma function. We all know the discrete factorial function ( $5! = (5)(4)(3)(2)(1)$ ). It has two main properties:
- $0!$ and $1!$ are 1
- $n! = n(n-1)!$ 

The gamma function is defined as folows:
$$\Gamma(x) = \int_{0}^{\infty} e^{-t}t^{x-1}dt \qquad \Gamma(1) = 1$$ 
Consider the following:
$$\Gamma(n) = \int_{0}^{\infty} e^{-t}t^{n}dt
Through integration by parts $dv = e^{-t}$ and $u = t^n$ we get (note that the $uv$ term goes to 0 so I left it out):
$$-\int_{0}{\infty}-e^{-t}n t^{n-1}dt$$
Rearranging a little we get that the gamma function is equiavalent to the factorial function:
$$\Gamma(n) n\int_{0}{\infty}-e^{-t}t^{n-1}dt$$
$$\Gamma(n) = n\Gamma(n-1)$$
$$\Gamme(n) = n!$$

Since the gamma function is an integral and not a discrete function like the standard factorial, we can actually evaulate it at anywhere. The gamma function is continuous and allows us to calculate things like $\frac{1}{2}! \approx 0.886$. Below is a picture of the gamma function
<img src="https://www.mathworks.com/help/examples/symbolic/win64/GammaPlotTheGammaFunctionvExample_01.png" alt="Gamma Function">

The gamma function makes it extremely easy to figure out the laplace transform for $t^{n}$

**Worked Example**


### Problems with Solutions
I take questions from a open source textbook and give full solutions. I'm not going to put many forward laplace transform questions since they don't have any work. Here is the open source textbook I pull from https://web.uvic.ca/~tbazett/diffyqs/laplace_section.html

However, I need content for forward laplace transforms I have the work for how inverse laplace transform them.


