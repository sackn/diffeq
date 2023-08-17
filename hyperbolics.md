
# Hyperbolic Functions

I will mark important results of the solving process with a number, so I can reference them in different places.

## Introduction

Most people are already familiar with the unit circle and the "traditional" trigonmetric functions. We have known for a while that the unit circle is defined to be $x^2 + y^2 = 1$ and that the x-coordinate is equal to the $cos(\theta)$ and the y-coordinate is equal to $sin(\theta)$.

If we only consider the first quadrant we also know that the area of the sector formed with an angle theta is equal to $\frac{\theta}{2}$. This isn't very hard to prove as the area of a sector on the circle is pretty well known to be $A = \frac{1}{2}r^2 \theta$ (in the case of the unit circle $r=1$)

Now instead of a unit circle lets define the unit hyperbola to be $x^2 - y^2 = 1$. Mathematicians wanted functions for hyperbolas that were analagous to that of a circle. Therefore, they decided that on the unit hyperbola that the x-coordinate would be equal to some mystery function $cosh(x)$ (hyperbolic cosine) and the y-coordinate would be equal to some other mystery function $sinh(x)$ (hyperbolic sine).

The functions $cosh(x)$ and $sinh(x)$ serve the exact purpose as $cos(x)$ and $sin(x)$. The only difference is that the hyperbolic functions are used on hyperbolas while trig functions are used on circles. For a unit hyperbola any point is defined as $(cosh(x), sinh(x))$

It would be nice if we continue to develop our theory behind hyperbolas in a similar way to circle. As mentioned previously the area of a sector swept by an angle theta is the $A = \frac{\theta}{2}$ on the unit circle. Mathematacians decided that it would be nice if the unit hyperbolic functions had a similar relationship with the unit hyperbola. They decided that they wanted the area of the "curvy triangle" to be also equal to $\frac{\theta}{2}$. Refer to the image below (technically there are two sides to the hyperbola but we only want to consider the first quadrant):


Going back to our unit circle we know it is defined by $x^2 + y^2 = 1$. We also already know that $x=cos(\theta)$ and $y=sin(\theta)$ and therefore we have the following trig identity:
$$cos^2(\theta) + sin^2(\theta) = 1$$
If we now consider our unit hyperbhola which is defined as $x^2 - y^2 = 1$. We have already defined that x-coordinate is $cosh(x)$ and that our y-coordinate is $sinh(x)$. Plugging our mysterious functions we get a similar relationship to that of the unit circle
$$cosh^2(x) - sinh^2(x) = 1 \qquad (1)$$

The above hyperbolic identitiy will become very important later when we derive the definition of these two mystery functions $cosh(x)$ and $sinh(x)$. As a little bit of a preview the definition of $cosh(x)$ and $sinh(x)$ are the following:
$$cosh(x) = \frac{e^{x} + e^{-x}}{2}  \qquad sinh(x)=\frac{e^{x} - e^{-x}}{2}$$

The definitions are extremely setrange at first glance and in the next part I will derive both of them. 

# Hyperbolic cosine and sin derivation

## The Idea
We can obtain the area of our desired region by subtracting two different parts. Notice the right angle traiangle that we form with the point and the x axis. That region over approximates the area of our region because there exists a portion of the triangle whcih we don't want. That area is left unshaded. If we can find the area of the total triangle and subtract form it the unshaded area then we would have the area of the region we want.

The total area of the triangle isn't very complicated its a triangle and therefore,
$$A_{triangle} = \frac{1}{2}bh$$
$$A_{triangle} = \frac{1}{2}cosh(x)sinh(x) \qquad (2)$$

Our triangle initially starts at the origin and goes out to the point defined by $(cosh(x),sinh(x))$ which is why we can simply substitute our x-coordinate and y-coordinates in.

The area of the unshaded region is a little more complex, so we have to integrate in order to find our area. The unit hyperbola is defined by the equation $x^2 - y^2 = 1$. In our deriviation we are going to consider only the portion of the curve that lies in quadrant one (so positive roots always) and we are going to integrate with respect to x (left to right). With those constraints the curve we would be integrating under would just a manipulated hyperbola formula in terms of $x$ which is $y= \sqrt{x^2 -1}$. That would give us the integral:

$$\int_{a}^{b} \sqrt{x^2 - 1}dx$$

However, this integral means nothing since we I haven't discussed what the limits of integration would be. The starting limit $a$ is the point at which the hyperbola intersects the x-axis on the POSITIVE side.

