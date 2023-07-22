## Line Integrals
So far in calculus we have been used to integrating from one end point to another. In calculus one, you integrated from the lower integrand $a$ to the upper integrand $b$ in the straight line. However, we are in three dimensional space now. Lets say you wanted to integrate between the starting spot $(a,b)$ and $(c,d)$. Well that statement alone is completley ambigous. There are an infinate number of paths going to $(a,b)$ to $(c,d)$. There is the obvious straight line that connects them but its also completely valid to go in circles or in zig zags. 

A line integral involves defining some path and then integrating along that path. Integrating along the path will get you the area of everything beneath the curve. This is best shown with an image (which I did not create):

<img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral.jpg" alt="lineIntegral">

We integrated along the top pink curve and we calculated the area in accordance the amount of $f(x,y)$ that was under said curve. A line integral is usually done with respect to arc length ($ds$) which is pretty intutive since we are integrating everything under the arc. We are still summing up a bunch of rectangles except this time the width of the rectangles is an arc length. When dealing with line integrals we don't write the upper and lower limits of integration instead we just write $C$ denoting that we are dealing with a curve. 
$$\int_{C} f(x,y)ds$$

With line integrals we want to define the curve that we are integrating over as a parametric functions. Something of the form $\vec{r}(t) = \langle g(t), h(t) \rangle$ if we have two independent varibles. This meanas that we want to write our original $f(x,y)$ in terms of our parametric functions, so we replace it with $f(g(t), h(t))$. With our parametric function that makes $ds = \sqrt{(\frac{dx}{dt})^2 + (\frac{dy}{dt})^2}$ which is equiavalent to the magnitude of the tangent vectors $\vec{r}'(t)$. With all that we get our definition for the line integral,

$$\int_{a}^{b} f(g(t), h(t))||\vec{r}'(t)||dt$$

**Worked Example 1**

