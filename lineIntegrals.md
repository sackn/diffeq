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


**Line Integrals with Respect to a certain Varible**

So far we have calculated line integrals with respect to all the variables in the system, but sometimes you want to only a line integral with respect to one varible (disregarded any contribution from the other varibles). In the 2D we know that the $ds$ is composed to $dx$ and $dy$. Take the following drawing:

<img src="https://github.com/sackn/diffeq/blob/main/Images/ds.png" alt="ds">

We have used $ds$ so far in line integrals accounting for contributions of both $dx$ and $dy$. However, what if we want to integrate with only respect to $x$ completely forgetting about the contributions of $y$ to the integral. Well its pretty simple take the $ds$ equation and just remove $dy$. Doing so will leave with just $dx$. 

$$\int_{C} f(x,y) dx $$

If we account for the fact that our line integral uses we parametric curve we get the following formula for the line integral over the curve $C$ with respect to $x$
$$= \int_{a}^{b} f(t) \dot{x} dt$$
Logically follows that the line inetgral with repect to y is the following,
$$= \int_{a}^{b} f(t) \dot{y} dt$$


That's all cool but, what exactly does the integral of a curve with respect to a single varible look like? I don't have fancy images to explain this, so the first minute of this video has a really good analogy and visuals. I did not create the video: [https://www.youtube.com/watch?v=2fcT5X5tUvM](url). As mentioned in the video think of it a projection on a specific plane (XZ plane in the case of dx and YZ plane in the case dy). 

I also like to think of by the definition of the integral. The a line integral we take a small step along the arc $ds$ which is a right triangle made up of $dx$ and $dy$. Imagine drawing these small arcs on top of the curve then just visualize them with only there there x component (line integral with respect to x) or only y component (line integral with respect to y)

**Worked Example 3**

Consider the line integral $\int_{C} xy dx$ along a curve $C$, where $C$ is the line segment between $(1,2)$ and $(3,4)$. This problem is an example of a line integral done with respect to the varible $x$. That means before we integrate our integral has to be of the form,
$$= \int_{a}^{b} f(t) \dot{x} dt$$
We can start the problem by getting the paramerization to our integral. Our paramerization for our line inetgral goes as follows,
$$\vec{r}(t) = \langle 1 + 2t ,2 + 2t \rangle \quad t \in [0,1]$$
Since we are integrating with respect to only $x$ we only need to differentiate the x component.
$$\dot{x}(t) = 2$$
Plugging what we have so far into the integral we have,
$$2 \int_{0}^{1} xy dt$$
The only thing left we have to do before we integrate is to turn $f(x,y)$ into $f(t)$ by subbing in our paramerization $x = 1 + 2t$ and $y = 2+2t$.
$$2 \int_{0}^{1} (1+2t)(2+2t)$$
Finishing off this integral we get that,
$$2 \int_{0}^{1} 2 + 6t + 4t^{2} = $$
$$2((2(1)  + 3(1)^{2} + \frac{4}{3}(1)^{3} - 0) = \frac{38}{3} \quad \square$$

When it comes to line integrals the phrase positive direction and negative direction doesn't have much meaning do the ambiguity of the path which is why the way that you traverse a path doesn't effect the area. However when you are integrating with respect to a singular variable there does exist a "positive" and "negative direction", so the following statements are true (similar to the fact that $\int_{a}^{b} f(x) dx$ = - \int_{b}^{a} f(x) dx$):
$$\int_{C} f(x)dx = -\int_{C} f(x) dx$$
The same is true for any other varible

The concept of doing line integrals with respect to a single varible also scaled up to higher dimensions as you make expect. There literally is no difference outside of the fact that you just have more variables.

### Questions and Solutions 
For the questions you can assume positive orientation (counter-clockwise movement, left to right traversal)

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

**Question 7:** A curve $C$ is defined as a circle of radius two on $\theta \in [\frac{\pi}{6}, \frac{\pi}{3}]$ find $\int_{C} \frac{x^2-y^{2}}{x} dx$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral2/image3.png" alt="Question 7">
</details>

**Question 8:** A curve $C$ is defined as $y=e^{x}$ on $x \in [0,2]$ find $\int_{C} \frac{x^{2}}{y}dy$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral2/image1.png" alt="Question 8">
</details>

**Question 9:** A curve $C$ is defined as the line segment between $(2,0,0)$ and $(0,2,2)$ find \int_{C} $\frac{x^{2} - y^{2}}{x^2 + y^2} dz$

Warning: One of the integrals is difficult and should probably be estimated for the sake of the problem

<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral2/image2.png" alt="Question 9">
</details>

**Question 10:** A curve $C$ is defined as the line segment between $(0,0,0)$ and $(1,2,3)$ find $\int_{C} (x^2 + y^2 + z^2)dx$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral2/image4.png" alt="Question 10">
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

If we continue on the wind analogy then the following statement shouldn't be that far fetched
$$\int_{C} \vec{F} d\vec{r}  = -\int{C} \vec{F} \cdot d\vec{r}$$
If you traverse a path where the wind is against you, then if you traverse the path in reverse direction the wind will be in your favor. 

**Worked Example 1 Again**

Consider the same problem from the first example. When we traced the positive direction we went from $(0,0)$ to $4,3$. We did this by moving our parametric varible $t$ from $0$ to $1$. If we traverse the other way we would want to go from $(4,3)$ back to $(0,0)$ meaning we would shift our $t$ from $1$ to $0$. That would make our integral the following (refer to example 1)

$$8 \int_{1}^{0} t(dt)$$

From first year calculus you might remember the following fact:
$$\int_{b}^{a} f(x) dx=  -\int_{a}^{b} f(x) dx$$
If we apply the same to our integral we just get the negative version of our original answer and that answer supports the claim that $\int_{C} \vec{F} d\vec{r}  = -\int_{C} \vec{F} \cdot d\vec{r}$.

$$8 \int_{0}^{1} t(dt)$$

You may remember intergating with respect to a specific varible. The defintion of a line integral over a vector field plays complete into the ability to integrate with respect to a single varible. For a scenario with two indepdent varibles we know the vector field $\vec{F}$ to take the form of $\langle P, Q \rangle$ and we know that $d\vec{r}$ can be decomposed into $\langle dx, dy \rangle$. Those two facts make the following also true,
$$\int_{C} \vec{F} \cdot d\vec{r} = \int_{C} P dx + \int_{C} Q dy$$



**Question 1:** Given the vector field $\vec{F} = \langle x^{2}, y^{2} \rangle$ where $C$ is the part of a circle centered at the originwi wth a radius of two that lies in the first quadrant find $\int_{C} \vec{F} \cdot d\vec{r}$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegralOverVectors/image8.png" alt="Question 1">
</details>

**Question 2:** Given the vector field $\vec{F} = \langle 3y, -2x \rangle$ where $C$ is the curve caused by $y=x^2$ on the interval $x \in [0,2]$ find $\int_{C} \vec{F} \cdot d\vec{r}$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegralOverVectors/image7.png" alt="Question 2">
</details>

**Question 3:** Given the vector field $\vec{F} = \langle 2xy , x^2, z \rangle$ and the line segment going from $(0,0,0)$ to $(1,2,3)$ calculate $\int_{C} \vec{F} \cdot d\vec{r}$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegralOverVectors/image1.png" alt="Question 1">
</details>

**Question 4:** Given the vector field $\vec{F} = \langle \frac{y}{x^2 + y^2}, \frac{-x}{x^2+y^2} \rangle$ where $C$ is the unit circle on $[\pi, \frac{3\pi}{2}]$ calculate $\int_{C} \vec{F} \cdot d\vec{r}$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegralOverVectors/image5.png" alt="Question 1">
</details>


**Question 5:** Given the vector field $\vec{F} = \langle y^{2} + 2xy, x^2 + 2y \rangle$ on the part of the ellipse $\frac{x^2}{9} + \frac{y^2}{4} = 1$ that lies in the 4th quadrant. 
<details>
  <summary>Solution</summary>
  The solution is kind of messy, but the final answer is $3\pi - 3$ (hopefully it's right)

  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegralOverVectors/image10.png" alt="Question 5.a">
  
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegralOverVectors/image2.png" alt="Question 5.b">
  
</details>

**Question 6:** Given the vector field $\vec{F} = \langle 2x, 3y\rangle$ calculate $\int_{C} \vec{F} \cdot d\vec{r}$ given that the the curve is the following image

<img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegralProblem.png" alt="lineIntegralAddition">

<details>
  <summary>Solution</summary>
  Note that in the problem $C_1$ refers to the semi-circle and $C_2$ refers to to the line segment.
  
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegralOverVectors/image3.png" alt="Question 6.a">
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegralOverVectors/image9.png" alt="Question 6.a">

</details>


**Question 7:** Given the vector field $\vec{F} = \langle yz, xz, xy \rangle$ where $C$ is a helix defined as $\vec{r}(t) = \langle cos(t), sin(t), t\rangle$. Calculate $\int_{C} \vec{F} \cdot d\vec{r}$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegralOverVectors/image6.png" alt="Question 7">
</details>

**Question 8:** Given the vector field $\vec{F} = \langle y^{2}, z, xz \rangle$ and $C$ being the line segment going from $(1,2,3)$ to $(4,5,6)$ find $\int_{C} \vec{F} \cdot d\vec{r}$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegralOverVectors/image4.png" alt="Question 8">
</details>

## Conservative Vector Field and the Fundamnetal Theorem of Line Integrals

You might remember the fundamental theorem of calculus which states and I quote "If $f$ is continous on the interval $[a,b]$ and $F $is any function that satisifies $F'(x) = f(x)$ on this interval" then,
$$\int_{a}^{b} f(x) dx = F(b) - F(a)$$
The fundamnetal theorem of calculus makes the claim that if you find the anti-derivative to a function then the only thing you have to know to find the area of an interval are the locations of its end points. However, the fundamnetal theorem puts some has some a pre-conditions to the theorem. The function much be continous on the interval in question. It must in behave "nicely" for it to count.

All of these caveats and details are almost the exact same for the fundamnetal theorem of line integrals. The fundamnetal theorem of line integrals considers a smooth curve $C$ defined by some $\vec{r}$ on the inteval $t \in [a,b]$. It also consider some function $f$ who has a continous gradient vector $\nalba f$on the curve C. If both are satisifed then the following must be also true:

$$\int_{C} \nabla f \cdot d\vec{r} = f(\vec{r}(b)) - f(\vec{r}(a))$$

Where $\vec{r}(b)$ and $\vec{r}(a)$ represent some start and end points. There is a lot to unpack here so lets take it one step at a time. First concerning the gradient vector field of $f$ which is $\nabla f$. There is another definition I want to introduce briefly and thats the idea of a conservative vector field.A function is considered conservative if there exists some function $g$ such that $g = \nabla f$. In other words, the function $f$ is represents the gradient vector field of some function. The function $f$ is often called a potential function.

The word potential might ring a few bells. You might think of gravitational potential energy for example and how it could represnt a potential function. Gravitiational potential energy (atleast on small scales asumming #U_{Gravity} = mgh #) increases at a linear rate the farther away from the ground you are ($h$ increases). If gravitional potential energy can represent a potential function like $f$ then what is its corresponding $g$ such that $g = \nabla f$. The function g in this case would be gravitional force more specifically f= mg (where g is reference to gravity, and f is force). Its not very hard to get between the two since in this case the gradient of a function acts exactly like a derivative since we are working in a singular dimension.

Since gravitional force has a potential function that implies that it is a conservaitve vector field, but what properties does a conservative vector field even have. Gravity is a vector field and gravity will do work on an object. You let go of an object and gravity will apply work onto the object and push it down towards the Earth. Consider the two paths of an object as falls down:
<img src="https://github.com/sackn/diffeq/blob/main/Images/conservtaiveVectorField.png" alt="Question 8">

Both boxes (red and blue) start at the same spot and end at the same height (the dotted line), but there paths to that point are very different which box was helped out more by the gravity field (gravity did more work)?

If you named either box your incorrect. In fact despite, the difference in paths gravity did the same amount of work on both of them. For the blue box gravity was always helping the box fell straight down. However, for the red box it fell much further down than the blue box initially meaning gravity put in more work. However, to get back to the same height as the blue box the red box had to go against gravity (so gravity did negative work). After that entire process the more work that was done at the beginning on the red box as it descended canceled out with the negative work taht had to be done to bring it back up.

The main property of the a conservative vector field is that the work done on an object is path indepdendent. It doesn't matter what route a path took if they up at the same exact spot then the same amount of work is done. This leads extremely well into the fundamnetal theorem of line integrals which formally states that any path over a conservative vector field is only depend on its end points.

The line integral verf a conservative vector field doesn't care about the path it just cares about where it ends. The work matters on where it ends up not how it gets there. In the image both take different routes, but there end points are the exact same (they start at the same point and end at the same point). The fundamental theorem also tells us that we can the work done is just calculated through the difference between the potential at each point $F(\vec{r}(b)) - F(\vec{r}(a)$. A lot of writing time for an example:

**Worked Example 1**

Consider the vector field $\vec{F} = \langle xy \rangle$. Calculate the line integral $\int_{C} \nabla \vec{F} \cdot d\vec{r}$ on the line segment going from $(0,1)$ to $(2,3)$.

Noramlly for a problem like this I would say paramerized the line segment, but we don't need to in this case becasue we know that by defintion that $\nabla F$  is a conservative vector field. Our problem becomes simple because we only need to worry about the starting point $(0,1)$ and the ending point $(2,3)$. Using the fundamnetal theorem of line integral we get that,

$$ \text{Potential at the End} - \text{Potential at Start}=\vec{F}(2,3) - \vec{F}(0,1)$$
Evalulating the results we can easily get the answer,
$$2(3) - 1(0) = 6 \quad \square$$

For the sake of completnees I'm going to do a sanity check, so below is the work for the entire problem without invoking the fundamnetal theorem of line integrals to skip most of the process:
$$\vec{r}(t) = \langle 2t, 1 + 2t \rangle \quad t \in [0,1]$$
$$\vec{r}'(t) = \langle 2, 2 \rangle $$
$$F_x = y \quad F_y =x \implies \nabla F = \langle y,x \rangle$$
$$\int_{0}^{1} \langle 1 + 2t,2t \rangle \cdot \langle 2,2 \rangledt$$
$$\int_{0}^{1} (2+ 8t)dt = (2(1) + 4(1) - 0) = 6 \quad \square$$

**How to tell if a vector field is conservative**

Althought we will talk about the curl operator in more in depth later,  a conservative vector field can also be defined as a vector field where $curl \vec{F} = 0$. In simple terms, the vector field isn't swirly. That would corroborate with the belief that gravity is a conservative vector field since we know gravity to be not "swirly" as we know it to just act downwards. 

Let there be a vector field $\vec{F} = \langle P,Q \rangle$ on an open simply connected region. Then if the function P and Q are continous first order partial derivatives and
$$\frac{\partial }{\parital y} = \frac{\partial Q}{\partial x}$$
is true then the vector field $\vec{F}$ is conservative

When you get to the curl operator you might recognize the $\frac{\partial }{\partial y} - \frac{\partial Q}{\partial x} = 0$ is considered $curl \vec{F} = 0$ in 2D aswell.

We can easily tell if a vector field is conservative, but how do we go about actually finding the potential function. If let $\vec{g} = \langle P,Q \rangle$ be our function then we know there is a potential function $f$ such that $g = \nabla f$. We can decompose this statement to get
$$\langle P,Q \rangle = \langle \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \rangle$$
Setting components each to each other we get the two equations,
$$P = \frac{\partial f}{\partial x} \quad Q = \frac{\partial f}{\partial y}$$
We can then integrate and what not to get values for our potential function. This is best shown through an example.

**Worked Example 2**

If you one day look into differential equations you wil see type of differential equation called the exact equation. Exact equations are based completley on potential functions and conservative fields. I was running out of problems to use so I took a part of a problem from the exact equations section (Problem from Lebl 1.8.1):

Consider the vector field $(2xy + x^{2})dx + (x^2 + y^2 + 1)dy = 0$ prove thats its conservative and find its potential function.





