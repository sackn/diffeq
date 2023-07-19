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

**Question 1:**
<details>
  <summary>Part A Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image13.png" alt="Shimamota 4.1.1.a">
</details>

**Question 2:**
<details>
  <summary>Part A Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image13.png" alt="Shimamota 4.1.1.a">
</details>

**Question 3:** Given the function $f(x,y) = sin(x) + cos(y)$ find the tangent plane at the point $(\frac{\pi}{4}, \frac{\pi}{3})$
<details>
  <summary>Solution</summary>
  Finding the Partial derivatives and evaluating the function at $(\frac{\pi}{4}, \frac{\pi}{3})$
  $$\frac{\partial f}{\partial x} = cos(x) \quad \frac{\partial f}{\partial y} = -sin(y)$$
  $$f_x(\frac{\pi}{4}, \frac{\pi}{3}) = \frac{sqrt{2}}{2} \quad f_y(\frac{\pi}{4}, \frac{\pi}{3}) = -\frac{sqrt{3}}{2}$$
  $$f(\frac{\pi}{4}, \frac{\pi}{3}) = \frac{sqrt{2} + 1}{2} $$
  Finding our plane equation
  $$T(x,y) = \frac{sqrt{2}}{2}(x-x_0)  + -\frac{sqrt{3}}{2}(y-y_0) + \frac{sqrt{2} + 1}{2} $$
  
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

**Question 5:**
<details>
  <summary>Part A Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/4.13.1/image13.png" alt="Shimamota 4.1.1.a">
</details>

### Practice Questions
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



