## Nth term test

The nth term test for divergence is the simpliest way to determine whether a series diverges. The nth term test is only able to determine whether a series is able to diverge, passing the nth term test does not make the series convergent. 

**The nth term test**

$$ \text{If } \sum_{0}^{\infty} a_n \text{ converge, then } \lim_{n\to\infty} a_n =0 $$

$$ \text{In other words if} $\lim_{n\to\infty} a_n \neq 0$ \text{, then } $\sum_{0}^{\infty} a_n$ \text{ diverges.}$$




## Taylor Series

### Common Taylor Series Expansions (cenetered at zero)

$$e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!}$$

$$sin(x) = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{(2n+1)!}$$

$$cos(x) = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n}}{(2n)!}$$

$$tan^{-1}(x) = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{2n+1}$$


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
  
  $$tan^{-1}(x) = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{2n+1}$$

  If we allow $u = x^2$ our function is now,
  
  $$f(x) = tan^{-1}(u)$$
  Expanding our function in terms of the new varaible using the already known macluarin series for arctangent we get:
  
  $$\sum_{n=0}^{\infty} \frac{(-1)^n (u)^{2n+1}}{2n+1}$$

  We can now resubstitute, replacing every $u$ back with an x^2.
  
  $$\sum_{n=0}^{\infty} \frac{(-1)^n (x^2)^{2n+1}}{2n+1}$$
  
  $$\sum_{n=0}^{\infty} \frac{(-1)^n (x)^{4n+2}}{2n+1} \quad \square$$

</details>
  
  
**Problem 3:** Find the Maclaurin series for $f(x) = ln(1+x^2) $
<details>
  <summary>Solution</summary>
  First we can start by finding the eaiser taylor series of $g(x) = ln(1+x)$. Finding some of the first terms we get:
  $$g(x) = ln(x+1) \qquad g(0) = 0$$
  
  $$g'(x) = \frac{1}{x+1} \qquad g'(0) = 1$$
  
  $$g''(x) \frac{-1}{(x+1)^2} \qquad g''(0) = -1$$
  
  $$g'''(x) = \frac{2}{(x+1)^3} \qquad g'''(0) = 2$$
  
  $$g''''(x) = \frac{-6}{(x+1)^4} \qquad g''''(0) = -6$$
  
  We can guess that the series follows the pattern (note that our series starts at 1 rather than 0 in order to dodge the 0 term at the start of the expansion):
  
  $$\sum_{n=1}^{\infty} \frac{(-1)^{n+1}x^n(n-1!)}{n!} = \sum_{n=1}^{\infty} \frac{(-1)^{n+1}x^n}{n} $$ 

  Returning the the original function we can temporarily make $u = x^2$ making our function:
  $$f(u) = ln(1+u)$$
  
  Expanding using the maclaurin series we just derived we get:
  
  $$\sum_{n=1}^{\infty} \frac{(-1)^{n+1}(u)^n}{n} $$ 
  
  Re-substituing the $x^2$ for the $u$ we get the following answer:
  
  $$\sum_{n=1}^{\infty} \frac{(-1)^{n+1}(x)^{2n}}{n} \quad \square$$ 
</details>


**Problem 4:** Find the taylor series of $f(x) = e^{2x}$ centered at $a=2$.
<details>
  <summary>Solution</summary>
  First we can start by finding a few of the the deriviatves at the point $x=2$:
  $$f(x) = e^{2x} \qquad f(2) = e^4$$
  
  $$f'(x) = 2e^{2x} \qquad f'(2) = 2e^4$$
  
  $$f''(x) = 4e^{2x} \qquad f''(2) = 4e^4$$
  
  $$f'''(x) = 8e^{2x} \qquad f'''(2) = 8e^4$$
  
  $$f''''(x) = 16e^{2x} \qquad f''''(2) = 16e^4$$
  
  Our taylor series coeffients have a constant factor of $e^{4}$ and are increasing with respect to $2^n$. We can make a pretty good guess that our taylor series expanion is the following:
  $$\sum_{n=0}^{\infty} \frac{e^4 2^n (x-2)^n}{n!} \quad \square$$
  Note that our taylor series is centetered at a=2 which means our varible term is $(x-2)^n$ rather than just $x^n$
</details>


**Problem 5:** Find hte taylor series of $f(x) = sin(2x)$ centered at $a = \pi$
<details>
  <summary>Solution</summary>
  First we can start by finding a few of the the deriviatves at the point $x=\pi$:
  $$f(x)= sin(2x) \qquad f(\pi) = 0$$
  
  $$f'(x) = 2cos(2x) \qquad f'(\pi) = 2$$
  
  $$f''(x) = -4sin(2x) \qquad f''(\pi) = 0$$
  
  $$f'''(x) = -8cos(2x) \qquad f'''(\pi) = -8$$
  
  $$f''''(x) = 16sin(2x) \qquad f''''(\pi) = 0$$
  
  $$f'''''(x) = 32cos(2x) \qquad f'''''(\pi) = 32$$

  We know that the Maclaurin series of $sin(x)$ is the following:
  
  $$sin(x) = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{(2n+1)!}$$

  Our terms match the typical sin(x) expansions outside of the fact we have this new factor of $2^n$ on each term and that our series is centered at $\pi$ rather than zero. We can therefore make a pretty get guess that our taylor series expansion about $\pi$ is the following:
  $$sin(x) = \sum_{n=0}^{\infty} \frac{(-1)^n 2^n (x-\pi)^{2n+1}}{(2n+1)!} \quad \square$$

  
  
</details>

  