Consider the line integral over the line segment connecting $(0,0)$ and $(4,3)$,
$$\int_{C} (3x-2y)ds$$
I'm going to start my paramterizing the line segment. A line is made up of an initial point and a slope that gives me the following equation (refer to the section about parametric definition of lines/segments if you don't remember how to do this) 
$$\vec{r}(t) = \langle 4t, 3t \rangle$$
I need to figure out limits of integration. I know that $\vec{r}(0) = \langle 0,0 \rangle$ and $\vec{r}(1) \langle 4,3 \rangle$. That means that our entire line segment is fully traversed from left to right on the interval $t \in [0,1]$. We can also start dealing with our differential which we know is equal to $|\vec{r}'(t)| dt$.
$$\vec{r}'(t) = \langle 4, 3\rangle$$
$$|\vec{r}'(t)| = \sqrt{4^2 + 3^2} = 5$$
So far our integral looks like the following:
$$5\int_{0}^{1} (3x-2y)dt$$
The one outstanding issue is that the function we are integrating over is still in terms of $x$ and $y$. We can replace $x$ and $y$ with there paremetric forms $x= 4t$ and $y=3t$ repsecitvely 
$$5\int_{0}^{1} (3(4t)-2(3t) dt$$
$$30\int_{0}^{1} t(dt)$$
Now going to through the typical integral procedure we get:
$$30(\frac{1}{2} - \frac{0}{2}) = 15 \quad \square$$


**Worked Example 2**

Consider the line integral along the part of a circle that has radius two that lies in the 4th quadrant,
$$\int_{C} 2xy ds$$
We can first paramterize our circle (you might want to remember this paramterization if you don't already. Its just an extension of the definition of the unit circle):
$$\vec{r}(t) = \langle 2cos(t), 2sin(t) \rangle$$
The problem states that we want to integrate along the circle which lies in 4th quadrant that implies that $t \in [\frac{3\pi}{2}, 2\pi]$. Now we can setup our differential.
$$\vec{r}'(t) = \langle -2sin(t), 2cos(t) \rangle$$
$$|\vec{r}(t)| = \sqrt{ 4(sin^{2}(t) + cos^2{2}(t))} = 2$$
Plug what we have so far into our integral we get,
$$4 \int_{\frac{3\pi}{2}}^{2\pi} xy dt$$
If we substituite the definition of $x$ and $y$ for there parametric defintion $x=2cos(t)$ and $y=2cos(t)$ we get,
$$16 \int_{\frac{3\pi}{2}}^{2\pi}  cos(t)sin(t)(dt)$$
The problem has just become a standard calculus 1 integral. If we u-sub with $u=sin(t)$
$$16 \int_{-1}^{0} u(du)$$
Finishing the problem 
$$16(0 - \frac{(-1)^2}{2}) = -8 \quad \square$$
We have a negative area which means that $2xy$ lies majority under xy-plane along our path (in fact since its $2xy$ in the 4th quadrant it lies completely under the xy plane).




Remember for our old integrals that had the following property of adding up limits of integration,
$$\int_{a}^{b} f(x)(dx) +\int_{b}^{c} f(x)(dx) = \int_{a}^{c} f(x)(dx) $$
That property also holds with line integrals. If the behaviors of the curves is nice then we can connect line integrals together to form the answer for an even larger curve. 
$$\int_{C_1} f(x)(ds) +\int_{C_2} f(x)(ds) = \int_{C} f(x)(ds)$$

<img src="https://github.com/sackn/diffeq/blob/main/Images/addingLineIntegral.png" alt="lineIntegralAddition">

Also note that when we use the line integral to find the area under the curve of a path that the following statement is true:
$$\int_{C} f(x)(ds) = \int_{-C} f(x)(ds)  $$
It doesn't matter which way we traverse the path we will always get the same area which seems to line up with logic.

**Question 1:** Find the line integral $\int_{C} (2x-2y)ds$ on the line segment from $(0,0)$ to $(2,4)$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral/image1.png" alt="Question 1">
</details>

**Question 2:** Find the line integral $\int_{C} (x^{2} + y^{2})ds$ on the upper half of the the circle defined by $x^{2} + y^{2} = 9$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral/image3.png" alt="Question 2">
</details>

**Question 3:** Find the line integral $\int_{C} (x^{2} - 2y^{2})ds$ on the the line segment from $(-3,1)$ to $(3,-1)$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral/image2.png" alt="Question 3">
</details>

**Question 4:** Find the line integral $\int_{C} (4xy + 3)ds$ on the entire circle that has a center at $(-1, 2)$ and a radius of 3.
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral/image7.png" alt="Question 4">
</details>

**Question 5:** Find the line integral $\int_{C} (x^2 - y)ds$ on the the line the curve $y=x^{2}$ on the interval $x \in [0,2]$. 

Warning: You will run into a basically impossible integral, so do it numerically. 

<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral/image4.png" alt="Question 5">
</details>

**Question 6:** Consider the line integral $\int_{C} (4x-5y)ds$ where the curve is the graphed on the following image

<img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegralProblem.png" alt="lineIntegralAddition">

<details>
  <summary>Solution</summary>
  Note that in the problem $C_1$ refers to the semi-circle and $C_2$ refers to to the line segment.

  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral/image6.png" alt="Question 6.a">

  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral/image5.png" alt="Question 6.b">
  
</details>



## Line Integrals over Vector Fields
A vector field is created by a function which outputs a vector. A common place that you mean have seen a vector field is in the weather when they show you what direction the wind is blowing. Each vectors size and direction generally tells where and how hard the wind is blowing at that specific point. We can generate those vector fields with vector function which in the case of 2D space take a coordinate pair $(x,y)$ and output a 2D vector with both an x and y component. Below is the vector field representing wind over a certain region (I do not own the image).

<img src="https://github.com/sackn/diffeq/blob/main/Images/vectorField.jpg" alt="Vector Field">

Imagine yourself in sailboat under the effects of a vector field. If you look at the vector field given any starting point you can roughly trace out the path that you might take if only the wind was controlling your boat. Lets take a look at the following vector field which has two different paths on them (that have a specific direction they are traced in). 

<img src="https://github.com/sackn/diffeq/blob/main/Images/vectorFieldIntegral.png" alt="Vector Field Integral">

If you imagine the vector field to represent wind (althought theoretically it can't be wind since it doesn't obey the navier-stokes equations)  what happens when you travel along curve 1 in your sailboat. Well if you travel along curve one you the human have to put a lot of work to complete the route. Almost the entire time the "wind" is blowing against you as you travel. Meanwhile if you take curve 2 you would a lot less work because the wind is "blowing" in your favor. However, this does not mean that you don't have to do any work. The vectors shoot out in lines the only time where your path can be completed fully through the power of wind is if they are perfect lines along the vector field. You still have to put in some work if you want to do the small curves in the path however, it's still much less than if you were going against the wind. In total the wind in doing "positive" work along curve two and "negative" work along curve one. 

The line integral over a vector field measures how much "work" the wind as you sail along a specific path. If the line inetgral comes out to be positive then the wind generally helped you and if the line inetgral come sout be negative then the wind generally went against you. The definition for the line integral is as follows.
$$\int_{C} \vec{F} \cdot d\vec{r}$$
If we parameterize as we did previously our formula then becomes the more common where ($\vec{r}(t)$ represents the parametric definition of all of the variables),
$$\int_{a}^{b} \vec{F}(\vec{r}(t)) \cdot vec{r}'(t) dt$$

The formula for the line integral over a vector field includes a dot product which when you think of it kind of make sense. Remember that the dot product can be defined as $\vec{u} \cdot \vec{v} = |\vec{u}||\vec{v}|cos(\theta)$ where theta is the angle between two vectors. The closer the angle between the vector that represents where your boat is going at that momenet in time (your tangent vector \vec{r}'(t)) and wind vector the more work the wind will do.

<img src="https://github.com/sackn/diffeq/blob/main/Images/dotProductLineIntegral.png" alt="Vector Field Dot Product">

Notice how in scenario one no work is done by the wind since $\theta = \frac{\pi}{2}$ and thus $\vec{u} \cdot \vec{v} =0$. A lot more work is done in scenario two when the angle between the vectors is a lot closer to one implying $\vec{u} \cdot \vec{v}$ is pretty big.

**Worked Example 1**

Consider the vector field $\vec{F} = \langle 3y, -2x \rangle$ and where $C$ is equal to the line segment between $(0,0)$ and $(2,4)$ (this is the curve). Find $\int_{C} \vec{F} \cdot d\vec{r}$

We can start the problem by first paramterizing our line segment. Doing so we get the following
$$\vec{r}(t) = \langle 2t, 4t \rangle \quad t \in [0,1]$$

Note that $\vec{r}(0) = \langle 0,0 \rangle$ and $\vec{r}(1) = \langle 2, 4 \rangle$ which is why our limits go from 0 to 1. For the problem we will also need to take the derivative of our parameritization:

$$\vec{r}(t) = \langle 2,4 \rangle$$
Putting what we have so far into the line integral we have the following:

$$\int_{0}^{1} \langle 3y, -2x \rangle \cdot \langle 2, 4\rangle dt$$

Our vector field is still in terms of $x$ and $y$. In order to match our paramterization we substitute $x=2t$ and $y=4t$.

$$\int_{0}^{1} \langle 12t, -4t \rangle \cdot \langle 2,4 \rangle dt$$

Applying the dot product,

$$\int_{0}^{1} 24t - 16t dt$$

Carrying out the rest of the integral

$$8 \int_{0}^{1} t(dt) = 8(\frac{1^{2}}{2}- \frac{0}{2}) = 3 \quad \square$$

**Worked Example 2**

Consider the vector field $\vec{F} = \langle y, x \rangle$ and where $C$ is the part of the unit circle that exists in the first quadrant.  Find $\int_{C} \vec{F} \cdot d\vec{r}$

First we can starts by parameritizng our curve. Using the definition of a the unit circle and apply the approriate limits we get,
$$\vec{r}(t) = \langle cos(t), sin(t) \rangle \quad t \in [0, \frac{\pi}{2}]$$
We will also need to get the tangent vectors, so we take the derivative of our parameriztion
$$\vec{r}'(t) = \langle -sin(t), cos(t) \rangle$$
Rewriting our vector field in terms of the varible $t$ by subbing $x=cos(t)$ and $y=sin(t)$ we get,
$$\vec{F}(t) = \langle sin(t), cos(t) \rangle$$
Calculating the dot product between our vector field and tangent vectors we get the following,
$$\langle sin(t), cos(t) \rangle \cdot \langle -sin(t), cos(t) \rangle = cos^{2}(t) - sin^{2}(t)$$
This statement can be further simplified through the trig identity $cos(2\theta) = cos^{2}(\theta) - sin^{2}(\theta)$. Putting everything back into the integral,
$$\int_{0}^{\frac{\pi}{2}} cos(2t) dt$$
Finishing the rest of the integral we get,
$$\frac{1}{2}(sin(\pi) - sin(0)) = 0 \quad \square$$