$$x^2 - y^2 = 1$$
$$x^2 - 0^2 = 1$$
$$a=1$$

We know our starting limit to be one always however, our limit $b$ changes. It shouldn't be that much of a stretch to call the function $cosh(x)$ our upper limit. If you look at the image this should be pretty intuitive. That leaves us with the following integral:

$$\int_{1}^{cosh(x)} \sqrt{x^2 - 1}dx$$

By definition the area of the region of interest is $\frac{x}{2}$ (which again is analagous to traditional trig functions and the unit circle, refer to the third image in introduction). If we put all of the parts together that means that the following relationship must be true (where the first term is $A_{triangle}$):

$$\frac{x}{2} = \frac{1}{2}cosh(x)sinh(x) - \int_{1}^{cosh(x)} \sqrt{x^2 - 1}dx \qquad (3)$$

---

## The Integral (kind of annoying)
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


The first step to evlauating this integral involves the substituion $tan^2(\theta)= sec^{\theta} - 1$. If we distribute we can then split the integral into two different ones:
$$\int_{1}^{cosh(x)} sec^3(\theta) d\theta - \int_{1}^{cosh(x)}  sec(\theta) d\theta \qquad (4)$$

Both of the integrals are extremely common and notably annoying to do. Most people have them memorized and below I listed the the general solutions to each integral (I do the derivations for each of these integrals later):
$$\int sec(x)(dx) = ln|tan(x) + sec(x)| \qquad (5)$$
$$\int sec^3(x)(dx) = \frac{1}{2}sec(x)tan(x) + \frac{1}{2} ln|tan(x) + sec(x)| \qquad (6) $$

---

### Integrating $sec^3(x)$

We can do the first integral by using the formula listed above for $sec^3(x)$ (Equation 6). Remeber that we are integrating with respect to theta not the generic varibable $x$. 
$$\int sec^3(\theta)(d\theta) = \frac{1}{2}sec(\theta)tan(\theta) + \frac{1}{2} ln|tan(\theta) + sec(\theta)| $$
We can just plug in our limits yet since they were defined when we were dealing with the differential $dx$ (we did not change them during the substituion). We want need to find a way to express it in terms of $x$ before evalulating it with $1$ and $cosh(x)$. Lucklily at the start we made the assertion that $sec(\theta) = x$. That means whereever we see a $sec(\theta)$ in our formula we can just replace it with an $x$.

$$\int sec^3(\theta)(d\theta) = \frac{1}{2}xtan(\theta) + \frac{1}{2} ln|tan(\theta) + x| $$

However, what do we do with $tan(\theta)$. If we know $sec(\theta)$ then $tan(\theta)$ isn't very hard to derive. We know the relationship $tan^2(\theta) = sec^2{\theta} - 1$ to be true. If we manipulate a little we get $tan(\theta) = \sqrt{sec^2(\theta) - 1}$ (we only consider the 1st quadrant so the $\pm$ is always $+$) . Using the fact that $sec(\theta) = x$ again we get that:

$$tan(\theta) = \sqrt{x^2 - 1}$$

Plugging all of this in we can now put our limits of integration $a = 1$ and $b = cosh(x)$ in (the lower limit a=1 is zero):
$$\int_{1}^{cosh(x)} sec^3(\theta)(d\theta) = \frac{1}{2}x\sqrt{x^2 - 1} + \frac{1}{2} ln|\sqrt{x^2 - 1} + x \quad \vert_{1}^{cosh(x)} $$
$$\frac{1}{2}cosh(x)\sqrt{cosh^2{x} - 1} + \frac{1}{2} ln|cosh(x) + \sqrt{cosh^2(x) -1}| - 0$$
There is a pretty nice substituion that will further clean up our solution. We already previously discussed that $cosh^2(x)-sinh^2(x) = 1$. If we move terms around a little we  can replace all $\sqrt{cosh^2(x)} -1$ with $sinh(x)$. Doing so give us our first equation.
$$\frac{1}{2}cosh(x)sinh(x) + \frac{1}{2} ln|cosh(x) + sinh(x)| \qquad (7)$$

---

### Integrating $sec(x)$

Integrating the 2nd integral is much like the first. We can use the general form for the integral of sec(x) to help us integrate (Equation 5). We will have the same issue with differential giving us $\theta$ preventing us from directly plugging in our limits which were meant for $x$. However the same substituions are still valid $sec(\theta) = x$ and $tan(\theta) = \sqrt{x^2 - 1}$. Below is the work for the entire integral:

