# Hyperbolic Functions

Hyperbolic is kind of a misfit mathematics topic. It doesn't necessarily fit into any specific class, like Calculus 1 or Caclulus 1. At my high school, hyperbolic is taught in AP Calculus BC. I will mark important results of the solving process with a number so I can reference them in different places.

## Introduction

Most people are already familiar with the unit circle and the "traditional" trigonmetric functions. We have known for a while that the unit circle is defined to be $x^2 + y^2 = 1$ and that the x-coordinate is equal to $cos(\theta)$ and the y-coordinate is equal to $sin(\theta)$.

<img src="https://github.com/sackn/diffeq/blob/main/Images/hyperbolic/image1.png" alt="Image 1">

If we only consider the first quadrant, we also know that the area of the sector formed with an angle theta is equal to $\frac{\theta}{2}$. This isn't very hard to prove as the area of a sector on the circle is pretty well known to be $A = \frac{1}{2}r^2 \theta$ (in the case of the unit circle, $r=1$)

<img src="https://github.com/sackn/diffeq/blob/main/Images/hyperbolic/image2.png" alt="Image 2">

Now instead of a unit circle, let's define the unit hyperbola as $x^2 - y^2 = 1$. Mathematicians wanted functions for hyperbolas that were analogous to those of a circle. Therefore, they decided that on the unit hyperbola, the x-coordinate would be equal to some mystery function ($cosh(x)$ (hyperbolic cosine) and the y-coordinate would be equal to some other mystery function ($sinh(x)$ (hyperbolic sine).

The functions $cosh(x)$ and $sinh(x)$ serve the same exact purpose as $cos(x)$ and $sin(x)$. The only difference is that hyperbolic functions are used on hyperbolas, while trig functions are used on circles. For a unit hyperbola, any point is defined as $(cosh(x), sinh(x))$.

It would be nice if we continued to develop our theory behind hyperbolas in a similar way to a circle. As mentioned previously, the area of a sector swept by an angle theta is $A = \frac{\theta}{2}$ on the unit circle. Mathematicians decided that it would be nice if the unit hyperbolic functions had a similar relationship with the unit hyperbola. They decided that they wanted the area of the "curvy triangle" to also be equal to $\frac{\theta}{2}$. Refer to the image below (technically, there are two sides to the hyperbola, but we only want to consider the first quadrant):
<img src="https://github.com/sackn/diffeq/blob/main/Images/hyperbolic/image3.png" alt="Image 3">

Going back to our unit circle, we know it is defined by x^2 + y^2 = 1. We also already know that $x=cos(\theta)$ and $y=sin(\theta)$, and therefore we have the following trigonometric identity:
$$cos^2(\theta) + sin^2(\theta) = 1$$
If we now consider our unit hyperbhola, which is defined as $x^2 - y^2 = 1$, We have already defined that the x-coordinate is $cosh(x)$ and that our y-coordinate is $sinh(x)$. Plugging in our mysterious functions, we get a similar relationship to that of the unit circle.
$$cosh^2(x) - sinh^2(x) = 1 \qquad (1)$$

The above hyperbolic identity will become very important later when we derive the definition of these two mystery functions, $cosh(x)$ and $sinh(x)$. As a little bit of a preview, the definitions of $cosh(x)$ and $sinh(x)$ are the following:
$$cosh(x) = \frac{e^{x} + e^{-x}}{2}  \qquad sinh(x)=\frac{e^{x} - e^{-x}}{2}$$

The definitions are extremely strange at first glance, and in the next part, I will derive both of them.

# Hyperbolic cosine and sin derivation

## The Idea
We can obtain the area of our desired region by subtracting two different parts. Notice the right-angle triangle that we form with the point and the x axis. That region overestimates the area of our region because there is a portion of the triangle that we don't want. That area is left unshaded. If we can find the area of the total triangle and subtract from it the unshaded area, then we will have the area of the region we want.

The total area of the triangle isn't very complicated; it's a triangle, and therefore,
$$A_{triangle} = \frac{1}{2}bh$$
$$A_{triangle} = \frac{1}{2}cosh(x)sinh(x) \qquad (2)$$

Our triangle initially starts at the origin and goes out to the point defined by $(cosh(x),sinh(x)),$ which is why we can simply substitute our x-coordinate and y-coordinates in.

