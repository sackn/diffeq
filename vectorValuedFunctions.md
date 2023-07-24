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

Find the parametric equation of a line between the points $(-3,2,1)$ and $(2, -1, 3)$. Define the following:
$$\vec{A} = \langle -3, 2, 1 \rangle \quad \vec{B} = \langle 2, -1, 3 \rangle$$
We can get the "slope" of the line through finding the seperation vector between the points. 
$$\vec{u} = \vec{B} - \vec{A} = \langle 5, -3, 2 \rangle$$
We have the slope now all we need is a point on the line, so that we can get our paremetric equation. Getting points on the line isn't hard since the question prompt quite literally gives us two points already on the line. Choosing arbitrarily point $(3,2,1)$ the parametric equation of our line is the following:

$$\vec{r}(t) = \vec{A} + t \vec{u}$$
$$\vec{r}(t) = \langle -3,2,1 \rangle + t \langle 5, -3 ,2 \rangle$$

We can use vector arithmetic and add the two to get a more condensed formula:
$$ \vec{r}(t) = \langle -3 + 5t, 2 - 3t, 1 + 2t \rangle \quad \square$$

Althought, I have been mainly using vector notation to describe our line it is also valid to seperate the line into each of its components. In the case of the 3D line in the example we can write it as three different equations (one for each coordinate):
$$x(t)  = -3 + 5t$$
$$y(t) = 2 - 3t $$
$$z(t) = 1 + 2t$$

**Lines in Higher Dimensions**

Our definition of a line is pretty flexible. In fact with the way we designed it the equation for an nth dimensional line is the exact same. However, instead both our "initial point" and "slope" are nth dimensional vectors rather than 3rd dimensioanl vectors. 

### Questions and Solutions

**Question 1:** Find the Parametric Equation of a LINE between points the point $(1,2,3)$ and $(4, -1, 6)$:
<details>
  <summary>Solution</summary>
  $$\vec{A} = \langle 1, 2, 3 \rangle \quad \vec{B} = \langle 4, -1, 6 \rangle$$
  $$\vec{u} = \vec{B} - \vec{A} = \langle 3,-3,3 \rangle$$
  $$\vec{r}(t) = \langle 1,2,3 \rangle + t \langle 3,-3,3 \rangle$$
  $$\vec{r}(t) = \langle 1 + 3t, 2 - 3t, 3 + 3t \rangle \quad \square$$
</details>

**Question 2:** Find the Parametric Equation of a LINE SEGMENT between points the point $(1,2,3)$ and $(4, -1, 6)$:
<details>
  <summary>Solution</summary>
  Not much else to do besides add a constraint on the values that $t$ can be. $\vec{r}(0) = \langle 1,2,3 \rangle$ and $\vec{r}(1) = \langle 4,-1,6 \rangle$.Line segments will become pretty common place once we get to line integrals. 
  $$\vec{r}(t) = \langle 1 + 3t, 2 - 3t, 3 + 3t \rangle \quad t \in [0,1] \quad \square$$
</details>

**Question 3:** Find the Parametric Equation of a line which contains the point $(1,2,-1)$ and is perpendicular $x(t)= 2 + 3t$, $y(t) = 1-t$, $z(t) = -1 + 2t$.
<details>
  <summary>Solution</summary>
  The slope of the line already given to us is the following:
  $$\vec{u} = \langle 3, -1, 2 \rangle $$
  We want to find a line perpendicular to the line given to us. You might remember that a line with slope $m$ is perpendicular to a line of slope $-\frac{1}{m}$. That basically exactly what we are going to do instead with vectors this time define the slope of our perpendicular line to be:
  $$\vec{v} = -\frac{1}{\vec{u}} = \langle -\frac{1}{3}, 1, -\frac{1}{2} \rangle$$
  We have the slope of the line and we were given a point on the line so the paremetric form of our perpendicular line is as follows:
  $$\vec{r}_{\perp}(t) = \langle 1,2,-1 \rangle + t \langle -\frac{1}{3}, 1, -\frac{1}{2} \rangle$$
  $$\vec{r}_{\perp}(t) = \langle 1-\frac{1}{3}t,2 + t,-1-\frac{1}{2}t \rangle \quad \square$$
