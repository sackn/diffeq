

## Arc Length with Vector Functions
Recall for a function $y=f(t)$ on an interval $x \in [a,b]$ it will have an arc length equal to the following:
$$L = \int_{a}^{b} \sqrt{1 + \frac{df}{dt}}(dt)$$
For a parametric vector function $\vec{r} = \langle f(t), g(t) \rangle$ the equation for the arc length is a logical extension of the single variabe $f(x)$ scenario on the interval $t \in [a,b]$ .
$$L = \int_{a}^{b} \sqrt{(f'(t))^2 +  (g'(t)) ^2}(dt)$$
Similarly for a vector function with three componenets $\vec{r} = \langle f(t), g(t), h(t) \rangle$:
$$L = \int_{a}^{b} \sqrt{(f'(t))^2 +  (g'(t)) ^2 + (h'(t))^2}(dt)$$

If you look closely you might recognize a simplier way to write the integral. As previousyl defined the the magnitude of the derivative of a vector function $$||\vec{r}'(t)||$$ is also equal to $\sqrt{(f'(t))^2 +  (g'(t)) ^2}$ in the 2D case and $\sqrt{(f'(t))^2 +  (g'(t)) ^2 + (h'(t))^2}$ in the 3D case. We can simply replace the inside of our integral with that

$$L = \int_{a}^{b} ||\vec{r}'(t)||(dt)$$

This should make some intuitive sense since we are effecitvely summing all the lengths of all tangent vectors. Much like how we made really small lines in the y=f(x) scenario. 

Image Source: [https://www.dummies.com/article/academics-the-arts/math/calculus/how-to-calculate-arc-length-with-integration-192152/](url)

The dx and dy are analagous to the x&y components of our tangent vectors.

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