The area of the unshaded region is a little more complex, so we have to integrate in order to find our area. The unit hyperbola is defined by the equation $x^2 - y^2 = 1$. In our deriviation, we are going to consider only the portion of the curve that lies in quadrant one (so positive roots always), and we are going to integrate with respect to x (left to right). With those constraints, the curve we would be integrating under would just be a manipulated hyperbola formula in terms of $x$, which is $y= \sqrt{x^2 -1}$. That would give us the integral:

$$\int_{a}^{b} \sqrt{x^2 - 1}dx$$

However, this integral means nothing since we haven't discussed what the limits of integration would be. The starting limit (a) is the point at which the hyperbola intersects the x-axis on the positive side.

$$x^2 - y^2 = 1$$
$$x^2 - 0^2 = 1$$
$$a=1$$

We know our starting limit to be one always; however, our limit $b$ changes. It shouldn't be that much of a stretch to call the function $cosh(x)$ our upper limit. If you look at the image, this should be pretty intuitive. That leaves us with the following integral:

$$\int_{1}^{cosh(x)} \sqrt{x^2 - 1}dx$$

By definition, the area of the region of interest is $\frac{x}{2}$ (which again is analogous to traditional trig functions and the unit circle; refer to the third image in the introduction). If we put all of the parts together, that means that the following relationship must be true (where the first term is $A_{triangle}$):

$$\frac{x}{2} = \frac{1}{2}cosh(x)sinh(x) - \int_{1}^{cosh(x)} \sqrt{x^2 - 1}dx \qquad (3)$$

---

## The Integral (kind of annoying)
The longest part of the derivation is the integral of the unshaded area. Below is the work to compute the entire integral.

$$ \int_{1}^{cosh(x)} \sqrt{x^2 - 1}dx$$

First, we are going to do a trigonometric substitution. Remember the trigonometric relationship $cos^2(\theta) + sin^2(\theta) = 1$? If we divide everything by $cos^2(\theta)$ and move around the terms a little, we get the following relationship:
$$tan^2(\theta) = sec^2{\theta} - 1$$

Notice that if you make that substitution, $x=sec(\theta)$. Ignoring the differential and limits of integration for now, we will get the following integral:
$$\int_{1}^{cosh(x)} \sqrt{sec^2 - 1} dx$$

We chose this identity for a reason. Under the square root, we clearly have an alternative definition for $tan^2(\theta)$ (tan^2(\theta) = sec^2{\theta} - 1). If we make that substitution, we are left with:
$$\int_{1}^{cosh(x)} tan(\theta) dx$$

We made a variable substitution, so we must also change the differential. Our substitution was $x=sec(\theta)$. If we differentiate both sides, we get the following: $dx = sec(\theta)tan(\theta) d\theta$. Replacing our current differential with the new one, we get the integral:

$$\int_{1}^{cosh(x)} tan^2(\theta)sec(\theta) d\theta $$

The first step to evaluating this integral involves the substitution $tan^2(\theta)= sec^{\theta} - 1$. If we distribute, we can then split the integral into two different ones:
$$\int_{1}^{cosh(x)} sec^3(\theta) d\theta - \int_{1}^{cosh(x)}  sec(\theta) d\theta \qquad (4)$$

Both of the integrals are extremely common and notably annoying to do. Most people have them memorized, and below I listed the general solutions to each integral (I will do the derivations for each of these integrals later):
$$\int sec(x)(dx) = ln|tan(x) + sec(x)| \qquad (5)$$
$$\int sec^3(x)(dx) = \frac{1}{2}sec(x)tan(x) + \frac{1}{2} ln|tan(x) + sec(x)| \qquad (6) $$

---

### Integrating $sec^3(x)$

We can do the first integral by using the formula listed above for $sec^3(x)$ (Equation 6). Remember that we are integrating with respect to theta, not the generic variable $x$.

$$\int sec^3(\theta)(d\theta) = \frac{1}{2}sec(\theta)tan(\theta) + \frac{1}{2} ln|tan(\theta) + sec(\theta)| $$

We can just plug in our limits since they were defined when we were dealing with the differential $dx$ (we did not change them during the substitution). We need to find a way to express it in terms of $x$ before evaluating it with $1$ and $cosh(x)$. Lucky for us, at the start, we made the assertion that $sec(\theta) = x$. That means wherever we see a "sec(\theta) in our formula, we can just replace it with an "x.

