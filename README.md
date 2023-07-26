# First Order Differential Equations

## Integrating Factor Method for Differential Equations

### Introduction
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

### Worked Example

Consider the following problem:
$$\dot{y} - y = e^{3x} \qquad y(0) = 3$$

From the formulas that we previously derived we know that our integrating factor is equal to the following:
$$\mu = e^{\int -1(dx)} = e^{-x}$$

Our general soltuion then takes the following form:
$$y = \frac{1}{e^{-x}} \left( \int e^{-x}e^{3x} + c \right)$$
We can simplying the factor out front and the integral on the inside is pretty simplistic (remember to that $e^{-x}e^{3x} = e^{2x}$)
$$y = e^{x}(\frac{1}{2}e^{2x} + c)$$
$$y = (\frac{1}{2}e^{3x} + ce^{x})$$
Applying the initial condition of $y(0) = 3$ we can solve for a particular solution:
$$3 = \frac{1}{2} + c(1)$$
$$c = \frac{5}{2}$$

Applying the constant to our solution we get the final answer of:
$$y = \frac{1}{2}e^{3x} + \frac{5}{2}e^{x}$$

### Problems with Solutions

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

## Exact Equations
Exact functions are an extremely common form of differential equation. An exact equation is a type of potential function. Potential functions model so many things like the gravitational potential energy and electrostatic potential energy. A certain potential functions f(x,y) must obey a certain set of properties.

Remember that $g = \nabla f$  where f is the potential function of g. If g has a potential function (and not all functions have potential functions) then it is conservative. A conserative function implies that the potential function itself $\vec{F} = p\vec{i} + q\vec{j}$ has the following property:
$$\frac{\partial p}{\partial y} = \frac{\partial Q}{\partial x} $$

In order for the following methods to be applied the previous property must be true and the differential equation must take the form of:
$$P(x,y)dx + Q(x,y)dy = 0$$
Alternatively,
$$\frac{\partial F}{\partial x}(dx) + \frac{\partial F}{\partial y}(dy)=0$$

### Worked Example

Consider the problem (1.8.7): 
$$(2x+y)dx + (x-4y)dy = 0$$
We should first check whether the equation is exact. We can confirm whether the equation is exact by seeing if $\frac{\partial p}{\partial y} = \frac{\partial Q}{\partial x}$ holds true. We know $P = 2x+y = \frac{\partial F}{\partial x}$ and $Q = x-4y = \frac{\partial F}{\partial y}$. Note that the 2nd part of the equality between the partials and P will be extremely important later. Checking exactness:
$$\frac{\partial P}{\partial y} = 1 \qquad \frac{\partial Q}{\partial x} = 1$$ 

$$\frac{\partial P}{\partial y}  = \frac{\partial Q}{\partial x} \quad \therefore  exact$$ 

We know $p = \frac{\partial F}{\partial x}$ so we can integrate on both sides with respect to x.
$$\frac{\partial F}{\partial x} = 2x + y$$
$$F(x,y) = \int (2x+y)(dx)$$
We need to be careful with how we integrate this. We have y's in our integrand, but we are only integrating with respect to x. In this case, all y's should be treated as constants as we are not dealing with them directly. Also, our constant of integration will be slighly different. Since, we are teating y as a constant the constant of integration is actually any function of y (named $h(y)$ in this problem). If we try to invert the integral with a partial derivative with respect to x we will get back our original integrand regardless of what function of y is attached at the end.
$$F(x,y) = x^{2} + xy + h(y)$$

We have the a part of the solution all we are missing is $h(y)$. The big trick comes in through differentiatng $F(x,y)$ with respect to y. We will be left with $\frac{\partial F}{\partial y}$ equals something. If you go back we know that $\frac{\partial F}{\partial y} = Q = x-4y$. That means we can set the output of differivative equal to Q.

$$\frac{\partial F}{\partial y} = x + \dot{h}(y)$$
$$x-4y = x + \dot{h}(y)$$

With our new equation it is immediately apparent that $\dot{h}(y) = -4y$. We can easily solve this differential equation by integrating on both side and now that we are only dealing with a singular varible our constant of integration is really just +c.
$$\dot{h}(y) = -4y$$
$$h(y) = \int -4y (dy)$$
$$h(y) = -2y^{2} + c$$

