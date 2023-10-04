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
  <img src="https://github.com/sackn/diffeq/blob/main/Images/undeterminedCoeff/image1.png" alt="Question 1">
</details>

**Question 2** Solve for the general solution of $\ddot{y} + 2\dot{y} - 3y = 5x^2 + 6x + 2$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/undeterminedCoeff/image4.png" alt="Question 2">
</details>

**Question 3** Solve  for the general solution of $\ddot{y} - y -2y = 4sin(3x)$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/undeterminedCoeff/image2.png" alt="Question 3">
</details>

**Question 4** Solve the IVP $\ddot{y} - 4\dot{y} + 4y = 3e^{8x}$ with the initial conditions $y(0)=1$ and $\dot{y}(0) = 2$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/undeterminedCoeff/image6.png" alt="Question 4">
</details>

**Question 5** Solve the IVP $\ddot{y} + y = 5cos(3x)$ with the initial conditions $y(0)=0$ and $\dot{y}(0) = 1$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/undeterminedCoeff/image5.png" alt="Question 5">
</details>


**Question 6** Solve the IVP $\ddot{y}-6\dot{y} + 9y = e^{4x} + 12$ with the initial conditions $y(0)=0$ and $\dot{y}(0) = -13$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/undeterminedCoeff/image7.png" alt="Question 6">
</details>

**Question 7** Solve the IVP $\ddot{y} + 4y = 8sin(x) + 4e^{4x}$ with the initial conditions $y(0)=2$ and $\dot{y}(0) = 1$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/undeterminedCoeff/image3.png" alt="Question 7">
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

