## Line Integrals
So far in calculus we have been used to integrating from one end point to another. In calculus one, you integrated from the lower integrand $a$ to the upper integrand $b$ in the straight line. However, we are in three dimensional space now. Lets say you wanted to integrate between the starting spot $(a,b)$ and $(c,d)$. Well that statement alone is completley ambigous. There are an infinate number of paths going to $(a,b)$ to $(c,d)$. There is the obvious straight line that connects them but its also completely valid to go in circles or in zig zags. 

A line integral involves defining some path and then integrating along that path. Integrating along the path will get you the area of everything beneath the curve. This is best shown with an image (which I did not create):

<img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral.jpg" alt="lineIntegral">

We integrated along the top pink curve and we calculated the area in accordance the amount of $f(x,y)$ that was under said curve. A line integral is usually done with respect to arc length ($ds$) which is pretty intutive since we are integrating everything under the arc. We are still summing up a bunch of rectangles except this time the width of the rectangles is an arc length. When dealing with line integrals we don't write the upper and lower limits of integration instead we just write $C$ denoting that we are dealing with a curve. 
$$\int_{C} f(x,y)ds$$

With line integrals we want to define the curve that we are integrating over as a parametric functions. Something of the form $\vec{r}(t) = \langle g(t), h(t) \rangle$ if we have two independent varibles. This meanas that we want to write our original $f(x,y)$ in terms of our parametric functions, so we replace it with $f(g(t), h(t))$. With our parametric function that makes $ds = \sqrt{(\frac{dx}{dt})^2 + (\frac{dy}{dt})^2}$ which is equiavalent to the magnitude of the tangent vectors $\vec{r}'(t)$. With all that we get our definition for the line integral,

$$\int_{a}^{b} f(g(t), h(t))||\vec{r}'(t)||dt$$

**Worked Example 1**

**Worked Example 2**

Remember for our old integrals that had the following property of adding up limits of integration,
$$\int_{a}^{b} f(x)(dx) +\int_{b}^{c} f(x)(dx) = \int_{a}^{c} f(x)(dx) $$
That property also holds with line integrals. If the behaviors of the curves is nice then we can connect line integrals together to form the answer for an even larger curve. 
$$\int_{C_1} f(x)(ds) +\int_{C_2} f(x)(ds) = \int_{C} f(x)(ds)$$

<img src="https://github.com/sackn/diffeq/blob/main/Images/addingLineIntegral.png" alt="lineIntegralAddition">

Also note that when we use the line integral to find the area under the curve of a path that the following statement is true:
$$\int_{C} f(x)(ds) = \int_{-C} f(x)(ds)  $$
It doesn't matter which way we traverse the path we will always get the same area which seems to line up with logic.


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

