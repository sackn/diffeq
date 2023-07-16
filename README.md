# diffeq

## First Order Differential Equations

### Integrating Factor Method for Differential Equations

**Introduction**
Consider a first order linear differential equation that takes the following form where p(t) and g(t) are any arbitrary functions with respect to the dependendent variable. 
$$\frac{dy}{dt} + p(t)y = g(t)$$
For any of the following methods to work the functions p(t) and g(t) must also be continuous. A linear differential equation is the most common form of a differential equation and we will use the integration factor method to solve it.

Assume some magical function $\mu(t)$ called the integrating factor and multiply it through the equation.
$$\mu(t) \frac{dy}{dt} + \mu(t)p(t)y = \mu(t)g(t)$$
Assume the following is true
$$\mu(t)p(t) = \dot{\mu}(t)$$
Subbing in the our new assumption into our original differential equation.
$$\mu(t)\frac{dy}{dt} + \dot{\mu}(t)y = \mu(t)g(t)$$
We can recognize that the left side of the equation is the just the product rule. This allows us to rewrite the equation as the following:
$$\frac{d}{dt}(\mu (t) y(t)) = \mu(t)g(t)$$
We can integrate through this equation to get this next equation:
$$\mu(t)y(t) + c = \int \mu(t)g(t)(dt)$$
Solving for y(t) we get:
$$y(t) = \frac{\int \mu(t)g(t)(dt)}{\mu(t)}$$
Go back to our initial assumption and solve for p(t):
$$\mu(t)p(t) = \dot{\mu}(t)$$
$$p(t) = \frac{\dot{\mu}(t)}{\mu(t)}$$
Again you might recognize that the right side of the equation is the definition of a the derivative natural logarithim ($\frac{d}{dx}ln(u) = \frac{du}{dx}\frac{1}{u}:$)
\frac{d}{dt}ln(\mu(t)) = p(t)
Now integrating both sides and manipulating a little we get:
$$ln(\mu (t)) = \int P(t)(dt) + k$$
$$\mu(t) = ke{\int P(t)(dt)}$$
Plugging are formula into our equation for y(t) we get:
$$y(t) = \frac{k \int e^{\int p(t)(dt)} g(t)(dt) + c}{ke^{\int p(t)(dt)}}$$
Dividing through by k to reduce the equation to a single equation we get the final formula of:
$$y(t) = \frac{1}{\mu(t)}(\int \mu(t) g(t)dt + c)$$
$$\mu(t) = e^{\int p(t)(dt)}$$

**Problems with Solutions**

**Question 1.4.2:**  $\dot{y} + 6y = e^{x}$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/intFactor/image1.png" alt="1.4.2">
</details>

**Question 1.4.4:**  $\dot{y} + cos(x)y = cos(x)$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/intFactor/image3.png" alt="1.4.4">
</details>

**Question 1.4.10:**  $\dot{y}+ 3x^{2}y = x^{2}$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/intFactor/image2.png" alt="1.4.10">
</details>

**Question 1.4.11:**  $\dot{y} + 2sin(2x)y = 2sin(2x) \quad y(\pi/2) = 3$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/intFactor/image4.png" alt="1.4.11">
</details>

<hr>

### Exact Equations
Exact functions are an extremely common form of differential equation. An exact equation is a type of potential function. Potential functions model so many things like the gravitational potential energy and electrostatic potential energy. A certain potential functions f(x,y) must obey a certain set of properties.

Remember that $g = \nabla f$  where f is the potential function of g. If g has a potential function (and not all functions have potential functions) then it is conservative. A conserative function implies that the potential function itself $\vec{F} = p\vec{i} + q\vec{j}$ has the following property:
$$\frac{\partial p}{\partial y} = \frac{\partial Q}{\partial x} $$

In order for the following methods to be applied the previous property must be true and the differential equation must take the form of:
$$P(x,y)dx + Q(x,y)dy = 0$$
Alternatively,
$$\frac{\partial F}{\partial x}(dx) + \frac{\partial F}{\partial y}(dy)=0$$

