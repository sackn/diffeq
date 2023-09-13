## Vectors as Deriviatves

Most of us have dealth with parametric functions. We can take the derivaitve of the parametric curve and get a vector field representig tangent vectors at each point. Parametric curves usally involv some "universal variable" $t$ and the the function $\vec{R}(t)$ will output the curve (effectively a function that yields a position vector). As we enumerate all $t$ we will trace entire the curve. 

If want to the tangent vectors over the curve we have to find the deriviatve $\frac{d \vec{R}}{dt}$. If we write the derivaitive using its limit definition

$$\frac{d\vec{R}}{dt} = \lim_{h\to0} \frac{\vec{R}(t+h)-\vec{R}(t)}{h}$$

The limit will give us the tangent vectors along the curve. If we expand $\frac{d\vec{R}}{dt}$ with the fact that $x=u(t)$ and $y=v(t)$ we get the following

$$\frac{d\vec{R}}{dt} = \frac{d\vec{R}}{dx} \frac{dx}{dt} + \frac{d\vec{R}}{dy} \frac{dy}{dt}$$

Note that things like $\frac{dx}{dt}$ are scalar while $\frac{d\vec{R}}{dt}$ are vector values. What effectively we have the deriative $\frac{d\vec{R}}{dt}$ written as two component scalar values ($\frac{dx}{dt}$ and $\frac{dy}{dt}) each paired with there own "basis vector" ($\frac{d\vec{R}}{dx}$ and $\frac{d\vec{R}}{dy}$)