Plugging our answer for $h(y)$ back into our previous answer we get the general solution to the exact differential equation.
$$F(x,y) = x^{2} + xy - 2y^{2} + c$$

### Problems with Solutions

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

## Autonomous Equations and Equilibrium

We can tell whether the stabitlity of an equilibrium solution through is second derivative. More specifically,
- $\frac{d^2 y}{dx^2} < 0$. Equilibrium is stable
- $\frac{d^2 y}{dx^2} > 0$. Equilbrium is unstable
- $\frac{d^2 y}{dx^2} = 0$. Inconclusive most likely have to draw the slope field

For drawing slope fields you can use this desmos link (I did not make this) [https://www.desmos.com/calculator/p7vd3cdmei](url) . It's not perfect and there do exist more accurate alternatives, but its really accessible. 

**Add Images and annotations later**

Note for some of the problems you may have to approximate a zero. However make sure to approximate a zero only when you know that it exists. If you function is asymoptoic to zero it isn't a equilibrium solution.

**Question 1:**  For the autonomous equation $\frac{dy}{dx} = y(3-y)$ identify and classify equilibrium solutions.
<details>
  <summary>Solution</summary>
   $$0 = y(3-y) \implies y=0,3$$
   Our eqiulbrium solutions happen at $y=0$ and $y=3$. Looking at the slope field we see that $y=3$ is stable and $y=0$ in unstable
</details>

**Question 2:**  For the autonomous equation $\frac{dy}{dx} = 2y^2 -5y + 2$ identify and classify equilibrium solutions.
<details>
  <summary>Solution</summary>
  $$2y^{2} - 5y + 2$$
  $$(2y-1)(y-2) =0 \implies y=\frac{1}{2}, 2$$
  Our equilibrium solutions happen at $y=\frac{1}{2}$ and $y=2$. Looking at the slope field we can see that $y=2$ is unstable and $y=\frac{1}{2}$ is stable
</details>

**Question 3:**  For the autonomous equation $\frac{dy}{dx} = y^3 -4y^2 + 3y$ identify and classify equilibrium solutions. 
<details>
  <summary>Solution</summary>
  $$y(y^2 - 4y + 3) = y(y-1)(y-3) \implies y=0,1,3$$
  Our equilibrium solutions happen at $y = 0,1,3$. Looking at the slope field we can see that $y=3$ is unstable, $y=1$ is stable, and $y=0$ is unstable.
  
</details>

**Question 4:**  For the autonomous equation $\frac{dy}{dx} = 2e^{-y}-y$ identify and classify equilibrium solutions.
<details>
  <summary>Solution</summary>
  $$0 = 2e^{-y}-y$$
  Using numerical methods we can figure out that our eqiulibrium soltuions appears at $y\approx 0.853$. Looking at the slope field the eqiulibrum at $y = 0.853$ is stable
  
</details>

**Question 5:**  For the autonomous equation $\frac{dy}{dx} = \frac{y^2}{y+1}$ identify and classify equilibrium solutions.
<details>
  <summary>Solution</summary>
  $$0 = frac{y^2}{y+1}$$
  We know that $y=0$ will be the location of an equilibrium solution, but we also have a discontinuity at $y=-1$. Looking at a slope field the equilibrium at $y=0$ semi-stable.
</details>

**Question 6:**  For the autonomous equation $\frac{dy}{dx} = y(4-y)(y-2)$ identify and classify equilibrium solutions.
<details>
  <summary>Solution</summary>
  $$0 = y(4-y)(y-2) \implies y=0,2,4$$
  Looking at a slope field the equilibrium solution at $y=0$ is stable, the solution at $y=2$ is unstable, and the solution at $y=4$ is stable.
  
</details>

**Question 7:**  For the autonomous equation $\frac{dy}{dx} = e^y -2$ identify and classify equilibrium solutions.
<details>
  <summary>Solution</summary>
  $$0 = e^y - 2 \implies y = ln(2)$$
  Looking at a slope field the equilbrium solution at $y =ln(2)$ is unstable.
</details>




# 2nd and Higher Order Differential Equations

## 2nd Order Linear Homogenous Differential Equations (and a lot of theory)

### Theory behind Linear Differential Equations

2nd order linear ordinary differential equations take the following general form where $p(x)$ and $q(x)$ are any arbitrary function of x (in most cases both p and q will be constant since having them non-constant makes most differential equations extremely difficult).
$$\ddot{y} + p(x)\dot{y} + q(x)y = f(x)$$

There is a special type of 2nd order linear differnetial equations when $f(x) = 0$. These equations are called homogenous and are the topic of this section. Homogenous equations have fleshed out theory and are relatively easy to solve compared to non-homogenous cases (where $f(x)\neq 0$ )

Firstly its important to talk about when solutions exist and when they are unique on some interval. Once we into more difficult equations with stranger conditions a solution might not always exist or there might be an infinate set of them. However, for linear differential equations the conditions for existance and uniqueness are pretty light.

### Existance and Uniqueness Theorem:

For an Initial Value Problem ofthe following form: (Also note that for a 2nd Order ODE you need two different initial conditions)
$$\ddot{y} + p(x)\dot{y}+q(x)y = f(x)$$
$$y(a) = b_0 \qquad \dot{y}(a) = b_1$$

If p,q,f are continuous on some interval which contains the point a then there exist a unique solution on that same interval.

Linear differential equations hold an extremely important property that will be key to almost all of our methods. You might have heard about basis vectors before. In cartesian coordinates our basis vectors are $\vec{i} = \langle 1,0 \rangle$ and $\vec{j} = \langle 0,1 \rangle$$. Both of these vectors are linearly independent and can represent any point in 2D space. For example $\langle -2, \frac{6}{5} \rangle = -2 \vec{i} + \frac{6}{5} \vec{j}$. The two basis vectors $\vec{i}$ and $\vec{j}$ are far from the only two vectors all of 2D space. 

For example if we choose our basis vectors to be instead $\vec{e_1} = \langle 1,1 \rangle$ and $\vec{e_2} = \langle -1, 2 \rangle$ we also can describe the entire 2D plane because the vectors are linearly independent (more about what this means later). We have require different "components" to reach each point on the 2D plane but regardless our two basis vectors can be scaled and summed in some way that any combination is possible. 

$$\langle 2, \frac{6}{5} \rangle = -\frac{14}{15}\vec{e_1} + \frac{16}{15}\vec{e_2}$$

In other words any number in $\mathbb{R}^{2}$ can be written as a some sum of two linearly indepdent vectors (this is more commonly called a superposition).

I talked a lot about vectors, but I swear this relates to differential equations. It turns out that differential equations have there own superpostiton property. 

### Superposition Theorem

Suppose $y_1$ and $y_2$ solve the following equation:

$$\ddot{y} + p(x)\dot{y} + q(x)y = 0$$

then the following is also a solution (where $c_1$ and $c_2$ are some arbitrary constant),

$$y = c_1 y_1 + c_2 y_2$$

In more simple terms any combination of two already existing solutions will also always be a solution. Since $c_1$ and $c_2$ are any arbitrary constant we technically have infinate solutions. This is where the extension to the superposition theorem become extremely important:


### Superposition Theorem (extended)

Suppose there are two linearly independent solutions $y_1$ and $y_2$ to the the following equation:
$$\ddot{y} + p(x)\dot{y} + q(x)y = 0$$
then the general solution to the differential equation is
$$y = c_1 y_1 + c_2 y_2$$

Althought, it doesn't look like I changed anything the new result speaks volumes. Yes there are infinate solutions, but every single solution is really a superposition of two linearly independent functions. These two linearly independent act almost like basis vectors. It can represent any solution in the _Fundamental Set of Solutions_. If you found two linearly independent solution and then you find a third one then you know that the third one is really just your two original solutions added up in some manner. 

I probably shouldn't have waited this long to explain what linear independence is but here we are. Since, I'm here to talk about differential equations I'm going to mention linear indepedence for functions, but not linear indepdence for vectors (this is a super common topic in linear algebra however). Two functions are linear indepedent on an interval is they are not constant multiples of other. 

For example, the functions $x$ and $2x$ are not linearly indepdent because $2x$ can be obtained by just multiply $x$ by 2. On the other hand, the functions $x$ and $x^{2}$ are linearly independent because there is no CONSTANT multiple that can be applied to $x$ to obtain $x^{2}$. Althought, a little harder to see the functions $cos(x)$ and $sin(x)$ are linearly independent. Cosine and Sine are can be equal if we apply a phase shift, but there is no way constant $k$ such that $kcos(x) = sin(x)$.

### The Wronskian

Sometimes it kind of hard to tell whether functions are linearly indepdent so someone made a fool-proof way to determine if a set of functions are linearly indepdent. For 2D dimensions the Wronskian matrix is defined as follows:

$$
W(t) = det \left( \begin{bmatrix}
y_1 & y_2 \\
\dot{y_1} & \dot{y_2}
\end{bmatrix} \right)
$$

By the way if your forgot how to take the determinent of a 2D matrix here is the formula:

$$
det \left( \begin{bmatrix}
a & b \\
c & d
\end{bmatrix} \right) = ad - bc
$$

Suppose that $y_1$ and $y_2$ are linearly independent then $W(t) \neq 0$ for atleast one t. Otherwise if $W(t) = 0$ for all t then the functions are linearly dependent (not linearly independent).

### Worked Example

Consider the two functions $y_1 = t$ and $y_2 = t^{2}$. Prove that they are linearly independent. Plugging the two equations into the Wronskian we get:

$$
W(t) = det \left( \begin{bmatrix}
t & t^{2} \\
1 & 2t
\end{bmatrix} \right) = 2t(t) - (1)t^{2} = t^{2}
$$

The Wronskian is equal to $t^{2}$. The condition to be linearly indepdent is to not be zero at atleast one point t. The function $t^{2}$ is non-zero at bunch of places more specifically it is non-zero everywhere except $t=0$. In total, $t$ and $t^{2}$ must be linearly independent. The Wronskian can also be expanded to scenarios where you have more than two equations. The Wronskian has logical expansion of: 

$$
W(t) = det \left( \begin{bmatrix}
y_1 & y_2 & y_3 \\
\dot{y_1} & \dot{y_2} & \dot{y_3} \\
\ddot{y_1} & \ddot{y_2} & \ddot{y_3} \
\end{bmatrix} \right) 
$$

Finding the deterimenent of a 3x3 matrix is a little harder. There exists a formula, but its probably more effective to learn an actual method (like the coverup method). I'm too lazy to write the laTex, but the formula is one google search away. The same conditions for linear independence of more that two functions also apply.

### Solving 2nd Order Constant Linear Homogenous Differential Equation

Maybe you read the theory above maybe you didn't, but here is how to actual solve things. Remember that we are solving a 2nd order linear constant homogenous differential equation which takes the following form where $a$, $b$, and $c$ are some constants.
$$a\ddot{y} + b\dot{y} + c{y} = 0$$
We can use the overpowered substitiuon of $y = e^{rt}$. After substituion our new equation is:
$$ar^{2}e^{rt} + bre^{rt} + ce^{rt} = 0$$
We can see that if we divide through by $e^{rt}$ we are just left with a quadratic. 
$$ar^{2} + br + c = 0$$

Pulling out the quadratic equation we get that the solutions to this quadratic are:
$$r = \frac{-b \pm \sqrt{b^{2}-4ac}}{2a}$$

Our equation is in a very general form and we actually have multiple scenarios depending on the result of the stuff under square root. More specifically we have three scenarios:
1. $b^2 - 4ac > 0 \quad \implies \quad$ two distinct roots
2. $b^2 - 4ac = 0 \quad \implies \quad$ one repeated root (root with multiplicity 2) 
3. $b^2 - 4ac < 0 \quad \implies \quad$ two complex roots (conjugate pair)

Each scenarion will produce a solution of a different form:

### Distinct Roots

Distinct roots are the simpliest. Lets say thats you have two real distinct roots $r_1$ and $r_2$ then the general solution to the differential equation is:
$$y = c_1e^{r_1t} + c_2e^{r_2t}$$

Our solution is a superposition of two expoential functions. The solution is so simple that the deriviation was probably just an educated guess. It might be good practice to plug the solution back in to the original differential equation and confirm that in fact this is a solution. Also, from inspection we can see that the functions are linearly indepdent(Remember that $e^{2x}$ is $e^{x}e^{x}$ and not $2e^{x}$). Since they are linearly indepdent we know that every single solution can be written as a superposition (through changing $c_1$ and $c_2$).

### Repeated Roots

When $b^2-4ac = 0$ you have two repeated roots. For a repeated root $r_1$ then the general solution to the differential equation is:
$$y = c_1e^{rt} + c_2te^{rt}$$

We notice that the repeated roots makes a difference in the answer.  Our solution is a superposition of $e^{rt}$ and $te^{rt}$. The factor of $t$ is a direct result of trying to maintain linearly independence. If we had just treated the repeated root as a distinct root we would get $y = c_1e^{rt} + c_2e^{rt}$. However, our two soltuions aren't linearly independent $c_1e^{rt}$ and $c_2e^{rt}$ are constant multiples of each other. We added a factor of $t$ to gurantee linear independence and a general solution.

As practice you should confirm that $te^{rt}$ really is a solution to the differential equation. It turns out that adding any number of t's will still produce solution (this will be important when I talk about higher order ODE's). We can also tell that our soltuions are linearly independent.