</details>

**Question 4:** Find the point of interesction between the lines $\vec{r}_1(t) = \langle 2 + 3t, 1-t, -1 + 2t$ and $\vec{r}_1(s) = \langle -1 + 2s, 3s, 4 + 3s \rangle$ or find out that they do not interest:
<details>
  <summary>Solution</summary>
  We know that at the point of interesction that all components must match each other. That leaves us with the following system of equations:
  $$2 + 3t = -1 + 2s$$
  $$1-t = 3s$$
  $$-1 + 2t = 4 + 3s$$

  If we take the first equation and add into to three times the second equation we find that $s = \frac{6}{11}$
  $$2 + 3t = -1 + 2s$$
  $$3 -3t = 9s$$
  $$s = \frac{6}{11}$$

  Plugging our new found value back into the 2nd equation we can find the value of $t$:
  $$1-t = 3(\frac{6}{11})$$
  $$t = -\frac{7}{11}$$

  Do not think you are done just because you found the values of $t$ and $s$. We have three equation and for there to be an intersection point we need all of them to agree. That means we must plug in our values for $t$ and $s$ into the 3rd equation to confirm that we do indeed have an intersction point.
  $$-1 + 2(-\frac{7}{11}) = 4 + 3(\frac{6}{11})$$
  $$-\frac{25}{11} \neq \frac{50}{11}$$
  It turns out that at the one point where our x and y coordinates in each lines the z coordinate doesn't quite match up. That means that the two lines mentioned do not interesct at all. 
</details>

## Parametric Equation of a Plane

We want to define an equation for a plane. Most commonly a plane is defined by a point in the plane a vector orthagonal $\vec{N}$ to the plane. A plane is just a set of points and we can obviously form a vector between any two points. It key to the equation of a plane to understand that the seperation vector between two points(in the same plane) will also lie in that the same plane. The seperation vector between two points is the difference between there position vectors. For some constant position vector $\vec{r}_0$ and any the position vector of any other point $\vec{r}$ we get that there seperation vector is
simply $\vec{r} - \vec{r}_0$. Below is a visualization of what I just said , 

<img src="https://github.com/sackn/diffeq/blob/main/Images/plane.png" alt="Plane">

We know that the any seperation vector between point in the plane will also lie in the plane. That means if we define a normal vector that is orthagonal to the plane the $\vec{N} \cdot (\vec{r} - \vec{r}_0) = 0$ will always hold. If we take this equation and expand it with some genernic varibles we get,
$$\langle a,b,c \rangle \cdot \langle x-x_0, y-y_0, z-z_0\rangle$$
Applying the dot product we get the definition of a plane.
$$a(x-x_0) + b(y-y_0) + c(z-z_0) = 0 \quad \sqaure$$
Alternatively some people may write it as the following
$$ax + by + cz = ax_0 + by_0 + cz_0$$

You might be asking how we actually get the normal to the plane. We can do that with the vector cross product. If we know two vectors inside the plane then we can take the cross product between them to find a vector normal to the entire plane. In order to define a plane you need atleast two vectors which would also imply that you need atleast 3 points to define a plane. 

**Worked Example**

Find the equation to the plane that contains A $(1,2,-1)$. B $(2,-1,3)$, and C $(-2,0,1)$

We have three points and we need two different vectors to help us find the normal through a cross product calculation. Subtrating any two points we can get a vector inside the plane. Picking any unique set of pairs we can get two vectors int he plane $\vec{u}$ and $\vec{v}$ (my choices are arbitrary there are other combinations that will also work to get a normal)
$$\vec{u} = B-A = \langle 1, -3, 4\rangle$$
$$\vec{v} = C-A = \langle -3, -2, 2\rangle$$
In order to find the normal to the plane we need to find the cross product between the two vectors $\vec{u} \times \vec{v}$. Doing so, will get us the following vector,

$$\[\mathbf{v} \times \mathbf{w} = \begin{vmatrix}\mathbf{i} & \mathbf{j} & \mathbf{k} \\-1 & -3 & 4 \\-3 & -2 & 2\end{vmatrix}\]

