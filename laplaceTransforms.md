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

$$f(t) =  3 \mathcal{L}^{-1} [\frac{1}{s}] + \frac{1}{5} \mathcal{L}^{-1} [\frac{1}{s^{2}] + \frac{1}{4} \mathcal{L}^{-1} [\frac{2}{s^{3}]$$

The inverse laplace transforms can be looked for directly off the table. After applying the inverse laplace transforms we get our function in terms of $t$.

$$f(t) = 3 + \frac{1}{5}t + \frac{1}{4}t^{2} + \frac{1}{2}t^{3}$$




### Problems with Solutions
I take questions from a open source textbook and give full solutions. I'm not going to put many forward laplace transform questions since they don't have any work. Here is the open source textbook I pull from https://web.uvic.ca/~tbazett/diffyqs/laplace_section.html

However, I need content for forward laplace transforms I have the work for how inverse laplace transform them.