### Complex Roots

When $b^2-4ac = 0$ you have two complex roots $\alpha \pm \beta i$. The general solution to the equation is:
$$y = c_1 e^{\alpha t}cos(\beta t) + c_2 e^{\alpha t}sin(\beta t)$$

We can see that despite starting with imaginary components we end up with a real solution. As mentioned previously $cos(t)$ and $sin(t)$ are linearly independent, so them alone describes all possible solutions. 

### Proof of Complex Roots Formula

Our roots are $\alpha + \beta i$ and $\alpha - \beta i$. Much like the distinct roots case we can write the solution as the following:
$$y = c_1e^{(\alpha + i \beta)t} + c_2e^{(\alpha  - i\beta)t}$$
The solution is ok. If you plug it into the differential equation to check it will work out, however its complex, so its difficult for it represent something of much worth. Lets consider only the first term $c_1e^{(\alpha + i \beta)t}$ we do a little bit of algebraic manipulation to get:
$$y_1 e^{\alpha t}e^{i \beta t}$$
Now we can make use of the infamous eulers formula takes the form $e^{ix} = cos(x) + isin(x)$. Applying eulers formula to our complex expoenetial we get:
$$y_1 = e{\alpha t}(cos(\beta t) + i sin(\beta t))$$
We can do a similar process on the other root of $\alpha - i \beta t$. A nearly identical work is show below to setup $y_2$:
$$y_2 = e^{alpha t}e^{-i \beta t}$$
$$y_2 = e^{\alpha t}(cos(\beta t) + i sin(\beta t))$$
We have two equations are we are allowed to add and subtrac them from each other to get new equations. If we add $y_1$ and $y_2$ then divide by two we get the following:
$$\frac{y_1 + y_2}{2} = e^{\alpha t}cos(\beta t)$$
Now if we subtracting $y_2$ from $y_1$ and then divide by $2i$ we get the following:
$$\frac{y_1 - y_2}{2i} = e^{\alpha t}sin(\beta t)$$