\[
\mathbf{v} \times \mathbf{w} = \left(\mathbf{i} \cdot (-3 \cdot 2 - 4 \cdot (-2))\right) - \left(\mathbf{j} \cdot (-1 \cdot 2 - 4 \cdot (-3))\right) + \left(\mathbf{k} \cdot (-1 \cdot (-2) - (-3) \cdot (-3))\right)$$





## Tangent, Normal, and Binormal Vectors on a curve

**Tangent Vectors**

One of the uses of vector value function is how easily we can define different vectors that describe its properties. Firstly, we can define the unit tangent vector which by is parallel to the tangent line (so it can therefore be used to define it) at some point A. We define the unit tangent vector as the following,

$$\vec{T}(t) = \frac{\vec{r}'(t)}{||\vec{r}'(t)||}$$

Where $\vec{T}(t)$ refer to the unit tangent vector and $r(t)$ refering to the position vector (making $r'(t)$ the rate of change of the position vector). A tangent vector drawn on a curve might look something like the following (I do not own this image): 

<img src="https://github.com/sackn/diffeq/blob/main/Images/tangentVector.png" alt="Tangent Vectors">

**Worked Example (Tangent Vectors on a Curve)** 

Let $C$ be a curve in three-dimensional space paramertrized by $\vec{r}(t) =\langle t^{2}, 2t, 3t + 1\rangle$. Find the unit tangent vector $\vec{T}(t) at t=2$ and form the tangent line using it.

We can start the problem by differentiating our parametric equation. This will give us the rate of change of our position vector \vec{r}'(t) :
$$\vec{r}'(t) = \langle 2t, 2, 3 \rangle$$
Since we want the unit tangent vectors we will also need to find the mangitude of the rate of change of our position vector \vec{r}'(t)  (remember the definition of a unit vector $\vec{u} = \frac{\vec{v}}{||\vec{v}||}$):
$$||\vec{r}'(t)|| = \sqrt{ (2t)^{2} + (2)^2 + (3)^{2}}$ = \sqrt{4t^{2} + 13}$$
Putting of these results together we can find the general equation for our tangent vector
$$\vec{T}(t) = \frac{\vec{r}'(t)}{||\vec{r}'(t)||}$$
$$\vec{T}(t) = \frac{\langle 2t, 2, 3\rangle}{\sqrt{4t^{2} + 13}}$$
$$\vec{T}(t) = \langle \frac{2t}{\sqrt{4t^{2} + 13}}, \frac{2}{\sqrt{4t^{2} + 13}}, \frac{3}{\sqrt{4t^{2} + 13}} \rangle$$
We have our general form by plugging int $t=2$ we can find the unit tangent vector at that specific point.
$$\vec{T}(2) = \langle \frac{4}{29}, \frac{2}{29}, \frac{3}{29} \rangle$$ 
We also want to get the tangent line at $t=2$. We have a vector parallel at $\vec{T}(2)$,but we also need a point on the line. We can get a point on the line by just evaluating its the original function at $t = 2$. 
$$\vec{r}(2) = \langle 4, 4, 7\rangle$$
Now that we have a point and a line parallel to the the line we can write the full definition for our tangent line:
$$\vec{L}(t) = \langle 4,4,7 \rangle + t \langle \frac{4}{29}, \frac{2}{29}, \frac{3}{29} \rangle$$
$$\vec{L}(t) = \langle 4 + \frac{4t}{29}, 4+\frac{2t}{29}, 7 + \frac{3t}{29} \rangle \quad \square$$

**Normal Vectors**

Another important vector quantitiy that can be obtained from a parametric curve is the normal vector $\vec{N}$. The normal vector $\vec{N}$ by defintion will point exactly orthagonal to the tangent vector $\vec{T}$  (think of it as pointing outwards). That may be hard to visualize to below is an image showing what a normal vector might look like on a curve:
<img src="https://github.com/sackn/diffeq/blob/main/Images/normalVector.png" alt="Normal Vector">

We usually define our vector quantities as unit vectors. The definition for the unit normal vector $\vec{N}$ is the following:
$$\vec{N}(t) = \frac{T'(t)}{||\vec{T}'(t)||}$$
The previous definition for the unit tangent vector was pretty intuitive becuase the tangent vector was completley built from the rate of change of the position vector. However, the fact that the normal vector is comprised of the rate of change of the unit tangent vector might be a little strange. This relationship between the rate of change of the tangent vector and the normal vector can be described through the very definition of the normal vector. I don't want to copy a proof, but there is a good one on [https://tutorial.math.lamar.edu/Classes/CalcIII/TangentNormalVectors.aspx](url). It turns out that that as long as magnitude stays constant then $\vec{r}'(t) \cdot \vec{r}(t) = 0$. We know the unit tangent vector to always have a mangitude of 1 (given the definition of a unit vector) by substituing $\vec{r}(t) = \vec{T}(t)$ we can get that $\vec{T}'(t) \cdot \vec{T}(t) = 0$. The previous statement is saying that the if the tangent vector is a unit vector then, the rate of change of the tangent vector $\vec{T}'(t)$ is always orthagonal (which is the definition of the normal vector).

We can create a tangent line from our tangent vector because its will always parallel similarly we can also create a "normal line" from our normal vector since it will also always be parallel.

**Worked Example (Normal Vectors on a Curve)**

Let $C$ be a smooth curve in three-dimensional space paramertized by $\vec{r}(t) = \langle t, t^{2}, 2t \rangle$. Find the normal vector at $t=1$.

In order to get our normal vector we need to figure out our tangent vector. The process is the exact same as the previous worked example, so here is a shorthanded version of the work. First take derivative and find its magnitude.

$$\vec{r}'(t) = \langle 1, 2t, 2\rangle$$

$$||\vec{r}'(t)|| = \sqrt{ 1^2 + (2t)^2 + 2^2 } = \sqrt{4t^2 + 5}$$

Apply unit tangent vector definition
$$\vec{T}(t) =  \langle \frac{1}{\sqrt{4t^{2} + 5}}, \frac{2t}{\sqrt{4t^{2} + 5}}, \frac{2}{\sqrt{4t^{2} + 5}} \rangle$$
In order to get to our unit normal vector we must take the derivative of out tangent vector $\vec{T}(t)$. This is a pretty tedious process, but after doing so we will end up with the following,
$$\vec{T}'(t) = \langle -\frac{4t}{(4t^{2} + 5)^{\frac{3}{2}}}, \frac{10}{(4t^{2} + 5)^{\frac{3}{2}}}, -\frac{8t}{(4t^{2} + 5)^{\frac{3}{2}}} \rangle$$
In order to make it a unit normal vector we need to find the magnitude of $\vec{T}'(t)$
$$||\vec{T}'(t)|| = \sqrt{\frac{16t^2}{(4t^2 + 5)^3} + \frac{100}{(4t^2 + 5)^3} + \frac{64t^2}{(4t^2 + 5)^3}}$$
$$||\vec{T}'(t)|| = \frac{\sqrt{80t^2 + 100}}{(4t^2 + 5)^{\frac{3}{2}}}$$
Now plugging our results into the formula for the unit normal vector we get the following general form for our normal vectors,

$$\vec{N}(t) = \frac{T'(t)}{||\vec{T}'(t)||}$$

$$\vec{N}(t) = \frac{\langle -\frac{4t}{(4t^{2} + 5)^{\frac{3}{2}}}, \frac{10}{(4t^{2} + 5)^{\frac{3}{2}}}, -\frac{8t}{(4t^{2} + 5)^{\frac{3}{2}}} \rangle}{\frac{\sqrt{80t^2 + 100}}{(4t^2 + 5)^{\frac{3}{2}}}}$$

$$\vec{N}(t) = \langle -\frac{4t}{\sqrt{80t^2 + 100}}, \frac{10}{\sqrt{80t^2 + 100}}, -\frac{8t}{\sqrt{80t^2 + 100}} \rangle$$
We wanted our normal vectors at $t=1$. Evalulating our normal vector at that point will give us the final solution to the problem:
$$\vec{N}(1) = \langle -frac{4}{\sqrt{180}}, frac{10}{\sqrt{180}}, -frac{8}{\sqrt{180}} \quad \square$$

**Binormal Vectors**

The binormal vector is the final vector valued property that we are going to talk about. The binormal vector is define as the following:

$$\vec{B} = \vec{T} \times \vec{N}$$

The binormal vector is orthagonal to both the unit tangent vector and the unit normal vector. That means for some reason if we wanted to make a plane formed between the tangent and normal vector we could just use the birnomal vector to define it. 

### Problems and Solutions

**Question 1** Consider the curve defined by $\vec{r}(t) = \langle cos(t), sin(t), t\rangle$

a) Find the unit tangent vector $\vec{T}(t)$

b) Find the unit normal vector $\vec{N}(t)$

