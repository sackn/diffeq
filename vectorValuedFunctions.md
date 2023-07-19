## Parametric Definition of a Line
We have known for a very long time that the equation to a line is simply $y = mx + b$. That equation worked all fine in 2D, but now that we are stepping into 3D it gets a little more annoying. It is possible to draw a line in 3D that uses x's and y's as inputs. However, its more easier and more useful to have the life in the form $f(t)$ a parametric equation. Firstly lets consider point slope form (from middle school math),
$$(y-y_0) = m(x-x_0)$$
In order to find the equation for a line at the very minimum we must have the slope of the line and some point on said line $(x_0, y_0)$. We are going to try find something similar for 3D parametric lines. When it comes to some point on the line thats easy we can just write it as its position vector call it $$\vec{r}_0(t) = \langle x_0, y_0, z_0 \rangle$$.

Now we need a way to define the slope of the line. That's not that bad either. Since we are dealing with a line the slope will never change by definition. That means we need to find a vector that can "represent" the slope of the line. In turns out that multiple vectors will actually work to do this. As long as the vector is parallel to the line then, it can describe its slope. Hopefully this is pretty intuitive. 

For example if you a line that goes 1 up on x, 2 down on y, and 3 up on z then any of the following vectors could be used to define said line:
- $\vec{r}_1(t) = \langle 1, -2, 3 \rangle$
- $\vec{r}_2(t) = \langle \frac{1}{2}, -1, \frac{3}{2} \rangle $
- $\vec{r}_3(t) = \langle -\frac{1}{2}, 1, -\frac{3}{2} \rangle $

If you visualize the line you might be able to see that all the vectors are different, but all of them technically still lie completely on the line. What vector we exactly use won't play a difference in the line as a whole however it will effect how $f(t)$ changes in response to time. Firstly, this would make more sense if I gave you the definition of a parametric line which is the following (where $\vec{r}_0$ is some point on the line and \vec{u} is a vector parallel to the line):

$$\vec{r}(t) = \vec{r}_0 + t\vec{u}$$

If you want we could also expand the vectors into their components and then add them so that we have singular vector equation describing the entire line.
$$\vec{r}(t) = \langle x_0, y_0, z_0 \rangle + t<U_x, U_y, U_z>$$
$$\vec{r}(t) = \langle x_0 + t u_x, y_0 + tu_y, z_0 + u_z \rangle$$

The equation $\vec{r}(t) = \vec{r}_0 + t\vec{u}$ mimics point slope form. You have an initial point and a slope. You move back and forth on the line using t. Now comes to the point where I talked about the effects of the parallel vector you chose. Assume you have some parallel vector $\vec{v}$ which move forward the line "forward" as you increase $t$ and "backwards" as you decrease $t$. If you instead paramterize it with $-\vec{v}$ (which is allowed since it is still parallel) you will instead move "backwards" as you increase $t$ and forward and you decrease $t$. If you use $3\vec{v}$ you will move "forward" on the line as you increase $t$ and "backwards" as you decrease $t$ however you do that at a rate three times faster than $\vec{v}$.  

In the end what parallel vector you choose changes how the $f(t)$ is graphed with respect to $t$. However, if you want your line to go on for ever (which by defintion a line has to go on for ever) then it really doesn't matter. You plot $f(t)$ for $t \in (-\infty, \infty)$. Every single point is plotted it doesn't matter what order or how "fast" you do it. 

**Worked Example**



## Arc Length with Vector Functions
Recall for a function $y=f(t)$ on an interval $x \in [a,b]$ it will have an arc length equal to the following:
$$L = \int_{a}^{b} \sqrt{1 + \frac{df}{dt}}(dt)$$
For a parametric vector function $\vec{r} = \langle f(t), g(t) \rangle$ the equation for the arc length is a logical extension of the single variabe $f(x)$ scenario on the interval $t \in [a,b]$ .
$$L = \int_{a}^{b} \sqrt{(f'(t))^2 +  (g'(t)) ^2}(dt)$$
Similarly for a vector function with three componenets $\vec{r} = \langle f(t), g(t), h(t) \rangle$:
$$L = \int_{a}^{b} \sqrt{(f'(t))^2 +  (g'(t)) ^2 + (h'(t))^2}(dt)$$

If you look closely you might recognize a simplier way to write the integral. As previousyl defined the the magnitude of the derivative of a vector function $||\vec{r}'(t)||$ is also equal to $\sqrt{(f'(t))^2 +  (g'(t)) ^2}$ in the 2D case and $\sqrt{(f'(t))^2 +  (g'(t)) ^2 + (h'(t))^2}$ in the 3D case. We can simply replace the inside of our integral with that

$$L = \int_{a}^{b} ||\vec{r}'(t)||(dt)$$

This should make some intuitive sense since we are effecitvely summing all the lengths of all tangent vectors. Much like how we made really small lines in the y=f(x) scenario. 

<img src="https://github.com/sackn/diffeq/blob/main/Images/arcLength.jpg" alt="Arc Length Image">

