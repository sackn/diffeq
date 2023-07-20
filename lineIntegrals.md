## Line Integrals
So far in calculus we have been used to integrating from one end point to another. In calculus one, you integrated from the lower integrand $a$ to the upper integrand $b$ in the straight line. However, we are in three dimensional space now. Lets say you wanted to integrate between the starting spot $(a,b)$ and $(c,d)$. Well that statement alone is completley ambigous. There are an infinate number of paths going to $(a,b)$ to $(c,d)$. There is the obvious straight line that connects them but its also completely valid to go in circles or in zig zags. 

A line integral involves defining some path and then integrating along that path. Integrating along the path will get you the area of everything beneath the curve. This is best shown with an image (which I did not create):

<img src="https://github.com/sackn/diffeq/blob/main/Images/lineIntegral.jpg" alt="lineIntegral">

We integrated along the top pink curve and we calculated the area in accordance the amount of $f(x,y)$ that was under said curve. A line integral is usually done with respect to arc length ($ds$) which is pretty intutive since we are integrating everything under the arc. We are still summing up a bunch of rectangles except this time the width of the rectangles is an arc length. When dealing with line integrals we don't write the upper and lower limits of integration instead we just write $C$ denoting that we are dealing with a curve. 
$$\int_{C} f(x,y)ds$$

With line integrals we want to define the curve that we are integrating over as a parametric functions. Something of the form $\vec{r}(t) = \langle g(t), h(t) \rangle$ if we have two independent varibles. This meanas that we want to write our original $f(x,y)$ in terms of our parametric functions, so we replace it with $f(g(t), h(t))$. With our parametric function that makes $ds = \sqrt{(\frac{dx}{dt})^2 + (\frac{dy}{dt})^2}$ which is equiavalent to the magnitude of the tangent vectors $\vec{r}'(t)$. With all that we get our definition for the line integral,

$$\int_{C} f(g(t), h(t))||\vec{r}'(t)||dt$$

**Worked Example**



Remember for our old integrals that had the following property of adding up limits of integration,
$$\int_{a}^{b} f(x)(dx) +\int_{b}^{c} f(x)(dx) = \int_{a}^{c} f(x)(dx) $$
That property also holds with line integrals. If the behaviors of the curves is nice then we can connect line integrals together to form the answer for an even larger curve. 
$$$$

<img src="https://github.com/sackn/diffeq/blob/main/Images/addingLineIntegral.png" alt="lineIntegralAddition">