c) Find the birnomal vector $\vec{B}(t)$

d) Evalulate $\vec{T}(t)$, $\vec{N}(t)$, and $\vec{B}(t)$ at $t=\frac{\pi}{4}$

<details>
  <summary>Part ASolution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/tangentNormalBinormal/image4.png" alt="Question 1.a">
</details>
<details>
  <summary>Part B Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/tangentNormalBinormal/image9.png" alt="Question 1.b">
</details>
<details>
  <summary>Part C Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/tangentNormalBinormal/image6.png" alt="Question 1.c.1">
  <img src="https://github.com/sackn/diffeq/blob/main/Images/tangentNormalBinormal/image2.png" alt="Quetsion 1.c.2">
</details>
<details>
  <summary>Part D Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/tangentNormalBinormal/image5.png" alt="Question 1.d">
</details>


**Question 2** Consider the curve defined by $\vec{r}(t) \langle t, t^2, t^3\rangle$

a) Find the unit tangent vector $\vec{T}(t)$

b) Find the unit normal vector $\vec{N}(t)$

c) Find the birnomal vector $\vec{B}(t)$

d) Evalulate $\vec{T}(t)$, $\vec{N}(t)$, and $\vec{B}(t)$ at $t=1$

Warnining: This problem gets very messy, so you will see me use substituions to keep the amount of work minimal. 