Adding the two solutions we get the general solution for the scenario of two complex roots:
$$y = c_1 e^{\alpha t}cos(\beta t) + c_2 e^{\alpha t}sin(\beta t)$$

### Worked Example (Real Roots)

Consider the following problem (Question 2.2.2):
$$\ddot{y} + 9\dot{y}-10y = 0$$
Substituing in $y = e^{rt}$ and canceling all $e^{rt}$ we get our characteristic equation:
$$r^{2} + 9r - 10 = 0$$
Factoring we find that our roots are the following:
$$(r+10)(r-1) = 0$$
$$r_1 = -10 \quad r_2 = 1$$
Plugging our roots into the general solution for two distinct real roots we get the gerneral solution of:
$$y = c_1 e^{-10 t} + c_2 e^{t}$$

### Worked Example (Repeated Roots)

Consider the following problem:
$$9x^{2} - 12x + 4 = 0$$
Substituing in $y = e^{rt}$ and canceling all $e^{rt}$ we get our characteristic equation:
$$9r^{2} - 12r + 4 = 0$$
The quadratic is factorable and in this case we have repeated roots.
$$(3r-2)(3r-2) = 0$$
$$r = \frac{2}{3} \quad mult. \quad 2$$ 
Plugging our roots into the general solution for two repeated roots we get the gerneral solution of:
$$y = c_1 e^{\frac{2}{3}t} + c_2 t e^{\frac{2}{3}}$$


