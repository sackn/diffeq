## Multivaraible Chainrule

## Directional Derivatives and Graident Vectors
Now that we are in higher dimensions the word rate of change becomes a little ambigous. In 2D when someone set rate of change it was obvious what they meant. They were talking about $\frac{\Delta y}{\Delta x}$. In 3D space, the word rate of change could be the rate of change going to the "right", the rate of change going "up", or even the rate of change if you walk Northeast. Generally there is different meaning of rate of change depending on what direction you are taking the derivative in. 

Define the directional deriative as the rate of change of some function $f(x,y)$ in the direction of a unit vector $\vec{u} = \langle a,b \rangle$. The directional deriative is often denoted as $D_{\vec{u}}f(x,y)$. The limit defintion of the directional is as follows:

$$ D_{\vec{u}}f(x,y) = \lim\limits_{\Delta h \to 0} = \frac{f(x + a\Delta h, y + b\Delta h) - f(x,y)}{\Delta h}$$

IF we want a way to easily evalulate our directional derivative we introduce a new function in terms of a single variable (paramterize our original function) and we it equal to the current function $h(z) =f(x,y)$. In order to match our parameterization We  redefine our $x$ and $y$ varibles to be $x= x_0+ az$ and $y y_0 + bz$ respectively. Now we take the the deriative of parametric function we can use multivarible chain rule to expand it into the following:

$$\dot{g}(z) = \frac{\partial f}{\partial x} \frac{\partial x}{\partial z} + \frac{\partial f}{\partial y} \frac{\partial y}{\partial z}$$

We know that $\frac{\partial f}{\partial x}$ and $\frac{\partial f}{\partial y}$ are the partial deraitive of $f(x,y)$ with respect to x and y. We can also calculate $\frac{\partial x}{\partial z}$ and $\frac{\partial y}{\partial z}$. Doing all of this will yield us the formula for the directional deriative. 

$$ D_{\vec{u}}f(x,y) = f_x a + f_y b$$

There is often a more common way to write the directional deriative. In math we define the gradient vector of $f(x,y)$ to be vector containing the partial derivaitves of every varible in $f(x,y)$. In the case of two dimensions our gradient vector might look like the following:
$$\nabla f(x,y) = \langle f_x , f_y \rangle$$
If you remember the howe the dot product works that means that we can also write the directional derivative as the following:
$$D_{\vec{u}}f(x,y)  = \langle f_x, f_y \rangle \cdot \langle a, b \rangle = f_x a + f_y b$$

The defintion of the derivative is easily scaled up to higher dimensions. Under an increase in the varaibles the following will always hold:
$$D_{\vec{u}}f(x,y) = \nabla f(x,y) \cdot \vec{u}$$
For example in 3D space, 

$$D_{\vec{u}}f(x,y,z) = \langle f_x, f_y, f_z \rangle \cdot \langle a, b, c \rangle $$

A special property of the gradient vector is that it is orthagonal to the level curves. In other the gradient vector always points in the direction where rate of change maximized. If you evalulate the gradient vector then you fidn the greatest rate of change.  Below is a graph of countours of some function and its "gradient vector field".
<img src="https://github.com/sackn/diffeq/blob/main/Images/gradientVector.jpg" alt="gradientVector">

Remember when doing problems to always make sure the direction vector they give you is a unit vector. Otherwise, the that fact that the magnitude is not one will scale the answer. Remember the formula for a unit vector:
$$\vec{u} = \frac{\vec{v}}{||\vec{v}||}$$

### Problems and Solution

**Question 1:** For the function $f(x,y) = x^{2} + 3y^{2}$ find the directional derivative at the point $(1,2)$ in the direction of $\vec{v} = \langle 2, -1 \rangle$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/directional/image5.png" alt="Question 1">
</details>

**Question 2:** For the function $f(x,y,z) = 2xy + 3yz -4xz$ find the directional derivative at the point $(1,-1,2)$ in the direction of $\vec{v} = \langle 1,1,1 \rangle$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/directional/image1.png" alt="Question 2">
</details>