**Worked Example**

Consider the problem (1.8.7): 
$$(2x+y)dx + (x-4y)dy = 0$$
We should first check whether the equation is exact. We can confirm whether the equation is exact by seeing if $\frac{\partial p}{\partial y} = \frac{\partial Q}{\partial x}$ holds true. We know $P = 2x+y = \frac{\partial F}{\partial x}$ and $Q = x-4y = \frac{\partial F}{\partial y}$. Note that the 2nd part of the equality between the partials and P will be extremely important later. Checking exactness:
$$\frac{\partial P}{\partial y} = 1 \qquad \frac{\partial Q}{\partial x} = 1$$ 

$$\frac{\partial P}{\partial y}  = \frac{\partial Q}{\partial x} \quad \therefore  exact$$ 

We know $p = \frac{\parital F}{\partial x}$ so we can integrate on both sides with respect to x.
$$\frac{\partial F}{\partial x} = 2x + y$$
$$F(x,y) = \int (2x+y)(dx)$$
We need to be careful with how we integrate this. We have y's in our integrand, but we are only integrating with respect to x. In this case, all y's should be treated as constants as we are not dealing with them directly. Also, our constant of integration will be slighly different. Since, we are teating y as a constant the constant of integration is actually any function of y (named $h(y)$ in this problem). If we try to invert the integral with a partial derivative with respect to x we will get back our original integrand regardless of what function of y is attached at the end.
$$F(x,y) = x^{2} + xy + h(y)$$

We have the a part of the solution all we are missing is $h(y)$. The big trick comes in through differentiatng $F(x,y)$ with respect to y. We will be left with $\frac{\partial F}{\parital y}$ equals something. If you go back we know that $\frac{\partial F}{\partial y} = Q = x-4y$. That means we can set the output of differivative equal to Q.

$$\frac{\partial F}{\partial y} = x + \dot{h}(y)$$
$$x-4y = x + \dot{h}(y)$$

With our new equation it is immediately apparent that $\dot{h}(y) = -4y$. We can easily solve this differential equation by integrating on both side and now that we are only dealing with a singular varible our constant of integration is really just +c.
$$\dot{h}(y) = -4y$$
$$h(y) = \int -4y (dy)$$
$$h(y) = -2y^{2} + c$$

Plugging our answer for $h(y)$ back into our previous answer we get the general solution to the exact differential equation.
$$F(x,y) = x^{2} + xy - 2y^{2} + c$$


**Problems with Solutions**

**Question 1.8.1.a:**  $(2xy+x^{2})dx + (x^{2}+y^{2}+1)dy = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/exact/image4.png" alt="1.8.1.a">
</details>

**Question 1.8.1.b:**  $x(dx) + y(dy) = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/exact/image3.png" alt="1.8.1.b">
</details>

**Question 1.8.1.c:**  $(e^{x}+y^{3})dx + 3xy^2(dy) = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/exact/image2.png" alt="1.8.1.c">
</details>

**Question 1.8.7:**  $(3x^{2}+3y)dx+(3y^2+3x)dy = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/exact/image1.png" alt="1.8.7">
</details>

<hr>

### 2nd Order Linear Homogenous Differential Equations

**Problems with Solutions**

**Question 2.2.3:** $\ddot{y}  + 4\dot{y} + 2y = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/2ndorder/image4.png" alt="2.2.4">
</details>

**Question 2.2.4:** $\ddot{y} - 6\dot{y} + 9y = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/2ndorder/image1.png" alt="2.2.4">
</details>

**Question 2.2.6:** $\ddot{y} + 9\dot{y} =  0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/2ndorder/image2.png" alt="2.2.6">
</details>

**Question 2.2.7:** $2\ddot{y} + 50y = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/2ndorder/image5.png" alt="2.2.4">
</details>

**Question 2.2.9:** $2\ddot{y} + \dot{y} + y = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/2ndorder/image3.png" alt="2.2.8">
</details>

<hr>

### Higher Order Linear Homogenous Differential Equations