### Worked Example (Complex Roots)

Consider the following problem:
$$\ddot{y} + 4 \dot{y} + 13y = 0$$
Substituing in $y = e^{rt}$ and canceling all $e^{rt}$ we get our characteristic equation:
$$r^{2} + 4r + 13 = 0$$
The quadratic is not factorable over the reals. Through the quadratic equation we get our two complex roots:
$$r = \frac{-4 \pm \sqrt{16 - 4(1)(13)}}{2} = \frac{-4 \pm 6i}{2}$$
$$r_1 = -2 + 3i \qquad r_2 = -2 - 3i$$
Plugging our roots into the general solution for two complex roots we get the gerneral solution of:
$$y = c_1 e^{-2t}cos(3t) + c_2 e^{-2t}sin(3t)$$

Note that it is perfectly fine if you need to use a system of equations to find your constants in some of questions listed below.

### Problems with Solutions

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

## Higher Order Linear Homogenous Differential Equations


In some of the problems I will use synthetic division and rational roots theorem to get factors. The synthetic division thing usually looks like a table and its an easy way to divide polynomails (given certain conditions).

### Questions and Solutions

**Question 1:** Solve $\dddot{y} -6\ddot{y} + 11\dot{y} - 6y = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/higherOrder/image10.png" alt="Question 1">
</details>

