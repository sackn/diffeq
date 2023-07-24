## Method of Charaeristics 

**Worked Example**

Conisder the following partial differential equation $xu_x - yu_y = 2$ with the initial condition $u(x,2) = x^{2}$.

We know that the following to facts about the pde:
$$\frac{dx}{dt} = x \quad \frac{dy}{dt} = -y $$

For a change of varibles we would like to have to find y in terms of x. We can divide the two statements above to get $\frac{dy}{dx}$. Doing so will get us the following,
$$\frac{\frac{dy}{dt}}{\frac{dx}{dt}} = \frac{dy}{dx} = \frac{-y}{x}$$

This leaves us with just a seperable differential equation in terms of $x$ and $y$. Solving the integral through:
$$\frac{dy}{dx} = \frac{-y}{x}$$
$$\int -\frac{1}{y} dy = \int \frac{1}{x}dx$$
$$-ln|y| = ln|x| + c$$$
$$y = -cx \implies c = -\frac{y}{x}$$