**Question 3:** For the function $f(x,y,z) = e^{xy} + sin(z)$ find the directional derivative at the point $(0, 1, \pi)$ in the direction of $\vec{v} = \langle -1,2,3 \rangle$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/directional/image3.png" alt="Question 3">
</details>

**Question 4:** For the function $f(x,y) = \frac{x^2}{4} + y^{2} -3x + 2$ find the direction in which the directional derivative at the point (2,1 ) is maxiumum.
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/directional/image2.png" alt="Question 4">
</details>

**Question 5:** For the function $f(x,y,z) = x^{2} + 2y^{2} + 3z^{2}$ determine the direction where the directional derivative is zeor at the point $(1,-1,2)$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/directional/image4.png" alt="Question 5">
</details>

### Tangents Planes and Approximations
As you may remember in calculus one we were able to define a tangent line at some given point. In 2D space, the general form for a tangent line at point $(x_0, f(x_0) )$ of the function $f(x,y)$ was:
$$y-f(x_0) = f'(x_0)(x-x_0)$$ 
The tangent line acted a linear approximation around the point x_0. Any point around x_0 could be approximated by evaluating the tangent line. If we expand to higher dimensions we no longer have a tangent line, but a tangent plane. We know that the equation for a plane is as follows:
$$a(x-x_0) + b(y-y_0) + c(z-z_0) = 0$$
The equation for the tangent plane is a natural extension of the equation for a tangent line. We simply just add an extra term to the right side. The equation for a tangent plane of some graph $f(x,y)$ at some point $(x,y,f(x,y))$ is,
$$z - f(x,y) = f_x(x-x_0) + f_y(y-y_0)$$
Notice how instead of just the slope we mention both partials with respect to x and y instead. Visualize our tangent plane by thinking of the "tangent" lines for x and y. On the image below $\vec{T}_x$ represent the directon of tangent line if we only consider x and $\vec{T}_y$ rpresent the direction of tangent line if we only consider y. Together if we combine the directions of the two lines we form the plane which is marked as $A$ in the image. So naturally the addition of two "tangent vectors" should give us the tangent plane formed between them.

<img src="https://github.com/sackn/diffeq/blob/main/Images/tangentPlane.png" alt="Tangent Plane">

