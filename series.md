## Taylor Series

### Common Taylor Series Expansions (cenetered at zero)

$$e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!}$$
$$sin(x) = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{(2n+1)!}$$
$$cos(x) = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n}}{(2n)!}$$

$$tan^{-1}(x) \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{2n+1}$$


### Questions and Solutions

**Problem 1:**  Find the taylor series for $f(x) = \frac{sin(x)}{x^3}$ centered at zero.
<details>
  <summary>Solution</summary>
  The taylor series of sine:
  $$sin(x) = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{(2n+1)!}$$
  Substituing the taylor series for sine into the original functions we get equivalent statement
  $$f(x) = x^{3}(\sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{(2n+1)!})$$
  Distributing the $x^3$ into the summation we get the Maclaurin series of f(x):
  $$\sum_{n=0}^{\infty} \frac{(-1)^n x^{2n-2}}{(2n+1)!} \quad \square$$
</details>
  
**Problem 2:** Find the Maclaurin series for $f(x) = tan^{-1}(x^2)$
<details>
  <summary>Solution</summary>
  We know the Macluarin series of $tan^{-1}(x)$ to be the following:
  $$tan^{-1}(x) \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{2n+1}$$

  If we allow $u = x^2$ our function is now,
  $$f(x) = tan^{-1}(u)$$
  Expanding our function in terms of the new varaible using the already known macluarin series for arctangent we get:
  $$\sum_{n=0}^{\infty} \frac{(-1)^n (u)^{2n+1}}{2n+1}$$

  We can now resubstitute, replacing every $u$ back with an x^2.
  $$\sum_{n=0}^{\infty} \frac{(-1)^n (x^2)^{2n+1}}{2n+1}$$
  $$\sum_{n=0}^{\infty} \frac{(-1)^n (x)^{4n+2}}{2n+1} \quad \square$$
  
  
  
  

</details>
  

  