**Question 2:** Solve $\dddot{y} - 3\ddot{y} + 2\dot{y} =0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/higherOrder/image3.png" alt="Question 2">
</details>

**Question 3:** Solve $\dddot{y} + 3\ddot{y} + 3\dot{y} + y =0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/higherOrder/image7.png" alt="Question 3">
</details>

**Question 4:** Solve $\dddot{y} - 5\ddot{y} + 4\dot{y} =0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/higherOrder/image8.png" alt="Question 4">
</details>

**Question 5:** Solve $\dddot{y} - 4\ddot{y} + 3\dot{y} = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/higherOrder/image4.png" alt="Question 5">
</details>

**Question 6:** Solve $y^{(4)} + 4\dddot{y} +6\ddot{y} + 4\dot{y} + y = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/higherOrder/image5.png" alt="Question 6">
</details>

**Question 7:** Solve $y^{(4)} + - 5 \dddot{y} + 10\ddot{y} - 10\dot{y} + 4 =0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/higherOrder/image6.png" alt="Question 7">
</details>

**Question 8:** Solve $y^{(4)} + 3\dddot{y} + 2\ddot{y} - 2\dot{y} = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/higherOrder/image1.png" alt="Question 8">
</details>

**Question 9:** Solve $y^{(4)} + 6\dddot{6} + 8\ddot{y} + 2\dot{y} = 0$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/higherOrder/image2.png" alt="Question 9">
</details>

**Question 10:** Solve $y^{(4)} - 4\dddot{y} + 6\ddot{y} -4\dot{y} + y = 0$ 
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/higherOrder/image9.png" alt="Question 10">
</details>




## Method Undetermined Coefficients

The method of undetermined coefficients is used to solve non-homogenous differential equations like the following:
$$\ddot{y} - 4 \dot{y} + 4y = 8e^{2x}$$
So far we have been used to solving homogenous differential equations (using the characterisitc equation). By removing the 8e^{2x} on the right side of the equation we can get a homogenous differential equation,
$$\ddot{y} - 4 \dot{y} + 4y = 0$$
In differential equations we call the solutuion that solves the non-homogenous secnario the particular solution often denoted $y_p$ and we call the solution that solve the homogenous equation the homogenous solution often denoted $y_h$. Some person a long time ago worried what would happen if he added the particulawr solution and the homogenous solution $y_p + y_h$. Would it still solve either equation and if so which one would it solve?

$$\ddot{y} - 4 \dot{y} + 4y = 8e^{2x} \implies \text{non-homogenous, particular solution}$$
$$\ddot{y} - 4 \dot{y} + 4y = 0$$ implies \text{homogenous, homogenous solution}$$

