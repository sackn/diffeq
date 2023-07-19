## Multivaraible Chainrule

## Directional Derivatives and Graident Vectors
Now that we are in higher dimensions the word rate of change becomes a little ambigous. In 2D when someone set rate of change it was obvious what they meant. They were talking about $\frac{\Delta y}{\Delta x}$. In 3D space, the word rate of change could be the rate of change going to the "right", the rate of change going "up", or even the rate of change if you walk Northeast. Generally there is different meaning of rate of change depending on what direction you are taking the derivative in. 

Define the directional deriative as the rate of change of some function $f(x,y)$ in the direction of a unit vector $\vec{u} = \langle a,b \rangle$. The directional deriative is often denoted as $D_{\vec{u}}f(x,y)$. The limit defintion of the directional is as follows:

$$ D_{\vec{u}}f(x,y) = \lim\limits_{\Delta h \to 0} = \frac{f(x + a\Delta h, y + b\Delta h) - f(x,y)}{\Delta h}$$

IF we want a way to easily evalulate our directional derivative we introduce a new function in terms of a single variable (paramterize our original function) and we it equal to the current function $h(z) =f(x,y)$. In order to match our parameterization We  redefine our $x$ and $y$ varibles to be $x= x_0+ az$ and $y y_0 + bz$ respectively. Now we take the the deriative of parametric function we can use multivarible chain rule to expand it into the following:

$$\dot{g}(z) = \frac{\partial f}{\partial x} \frac{\partial x}{\partial z} + \frac{\partial f}{\partial y} \frac{\partial y}{\partial z}$$

We know that $\frac{\partial f}{\partial x}$ and $\frac{\partial f}{\partial y}$ are the partial deraitive of $f(x,y)$ with respect to x and y. We can also calculate $\frac{\partial x}{\partial z}$ and $\frac{\partial y}{\partial z}$. Doing all of this will yield us the formula for the directional deriative. 

$$ D_{\vec{u}}f(x,y) = f_x a + f_y b \quad \square $$


**Problems and Solution**


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