Image Source: [https://www.dummies.com/article/academics-the-arts/math/calculus/how-to-calculate-arc-length-with-integration-192152/](url)

The dx and dy are analagous to the x&y components of our tangent vectors.

**Question 1:** Find the Arc Length of $\vec{r}(t) = \langle 3cos(t), 3sin(t) \rangle$ on the interval $t \in [0, \pi]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/ArcLength/image2.png" alt="Question 1">
</details>

**Question 2:** Find the Arc Length of $\vec{r}(t) = \langle sin(t), cos(t), t \rangle$ on the interval $t \in [0, \frac{\pi}{2}]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/ArcLength/image2.png" alt="Question 2">
</details>

**Question 3:** Find the Arc Length of $\vec{r}(t) = \langle t, t^{2} \rangle$ on the interval $t \in [0, 1]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/ArcLength/image3.png" alt="Question 3">
</details>








### Problems and Solutions

Shimamota 2.1 is all about parametric equations.

**Shimamota Question 2.1.2:** Graph and indicate the direction of $\alpha(t) = \langle tcos(t), sin(t) \rangle$ on the interval $t \in [0, 6\pi]$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/Parametric/image5.png" alt="2.1.2">
</details>

**Shimamota Question 2.1.4:** Graph and indicate the direction of $\alpha(t) = \langle cos(t), sin(t), t \rangle$ 
<details>
  <summary>Solution</summary>
  Helix Graph
  <img src="https://github.com/sackn/diffeq/blob/main/Images/Parametric/Image6.png" alt="2.1.4">
</details>

**Shimamota Question 2.1.6:** Graph and indicate the direction of $\alpha(t) = \langle sin(t), cos(t), t \rangle$ 
<details>
  <summary>Solution</summary>
  Helix graph traced in a different direction
  <img src="https://github.com/sackn/diffeq/blob/main/Images/Parametric/Image7.png" alt="2.1.6">
</details>

**Shimamota Question 2.1.8:** Graph and indicate the direction $\alpha(t) = \langle cos(t), sin(t), cos(2t) \rangle$ on the interval $t \in [0, 2\pi]$
<details>
  <summary>Solution</summary>
  Potato Chip Graph
  <img src="https://github.com/sackn/diffeq/blob/main/Images/Parametric/Image8.png" alt="2.1.8">
</details>

**Shimamota Question 2.1.10:** Find a parametric equation for $xy = 1$ with $1 \leq x \geq 2$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/Parametric/image4.png" alt="2.1.10">
</details>

**Shimamota Question 2.1.12:** Find equation for a right handed helix that has a radius of two and completes one full twist between $z=0$ and $z=1$.
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/Parametric/image2.png" alt="2.1.12">
</details>


**Shimamota Question 2.1.14:** Find a point and a vector which parrallel to the line $\alpha(t) = \langle 1+2t, -3t, 4+5t \rangle$
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/Parametric/image1.png" alt="2.1.14">
</details>

**Shimamota Question 2.1.16:** Find equation of line that goes between $a=(1,-2,3)$ and $b = (-4,5,-6)$.
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/Parametric/image3.png" alt="2.1.14">
</details>



#### Problems and Solutions**

Shimamota 2.2 is velocity, speed, acceleration, and arc length.

**Shimamota Question 2.2.1**

$\vec{r}(t) = \langle 3t^{2}, 6t, 6 \rangle$

Part A: Find velocity vector, speed, and acceleration vector

Part B: Arc Length on the interval $t \in [0,4]$

<details>
  <summary>Part A Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/VectorValue/image5.png" alt="2.2.1.a">
</details>
<details>
  <summary>Part B Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/VectorValue/image3.png" alt="2.2.1.b">
</details>

**Shimamota Question 2.2.2**

$\vec{r}(t) = \langle \frac{1}{2}t^{2}, 2t, \frac{4}{3}t^{\frac{3}{2}} \rangle$

Part A: Find velocity vector, speed, and acceleration vector

Part B: Arc Length on the interval $t \in [2,4]$

<details>
  <summary>Part A Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/VectorValue/image7.png" alt="2.2.2.a">
</details>
<details>
  <summary>Part B Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/VectorValue/image4.png" alt="2.2.2.b">
</details>

**Shimamota Question 2.2.3**

$\vec{r}(t) = \langle cos(2t), sin(2t), 4t^{3/2} \rangle $

Part A: Find velocity vector, speed, and acceleration vector

Part B: Arc Length on the interval $t \in [1,2]$

<details>
  <summary>Part A Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/VectorValue/image8.png" alt="2.2.2.a">
</details>
<details>
  <summary>Part B Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/VectorValue/image2.png" alt="2.2.2.b">
</details>

**Shimamota Question 2.2.4**

For some arbitrary constants $a,b$. Assume $a>0$.

$\vec{r}(t) = \langle acos(t), asin(t), bt \rangle$

Part A: Find velocity vector, speed, and acceleration vector

Part B: Arc Length on the interval $t \in [0, 2\pi]$

<details>
  <summary>Part A Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/VectorValue/image6.png" alt="2.2.2.a">
</details>
<details>
  <summary>Part B Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/VectorValue/image1.png" alt="2.2.2.b">
</details>