$$\int sec^3(\theta)(d\theta) = \frac{1}{2}xtan(\theta) + \frac{1}{2} ln|tan(\theta) + x| $$

However, what do we do with $tan(\theta)$? If we know $sec(\theta)$, then $tan(\theta)$ isn't very hard to derive. We know the relationship $tan^2(\theta) = sec^2{\theta} - 1$ to be true. If we manipulate a little, we get $tan(\theta) = \sqrt{sec^2(\theta) - 1}$ (we only consider the 1st quadrant, so the $\pm$ is always $+$). Using the fact that $sec(\theta) = x$ again, we get that:

$$tan(\theta) = \sqrt{x^2 - 1}$$

Plugging all of this in, we can now put our limits of integration $a = 1$ and $b = cosh(x)$ in (the lower limit a = 1 is zero):
$$\int_{1}^{cosh(x)} sec^3(\theta)(d\theta) = \frac{1}{2}x\sqrt{x^2 - 1} + \frac{1}{2} ln|\sqrt{x^2 - 1} + x \quad \vert_{1}^{cosh(x)} $$
$$\frac{1}{2}cosh(x)\sqrt{cosh^2{x} - 1} + \frac{1}{2} ln|cosh(x) + \sqrt{cosh^2(x) -1}| - 0$$
There is a pretty nice substitution that will further clean up our solution. We already discussed that $cosh^2(x)-sinh^2(x) = 1$. If we move terms around a little, we can replace all $\sqrt{cosh^2(x)} -1$ with $sinh(x)$. Doing so gives us our first equation.
$$\frac{1}{2}cosh(x)sinh(x) + \frac{1}{2} ln|cosh(x) + sinh(x)| \qquad (7)$$

---

### Integrating $sec(x)$

Integrating the second integral is much like the first. We can use the general form for the integral of sec(x) to help us integrate (Equation 5). We will have the same issue with differential giving us $\theta$, preventing us from directly plugging in our limits, which were meant for $x$. However, the same substituions are still valid: $sec(\theta) = x$ and $tan(\theta) = \sqrt{x^2 - 1}$. Below is the work for the entire integral:

$$\int_{1}^{cosh(x)} sec(\theta) d\theta = ln|tan(\theta) + sec(\theta)| \quad \vert_{1}^{cosh(x)}$$

$$ln|\sqrt{x^2 - 1} + x| \vert_{1}^{cosh(x)} \quad \vert_{1}^{cosh(x)}$$

$$ln|\sqrt{cosh^2(x) -1} + cosh(x)| - 0$$

$$ln|sinh(x) + cosh(x)| \qquad (8)$$

---

### Putting it back together

We spent so much time doing the individual integrals that you may have forgotten why we were even doing them in the same place. The area of the unshaded region that we are subtracting from our train to get the region that we want is the following integral (Equation 4):
$$\int_{1}^{cosh(x)} sec^3(\theta) d\theta - \int_{1}^{cosh(x)}  sec(\theta) d\theta $$

In the previous two sections, we integrated each term separately. If we sub our previous results into the integral, we can get the general solution for the area of the unshaded region (substituting equation 7 and then equation 8).

$$\frac{1}{2}cosh(x)sinh(x) + \frac{1}{2} ln|cosh(x) + sinh(x)| - ln|sinh(x) + cosh(x)| $$
$$A_{unshaded} = \frac{1}{2}\text{cosh}(x)sinh(x) - \frac{1}{2} ln|cosh(x) + sinh(x)|$$

Again, we are searching for the highlighted region $A_{highlighted}$, which by definition has the area $\frac{x}{2}$. In other words, the following must be true (Equation two and A_{unshaded}$, which is directly above):

$$\frac{x}{2} = A_{triangle} - A_{unshaded}$$

We have already found $A_{triangle}$ and $A_{unshaded}$. Plugging them in, we get that our area $\frac{x}{2}$ is equal to:

$$\frac{x}{2} = (\frac{1}{2}cosh(x)sinh(x)) - (\frac{1}{2}cosh(x)sinh(x) - \frac{1}{2} ln|cosh(x)+sinh(x)|)$$
$$x = ln|cosh(x)+ sinh(x)|$$

We can then raise both sides to the power of $e$ to get the following relationship:
$$cosh(x) + sinh(x) = e^x \qquad (9)$$

---
### A System of Equations