$$\int_{1}^{cosh(x)} sec(\theta) d\theta = ln|tan(\theta) + sec(\theta)| \quad \vert_{1}^{cosh(x)} $$
$$= ln|\sqrt{x^2 - 1} + x| \vert_{1}^{cosh(x)} \quad \vert_{1}^{cosh(x)}$$
$$= ln|\sqrt{cosh^2(x) -1} + cosh(x)| - 0$$
$$= ln|sinh(x) + cosh(x)| \qquad (2) \qquad (8)$$

---
### Putting it back together

We spent a lot of time doing the individual integral that you may have forgotten why we were even doing them in the same place. The area of the unshaded region which we are subtracting for our traingle to get the region that we want is the following integral (Equation 4):
$$\int_{1}^{cosh(x)} sec^3(\theta) d\theta - \int_{1}^{cosh(x)}  sec(\theta) d\theta$$

In the previous two sections we integrated each term seperately. If we sub our previous results into the integral we can get the general solution for the area of the unshaded region (Subbing equation 7 and then equation 8),

$$\frac{1}{2}cosh(x)sinh(x) + \frac{1}{2} ln|cosh(x) + sinh(x)| - ln|sinh(x) + cosh(x)| $$
$$A_{unshaded} = \frac{1}{2}\text{cosh}(x)sinh(x) - \frac{1}{2} ln|cosh(x) + sinh(x)|$$


Again we are searching of the highlighted region $A_{highlighted}$ which by definition has the area $\frac{x}{2}$. In other words the following must be true:

$$\frac{x}{2} = A_{triangle} - A_{unshaded}$$

We have already found $A_{triangle}$ and $A_{unshaded}$. Plugging our them we get that our area $\frac{x}{2}$ is equal to: 

$$\frac{x}{2} = (\frac{1}{2}cosh(x)sinh(x)) - (\frac{1}{2}cosh(x)sinh(x) - \frac{1}{2} ln|cosh(x)+sinh(x)|)$$
$$x = ln|cosh(x)+ sinh(x)|$$

We can then expoentiate both sides to then get relationship
$$cosh(x) + sinh(x) = e^x \qquad (9)$$

---
### A System

From the work in the previous section we got that $cosh(x) + sinh(x) = e^{x}$ (Equation 9). If we wish to derive both $cosh(x)$ and $sinh(x)$ we need another equation. We already this second equation and its the definition of a unit hyperbola $cosh^2(x) - sinh^2(x) = 1$ (Equation 1). We now have the two following equation and we can solve this non-linear system to get an solution for our two unknowns $cosh(x)$ and $sinh(x)$.
$$cosh(x) + sinh(x) = e^{x} \qquad cosh^2(x) - sinh^2(x) = 1$$

To solve this system we can start by factoring our right equation and substiting in our other equation.
$$(cosh(x)-sinh(x))(cosh(x) + sinh(x)) = 1$$
$$(cosh(x)-sinh(x))e^x = 1$$
$$cosh(x)-sinh(x) = e^{-x} \qquad (10)$$

We now have this manipulate formula which is a way easier to deal with. We can then take this equation (equation 10) and perform elimination by adding it onto $cosh(x)+sinh(x) = e^{x}$ (Addsing equation 10 to equation 9)
$$cosh(x) + sinh(x) = e^{x}$$
$$+(cosh(x)-sinh(x) = e^{-x})$$

$$2cosh(x) = e^{x} + e^{-x}$$

Moving the two over we get our definition for $cosh(x)$:
$$cosh(x) = \frac{e^{x} + e^{-x}}{2}\qquad (11)$$

We can then bring back out equations, but this time instead of adding them together we can subtract them (subtratcing equation 10 from equation 9). Doing so will give us the definition for hyperbolic sine.
$$cosh(x) + sinh(x) = e^{x}$$
$$-(cosh(x)-sinh(x) = e^{-x})$$

$$2sinh(x) = e^{x} - e^{-x}$$
$$sinh(x) = \frac{e^{x} - e^{-x}{2} \qquad (12)$$

---
### Results

We found that the two following hyperobolic definition (equation 11 and equation 12)
$$cosh(x) = \frac{e^{x} + e^{-x}}{2}  \qquad sinh(x)=\frac{e^{x} - e^{-x}}{2}  $$

---
## Extra: Integral of $sec(x)$ and $sec^3(x)$$