If you not convinced of my hand-waving reasoning for the formula refer to the proof on this website (which I do not own): [https://tutorial.math.lamar.edu/Classes/CalcIII/TangentPlanes.aspx](url)

Much like how we used tangent lines for approximations we can also use tangents planes for approximations. We can plug in any point near $(x_0, y_0)$ and get a reasonable approximation of it through the evaluating the tangent plane. 

The idea of the tangent plane can also be easily expanded to higher dimensions. For example a tangent plane for a function of three varibles would look like the following:
$$z - f(x,y,z) = f_x(x-x_0) + f_y(y-y_0) + f_z(z-z_0)$$

**Question 1:** Given the function $f(x,y) = x^{2} + 2y^{2}$ find the tangent plane at the point $(1, -1)$
<details>
  <summary>Solution</summary>
  Finding the Partial derivatives and evaluating the function at $(1,-1)$
  $$\frac{\partial f}{\partial x} = 2x \quad \frac{\partial f}{\partial y} = 4y$$
  $$f_x(1,-1) = 2 \quad f_y(1,-1) = -4$$
  $$f(1, -1) = 3$$
  Finding our tanget plane equation
  $$T(x,y) = 2(x-1) -4 (y+1) + 3$$
</details>

**Question 2:** Given the function $f(x,y) = \sqrt{x} + y$ find the tangent plane at the point $(4,3)$
<details>
  <summary>Solution</summary>
  Finding the Partial derivatives and evaluating the function at $(4,3)$
  $$\frac{\partial f}{\partial x} = \frac{1}{2\sqrt{x}} \quad \frac{\partial f}{\partial y} = 1$$
  $$f_x(1,-1) = 2 \quad f_y(1,-1) = -4$$
  $$f(4,3) = 5$$
  Finding our tangent plane eqauation
  $$T(x,y) = 2(x-4) -4(y-3) + 5$$
 
</details>

**Question 3:** Given the function $f(x,y) = sin(x) + cos(y)$ find the tangent plane at the point $(\frac{\pi}{4}, \frac{\pi}{3})$
<details>
  <summary>Solution</summary>
  Finding the Partial derivatives and evaluating the function at $(\frac{\pi}{4}, \frac{\pi}{3})$
  $$\frac{\partial f}{\partial x} = cos(x) \quad \frac{\partial f}{\partial y} = -sin(y)$$
  $$f_x(\frac{\pi}{4}, \frac{\pi}{3}) = \frac{\sqrt{2}}{2} \quad f_y(\frac{\pi}{4}, \frac{\pi}{3}) = -\frac{\sqrt{3}}{2}$$
  $$f(\frac{\pi}{4}, \frac{\pi}{3}) = \frac{\sqrt{2} + 1}{2} $$
  Finding our plane equation
  $$T(x,y) = \frac{\sqrt{2}}{2}(x-x_0)  + -\frac{\sqrt{3}}{2}(y-y_0) + \frac{\sqrt{2} + 1}{2} $$
  
</details>

**Question 4:** Given the function $f(x,y) = e^{x} + ln(2y)$ find the tangent plane at the point $(1,1)$ and use it to approximate $(1.02, 0.98)$
<details>
  <summary>Solution</summary>
  Finding the Partial derivatives and evaluating the function at $(1,1)$
  $$\frac{\partial f}{\partial x} = e^{x} \quad \frac{\partial f}{\partial y} = \frac{1}{y}$$
  $$f_x(1,1) = e \quad f_y(1,1) = 1$$
  $$f(1,1) = e + ln(2)$$
  Finding our plane equation
  $$T(x,y) = e(x-1) + (y-1) + e + ln(2)$$
  Approximating the point $(1.02 , 0.98)$
  $$T(1.02, 0.98) = e(1.02 - 1) + (0.98 - 1) + e + ln(2)$$
  $$T(1.02, 0.98) \approx 3.446$$
</details>

**Question 5:** Given the function $f(x,y) = x^{2} + 2y - cos(xy)$ find the tangent plane at $(1,2)$ and use it to approximate $(1.01, 1.95)$
<details>
  <summary>Solution</summary>
  Finding the Partial derivatives and evaluating the function at $(1,2)$
  $$\frac{\partial f}{\partial x} = 2x + ysin(xy) \quad \frac{\partial f}{\partial y} = 2 + xsin(xy)$$
  $$f_x(1,2) = 2 + 2sin(2) \quad f_y(1,2) = 2 + sin(2)$$
  $$f(1,2) = 5 - cos(2)$$
  Finding our plane equation
  $$T(x,y) = (2+2sin(2))(x - 1) + (2+sin(2))(y-2) + 5 - cos(2)$$
  $$T(x,y) \approx (3.819)(x-1) + (2.909)(y-2) + 5.416$$
  Approximating the point $(1.01, 1.95)$
  $$T(1.01, 1.95) \approx (3.819)(1.01-1) + (2.909)(1.95-2) + 5.416 $$
  $$T(1.01, 1.95) \approx 5.309$$
</details>

## Relative Maxiumum and Minimums
Remember from calculus one we could find relative extrema by finding when the deraitive of the function is zero. There exist is a similar process for finding extrema in higher dimensions. Just as clarification critical points and extrema aren't quite the same thing. All extrema are critical points, but a critical point is any point where the derivative is equal to zero OR point is undefined (and an extrema must actual be greater than or less than its neighboring points). 

Critical points for a function of two variables occurs if either:
- $f_x(a,b) = 0$ AND $f_y(a,b) = 0$
- Either $f_x(a,b)$ or $f_y(a,b)$ is undefined

It is very important to understand that the first condition is an AND statement. We do not have a critical point if only one of the partial deraitives is zero. 

**Relative Maximum or Relative Minimum**

In your calculus one class you may have drawn a sign graph over the tangent lines. If the slopes were positive then turned negative then the critical point was relative max. If the slopes were negative then became positive then the critical point was a relative min. If it was neither of those scenarios then you didn't have an extrema at all. 

For example you might have been given $f(x) = x^{2}$. You would have recognized that $f'(x) = 2x$ and that it has an critical point at 0. Most of the time you would follow up with drawing like the following where you would note that the derivative of values prior to the critical point were negative and the deriative of values after the critical point were positive. Since, the tangent lines were going from negative to positive you knew that $x=0$ was a relative minimum
<img src="https://github.com/sackn/diffeq/blob/main/Images/relMin.png" alt="relMin">

However this is a little different in higher dimensions. There are sine graph depending on what direction you come in form. Refer to the following image which shows all three possibilites of a critical point:
<img src="https://github.com/sackn/diffeq/blob/main/Images/criticalPoint.png" alt="criticalPoint">

A saddle point is technically both a relative maximum and a relative minimum. If you approach it from one axis you get a relative minimum if you approach from a different axis you get a relative maximum. For 3D graphs, there exist a test called the 2nd partial tests which can be used to tell whether a critical point is a relative minimum, relative maximum, or a saddle point.

**2nd Partials Test**

Suppose you have some critical point $(a,b)$ where the 2nd order partial deraivatives are constant. Define:
$$D(a,b) = f_{xx}(a,b)f_{yy}(a,b) - [f_{xy}(a,b)]^{2}$$

Classifying the point:
- $D > 0 \quad f_{xx}(a,b) > 0 \implies$ Local Minimum
- $D > 0 \quad f_{xx}(a,b) < 0 \implies$ Local Maximum
- $D < 0 \implies$ Saddle Point
- $D = 0 \implies$ requires different methods to classify

## Absolute Extrema and Lagrange Multipliers
From calculus one, you might remember plugging in all critical points and boundary points to find your absolute extrema. In 2D dimensions you have to include the boundary points of your interval. This is not different in 3D space however, your boundary "points" are not points, but functions. You would have a function each side (four boundary functions in total) each with there own critical points and boundary points. That can become quite tedious to deal with so there is an alternative method.

If your interested in reading about how to do it without the method I'm going to talk about refer to the following website (which I do not own): [https://tutorial.math.lamar.edu/Classes/CalcIII/AbsoluteExtrema.aspx](url)

The most common way to find absolute extrema is done through the Lagrange Multiplier method. The lagrange multiplier method has the user solve the following system (in the case of three dimensions)
$$\nabla f(x,y,z) = \lambda \nabla g(x,y,z)$$
$$g(x,y,z) = k$$
In the lagrange multiplier method $f(x,y,z)$ represents the function you want to get the absolute extrema for and $g(x,y,z)$ represents some constraint function. For example, if you want to get the absolute extrema of $f(x,y,z)$  along a sphere of radius one then  $g(x,y,z) = x^{2} + y^{2} + z^{2}=4 $. The constant $\lambda$ is also called the lagrange mulitplier. 

It's key that you look into the system of equations and realize that for the 3D example its not system of two equations, but a system of four equations. In the upper equation you are setting two vectors equal to each other so what you really have is the following:
$$f_x = \lambda g_x$$
$$f_y = \lambda g_y$$
$$f_z = \lambda g_z$$
$$g = k$$

Also a quick mention before the worked example. The lagrange multiplier method can easily be scaled up to higher dimensions. The only thing that would change was the size of the constraint and gradient vector. For example a 4D lagrange setup might look like the following where you have a system of five equations:
$$\nabla f(x,y,z,w) = \lambda \nabla g(x,y,z,w)$$
$$g(x,y,z,w) = k$$

**Worked Example**

Consider the function $f(x,y) = 2x + 3y$ subject to the constraint $x^{2} + y{2} = 25$. We first indentify $f(x,y) = 2x + 3y$ as the function we want to "optimize" and $g(x,y) = x^{2} + y^{2} = 25$ as our constraint function. We can find the gradient vector of each of these functions. Doing so will get us the following:
$$\nabla f(x,y) = \langle f_x, f_y \rangle = \langle 2, 3 \rangle$$
$$\nabla g(x,y) = \langle g_x, g_y \rangle = \langle 2x, 3y \rangle$$
Our the system of equation is the following:
$$\langle 2, 3\rangle = \lambda \langle 2x,3y \rangle$$
$${x^2} + y^{2} = 25$$
Splitting everything up into its own equation we get the following:
$$2 = 2x\lambda$$
$$3 = = 3y\lambda$$
$$x^{2} + y^{2} = 25$$
If we solve the first two equations for $x$ and $y$ we respecitvely we can plug them into the third equation to get the the value of the lagrange multiplier.
$$(\frac{1}{\lambda})^{2} + (\frac{1}{\lambda})^{2} = 25$$
$$\lambda = \pm \frac{\sqrt{2}}{5}$$
We have two different possible lagrange multiplier corresponding with two different critical points. Lets first consider the positive scenario where $\lambda = \frac{\sqrt{2}}{5}$. Plugging in $\lambda$ into $x$ and $y$ we can get the location of the critical point.
$$x = \frac{1}{\frac{\sqrt{2}}{5}} \implies x = \frac{5}{\sqrt{2}} $$
$$y = \frac{1}{\frac{\sqrt{2}}{5}} \implies y = \frac{5}{\sqrt{2}}$$
Now plugging in the location of the critical point into the original function $f(x,y)$ we can get its value.
$$f(\frac{5}{\sqrt{2}},  \frac{5}{\sqrt{2}}) = \frac{25}{sqrt(2)} \approx 17.678$$
Now lets consider the other scenarios where $-\frac{\sqrt{2}}{5}$. We plug into $x$ and $y$ to get the location of the critical point. 
$$x = \frac{1}{-\frac{\sqrt{2}}{5}} \implies x = -\frac{5}{\sqrt{2}} $$
$$y = \frac{1}{-\frac{\sqrt{2}}{5}} \implies y = -\frac{5}{\sqrt{2}}$$
Now plugging our newly found location of the critical point into the original function $f(x,y)$ we can get its value.
$$f(-\frac{5}{\sqrt{2}}, -\frac{5}{\sqrt{2}}) = -\frac{25}{sqrt(2)} \approx -17.678 $$

We evaluated all of the possible lagrange multipliers and we can now compare them. We have an absolute maximum at the point $(\frac{5}{\sqrt{2}},  \frac{5}{\sqrt{2}})$ with a value of around 17.678. We then have an absolute minimum at the point $(-\frac{5}{\sqrt{2}},  -\frac{5}{\sqrt{2}})$ with a value around -17.678. 


### Practice Questions$
Shimamota Questions mainly partial derivatives, tangent approximations, and gradient vectors.

**Shimamota Question 4.1.1:**
<details>
  <summary>Part A Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image13.png" alt="Shimamota 4.1.1.a">
</details>
<details>
  <summary>Part B Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image3.png" alt="Shimamota 4.1.1.b">
</details>
<details>
  <summary>Part C Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image6.png" alt="Shimamota 4.1.1.c">
</details>
<details>
  <summary>Part D Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image7.png" alt="Shimamota 4.1.1.d">
</details>

**Shimamota Question 4.1.2:**
<details>
  <summary>Part A Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image11.png" alt="Shimamota 4.1.2.a">
</details>
<details>
  <summary>Part B Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image16.png" alt="Shimamota 4.1.2.b">
</details>
<details>
  <summary>Part C Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image14.png" alt="Shimamota 4.1.2.c">
</details>
<details>
  <summary>Part D Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image9.png" alt="Shimamota 4.1.2.d">
</details>

**Shimamota Question 4.1.4:**
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image4.png" alt="Shimamota 4.1.4">
</details>

**Shimamota Question 4.1.6:**
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image10.png" alt="Shimamota 4.1.6.a">
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image2.png" alt="Shimamota 4.1.6.b">
</details>

**Shimamota Question 4.1.8:**
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image12.png" alt="Shimamota 4.1.8">
</details>

**Shimamota Question 4.1.10**
<details>
  <summary>Part A Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image1.png" alt="Shimamota 4.1.10.a">
</details>
<details>
  <summary>Part B Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image8.png" alt="Shimamota 4.1.10.b">
</details>

**Shimamota Question 4.1.12**
<details>
  <summary>Part A Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image5.png" alt="Shimamota 4.1.12.a">
</details>
<details>
  <summary>Part B Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image15.png" alt="Shimamota 4.1.12.b">
</details>