It turns out that $y_p + y_h$ will solve the non-homogenous equation. More specifically it is the general solution and can enumerate all possible solutions. The proof is pretty simple, but I'm going to prove it for our current scenario because it probably makes more sense that way. If we plug in $y_h + y_p$ into the non-homogenous differential equation we get
$$(y_h + y_p)'' - 4(y_h + y_p)' - 3(y_h + y_p) = 8e^{2x}$$
$$\ddot{y_h} + \ddot{y_p} - 4\dot{y_h} - 4\dot{y_p} -3y_h -3y_p = 8e^{2x} $$
We can then move around the terms a little to get 
$$(\ddot{y_h} -4\dot{y_h} -3y_h) + (\ddot{y_p} -4\dot{y_p} - 3y_p) = 8e^{2x}$$
We can recognize that our left grouping is just our homogenous equation which we know to be equal to zero and our right grouping to be our particular solution which we know to equal $8e^{2x}$. If we do a little substituion we figure out that $y_h + y_p$ is a general solution to the non-homogenous differential equation
$$0 + 8e^{2x} = 8e^{2x} \quad \square$$

The general process of solving with the method of undetermined coefficients is based on the property that $y_h +y_p$ is the general solution. In other word the general solution $y_g$ is $y_g = y_h + y_p$. Firstly we can find our homogenous solution pretty easily. All we need to do is set the right side to zero and do as we always have through using the characeristic equation. The particular solution on the other hand is a little bit more difficult.

Finding some particular solution is based on guessing its general form. For equation $\ddot{y} - 4 \dot{y} + 4y = 8e^{2x}$ we might "randomly" guess that our particular solution is $y_p = Ae^{2x}$ where A is just some constant that we will have to solve for. If check how well our guess is by plugging it into the differentail equation. If our solution is valid then we theoretically should be able to guess at the constant A to find a particular solution $y_p$.

The final part involves getting the general solution $y_g$ which is just adding the homogenous and particular solutions together.  

The above process might be a little hard to visualize so here is an example:

**Worked Example**

Find the general solution to $\ddot{y} - 5\dot{y} + 6y = 12e^{4x}$ and then solve the IVP where the equation subject to the initial conditions $y(0) = 1$ and $\dot{y}(0) = 3$

We know that in order to create our general formula we need both the homogenous solution and the particular solution. We can start by setting the right hand side of equation to zero, so that we can find our homogenous solution.
$$\ddot{y} - 5\dot{y} + 6y = 0$$
You already should be able to solve the equation above so I'm going to be quick about it. Below is all the work necessary,
$$r^2 - 5r + 6 = 0$$
$$(r-3)(r-2) = 0 \implies r=2,3$$
$$y_h = c_1e^{2x} + c2e^{3x}$$
We have our homogenous solution and now we need our particular solution. We have to guess a solution to,
$$\ddot{y} - 5\dot{y} + 6y = 12e^{4x}$$
I'm going to guess that our particular solution take the form of $y_p = Ae^{4x}$ (more about why I guess this later) where $A$ is some constant I will find later. I can plug this solution into our differential equation to try and find the constant A. If I do so I will get,
$$(Ae^{4x})'' - 5(Ae^{4x})' + 6(Ae^{4x}) = 12e^{4x}$$
Applying the derivatives we get,
$$16Ae^{4x} - 20Ae^{4x} + 6Ae^{4x} = 12e^{4x}$$
$$2Ae^{4x} = 12e^{4x}$$
At this point its pretty clear that $A=6$. That means that our particular solution is $y_p = 6e^{4x}$. The final step is to put our homogenous and particular solutions together to get our final general solution.
$$y_g = y_h + y_p$$
$$y_g = c_1e^{2x} + c_2e^{3x} + 6e^{4x}$
Notice that the constants originate from the homogenous solution not the particular solution. One of our initial conditions require $\dot{y}(0)$ so we will differentiate our general solution.
$$y_g = 2c_1e^{2x}+3c_2e^{3x} + 24e^{4x}$$
If we plug in both initial conditions at the same time we get thest two equations:
$$y(0)=1 \implies 1=c_1 +c_2 + 6$$
$$\dot{y}(0) = 3 \implies 3 = 2c_1 + 3c_2 + 24$$
We have a system of equations and with a little bit of basic algebra (you can use matrices if you wish) we can find out that,
$$c_1 = 6 \quad c_2 = -11$$
Putting our constants into our general soluton we get our final answer
$$y_g = 6e^{2x} -11e^{3x} + 6e^{4x} \square \quad$

As promised I'm going to talk about what types of guesses you should make when you are trying to find your particular solution. Below is a table denoting what the right side of the equation looks like and the best thing to guess.