From the work in the previous section, we got that $cosh(x) + sinh(x) = e^{x}$ (Equation 9). If we wish to derive both $cosh(x)$ and $sinh(x)$, we need another equation. We already have this second equation, which is the definition of a unit hyperbola. $cosh^2(x) - sinh^2(x) = 1$ (Equation 1). We now have the two following equations, and we can solve this non-linear system to get a solution for our two unknowns, $cosh(x)$ and $sinh(x)$.
$$cosh(x) + sinh(x) = e^{x} \qquad cosh^2(x) - sinh^2(x) = 1$$

To solve this system, we can start by factoring in our right equation and substituting in our other equation.
$$(cosh(x)-sinh(x))(cosh(x) + sinh(x)) = 1$$
$$(cosh(x)-sinh(x))e^x = 1$$
$$cosh(x)-sinh(x) = e^{-x} \qquad (10)$$

We now have this manipulative formula, which is way easier to deal with. We can then take this equation (equation 10) and perform elimination by adding it to $cosh(x)+sinh(x) = e^{x}$ (adding equation 10 to equation 9).
$$cosh(x) + sinh(x) = e^{x}$$
$$(cosh(x)-sinh(x) = e^{-x})$$

$$2cosh(x) = e^{x} + e^{-x}$$

Moving the two over, we get our definition for $cosh(x)$:
$$cosh(x) = \frac{e^{x} + e^{-x}}{2}\qquad (11)$$

We can then bring back the equations, but this time instead of adding them together, we can subtract them (subtracting equation 10 from equation 9). Doing so will give us the definition of a hyperbolic sine.
$$cosh(x) + sinh(x) = e^{x}$$
$$-(cosh(x)-sinh(x) = e^{-x})$$

$$2sinh(x) = e^{x} - e^{-x}$$

$$sinh(x) = \frac{e^{x} - e^{-x}}{2} \qquad (12)$$

---
### Results

We found that the two following hyperbolic definitions (equation 11 and equation 12)
$$cosh(x) = \frac{e^{x} + e^{-x}}{2}  \qquad sinh(x)=\frac{e^{x} - e^{-x}}{2}  \qquad \square$$

---
## Extra: Integral of sec(x) and sec(x) cubed
I recommended looking through the $sec(x)$ integral first because the integral of $sec^3(x)$ requires you to also integrate $sec(x)$.

### Integral of sec(x)

##

$$\int sec(x) dx$$

To make the integral easier to solve through substitution, we can multiply the top and bottom by $sec(x) + tan(x)$.

$$\int \frac{sec(x)(sec(x) + tan(x))}{sec(x) + tan(x)}dx$$
$$\int \frac{sec^2(x) + sec(x)tan(x))}{sec(x) + tan(x)}dx$$

We can then do a u-substitution, setting $u= sec(x) + tan(x)$.

$$\int \frac{sec^2(x) + sec(x)tan(x))}{u}\frac{du}{sec^2(x) + sec(x)tan(x)}$$
$$\int \frac{1}{u} du = ln|u| + c$$
We can then do a u-substitution, setting $u= sec(x) + tan(x)$. Substituting in our original value for $u$, we get the integral of sec(x).

$$\int sec(x) dx = ln|sec(x) + tan(x)| + c \qquad \square$$ 

##

### Integral of sec(x) cubed

$$\int sec^3(x) dx$$

We can split up $sec^3(x)$ into a factor of $sec(x)$ and $sec^2(x)$. Then, we can apply integration by parts, making $u = sec(x)$ and $dv = sec^2(x)$. Following through, we get:

$$sec(x)tan(x) - \int sec(x)tan^2(x)dx$$

Using the trigonmetric identity $tan^2(x) = sec^2(x) - 1$, we can expand our one integral into two.

$$\int sec^3(x)dx = sec(x)tan(x) - \int sec^3(x) dx + \int sec(x) dx$$

Notice that we have $sec^3(x)$ on both sides of the equation, which means that we can add $sec^3(x)$ on both sides and then divide by two to get an equivalent statement.

$$\int sec^3(x) dx = \frac{1}{2} sec(x)tan(x) + \frac{1}{2} \int sec(x) dx$$

Now all we have to do is substitute in the integral of $sec(x)$ which was derived earlier.

$$\int sec^3(x) dx = \frac{1}{2} sec(x)tan(x) + \frac{1}{2} ln|sec(x) + tan(x)| + c \qquad \square$$

##