<details>
  <summary>Part A Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/tangentNormalBinormal/image3.png" alt="Question 2.a">
</details>
<details>
  <summary>Part B Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/tangentNormalBinormal/image1.png" alt="Question 2.b">
</details>
<details>
  <summary>Part CSolution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/tangentNormalBinormal/image7.png" alt="Question 2.c">
</details>
<details>
  <summary>Part DSolution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/tangentNormalBinormal/image8.png" alt="Question 2.d">
</details>



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

**Question 4:** Find the Arc Length of $\vec{r}(t) = \langle t^{2}, t^{3}, 4{3} \rangle$ on the interval $t \in [0,1]$
<details>
  <summary>Solution</summary>
  $$\vec{r}'(t) = \langle 2t, 3t^{2}, 12t^{2} \rangle$$
  $$\int_{0}^{1} ||\vec{r}'(t)||dt = \int_{0}^{1} \sqrt{(2t)^{2} + (3t^{2})^{2} + (12t^{2})^{2}}dt$$
  $$\int_{0}^{1} t \sqrt{4 + 153t^{2}} dt$$
  U-sub with $u = 4 + 153t^{2}$ and change constants of integration
  $$\frac{1}{306} \int_{4}^{153} \sqrt{u}du$$
  $$\frac{1}{459}(153^{\frac{3}{2}} - 4^{\frac{3}{2}}) \approx 4.106$$
</details>








## Extra Problems and Solutions

Shimamota 2.1 is all about parametric equations.
Shimamota 2.2 is velocity, speed, acceleration, and arc length.
Shimamoto 2.4 is all about tangent and normal vectors of vector valued equations.

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

**Shimamoto Question 2.2.1**

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

**Shimamoto Question 2.2.2**

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

**Shimamoto Question 2.2.3**

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

**Shimamoto Question 2.2.4**

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

**Shimamoto Question 2.4.1:**

<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/2.3.4/image2.png" alt="Shimamoto 2.4.1.a">
</details>
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/2.3.4/image4.png" alt="Shimamoto 2.4.1.b">
</details>

**Shimamota Question 2.4.2:**

<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/2.3.4/image3.png" alt="Shimamoto 2.4.2.a">
</details>
<details>
  <summary>Solution</summary>
  <img src="https://github.com/sackn/diffeq/blob/main/Images/2.3.4/image1.png" alt="Shimamoto 2.4.2.b">
</details>