| Right Side of the Equation | What you should guess |
|----------|----------|
| Row 1    | Row 1    |
| Row 2    | Row 2    |
| Row 3    | Row 3    |
| Row 4    | Row 4    |

### Questions and Solutions



**Question 1** Solve for the general solution of $\ddot{y} - 4\dot{y} + 4y = 3e^{8x}$
<details>
  <summary>Solution</summary>
</details>

**Question 2** Solve for the general solution of $\ddot{y} + 2\dot{y} - 3y = 5x^2 + 6x + 2$
<details>
  <summary>Solution</summary>
</details>

**Question 3** Solve  for the general solution of $\ddot{y} - y -2y = 4sin(3x)$
<details>
  <summary>Solution</summary>
</details>

**Question 4** Solve the IVP $\ddot{y} - 4\dot{y} + 4y = 3e^{8x}$ with the initial conditions $y(0)=1$ and $\dot{y}(0) = 2$
<details>
  <summary>Solution</summary>
</details>

**Question 5** Solve the IVP $\ddot{y} + y = 5cos(3x)$ with the initial conditions $y(0)=0$ and $\dot{y}(0) = 1$
<details>
  <summary>Solution</summary>
</details>


**Question 6** Solve the IVP $\ddot{y}-6\dot{y} + 9y = e^{4x} + 12$ with the initial conditions $y(0)=0$ and $\dot{y}(0) = -13$
<details>
  <summary>Solution</summary>
</details>

**Question 7** Solve the IVP $\ddot{y} + 4y = 8sin(x) + 4e^{4x}$ with the initial conditions $y(0)=2$ and $\dot{y}(0) = 1$
<details>
  <summary>Solution</summary>
</details>

For question 8-10 beware of overlaps between the homogenous solutions and your guess. If they are duplicates they will not work and you attach a factor of $x$ to maintain linear independence.

**Question 8** For the differential equation $\ddot{y} + 2\dot{y} -3y = 3x^{3} + 4e^{x} + 5sin(2x) + 6cos(3x)$ 
<details>
  <summary>Solution</summary>
  Solving the homogenous
  $$r^{2} + 2r -3 = 0 \implies r= -2, -1$$
  $$y_h = c_1e^{-2x} + c_2e^{-x}$$
  If we compare our particular guess and our homogenous solution our general solution will have no overlapping terms the best guess is the following:
  $$y_p = Ax^{3} + Bx^{2} + Cx^ + D + Ee^{x} + Fsin(2x) + Gcos(2x) + Hcos(3x) + Isin(3x) \quad \square $$
</details>

**Question 9** For the differential equation $\ddot{y} + 4y = e^{3x} + 2cos(2x) -5sin(3x)$ 
<details>
  <summary>Solution</summary>
  Solving the homogenous:
  $$r^2 + 4 =0 \implies r = 0 \pm 2i$$
  $$y_h = c_1 cos(2x) + c_2sin(2x)$$
  Notice that we have some duplicate terms specifically with our guess for $2cos(2x)$ (which will turn into $cos(2x) + sin(2x)$). Lets keep the homogenous solution portion and attach x to the things that repeat in order to maintain linear independence between solutions
  $$y_p = Ae^{3x} + Bxcos(2x) + Cxsin(2x) + Dcos(3x) + Esin(3x) \quad \square$$
</details>

**Question 10** For the differential equation $\ddot{y} - 4\dot{y} + 4y = e^{2x} + 2sin(x) - 3cos(3x) + x^{2}$
<details>
  <summary>Solution</summary>
  Solving the homogenous:
  $$r^{2} - 4r + 4 \implies r = -2 \text{mult.}2 $$
  $$y_h = c_1e^{-2x} + c_2xe^{-2x}$$
  Notice we are duplicating our solution $e^{2x}$ if we make the normal guess of $Ae^{2x}$. Also notice that if we adjust by adding a single $x$ we are still duplicating $Axe^{2x}$. We need to add $x^{2}$ to keep linear independence amongst solution $Ax^{2}e^{2x}$
  $$y_g = Ax^{2}e^{2x} + Bsin(x) + Csin(x) + Dcos(3x) + Esin(3x) + Fx^{2} + Gx + H \quad \square$$
  
  
  
  
</details>



