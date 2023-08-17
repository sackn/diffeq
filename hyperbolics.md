
## Hyperbolic cosine and sin derivation

### The Idea
We can obtain the area of our desired region by subtracting two different parts. Notice the right angle traiangle that we form with the point and the x axis. That region over approximates the area of our region because there exists a portion of the triangle whcih we don't want. That area is left unshaded. If we can find the area of the total triangle and subtract form it the unshaded area then we would have the area of the region we want.

The total area of the triangle isn't very complicated its a triangle and therefore,
$$A_{triangle} = \frac{1}{2}bh$$
$$A_{triangle} = \frac{1}{2}cosh(x)sinh(x)$$

Our triangle initially starts at the origin and goes out to the point defined by $(cosh(x),sinh(x))$ which is why we can simply substitute $x=cosh(x)$ and $y=sinh(x)$

The area of the unshaded region is a little more complex, so we have to integrate in order to find our area. The unit hyperbola is defined by the equation $x^2 - y^2 = 1$. In our deriviation we are going to consider only the portion of the curve that lies in quadrant one (so positive roots always) and we are going to integrate with respect to x (left to right). With those constraints the curve we would be integrating under would just a manipulated hyperbola formula in terms of $x$ which is $y= \sqrt{x^2 -1}$. That would give us the integral:

$$\int_{a}^{b} \sqrt{x^2 - 1}dx$$

However, this integral means nothing since we I haven't discussed what the limits of integration would be. The starting limit $a$ is the point at which the hyperbola intersects the x-axis on the POSITIVE side.

$$x^2 - y^2 = 1$$
$$x^2 - 0^2 = 1$$
$$a=1$$

We know our starting limit to be one always however, our limit $b$ changes. It shouldn't be that much of a stretch to call the function $cosh(x)$ our upper limit. If you look at the image this should be pretty intuitive. That leaves us with the following integral:

$$\int_{1}^{cosh(x)} \sqrt{x^2 - 1}dx$$

By definition the area of the region of interest is $\frac{x}{2}$ (which again is analagous to traditional trig functions and the unit circle). If we put all of the parts together that means that the following relationship must be true (where the first term is $A_{triangle}$):

$$\frac{x}{2} = \frac{1}{2}cosh(x)sinh(x) - \int_{1}^{cosh(x)} \sqrt{x^2 - 1}dx$$

### The Integral
The longest part of the derivation is the integral of the unshaded area. Below is the work to compute the entire integral
$$ \int_{1}^{cosh(x)} \sqrt{x^2 - 1}dx$$
First our going to do a trigonmetric substituion. Remember the trig relationship $cos^2(\theta) + sin^2(\theta) = 1$? If we divide everything by $cos^2(\theta)$ and move around the terms a little we get the following relationship:
$$tan^2(\theta) = sec^2{\theta} - 1$$
Notice that if make that substituion $x=sec(\theta)$. Ignoring the differential and limits of integration for now we will get the following integral:
$$\int_{1}^{cosh(x)} \sqrt{sec^2 - 1} dx$$
We chose this trig identitiy for a reason. Under the square root we convienly have an alternative definition for $tan^2(\theta)$ (tan^2(\theta) = sec^2{\theta} - 1). If we make that substituion we are left with:
$$\int_{1}^{cosh(x)} tan(\theta) dx$$
We made a varible substituion, so we must also change the differential. Our substituion was $x=sec(\theta)$. If we differentiate both sides we get the following $dx = sec(\theta)tan(\theta) d\theta$. Replacing our current differential with the new one we get the integral:
$$\int_{1}^{cosh(x)} tan^2(\theta)sec(\theta) d\theta $$
