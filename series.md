## Nth term test

The nth term test for divergence is the simpliest way to determine whether a series diverges. The nth term test is only able to determine whether a series is able to diverge, passing the nth term test does not make the series convergent. 

**The nth term test for divergence**

$$ \text{If } \sum_{0}^{\infty} a_n \text{ converge, then } \lim_{n\to\infty} a_n =0 $$

$$ \text{In other words if} \lim_{n\to\infty} a_n \neq 0 \text{, then } \sum_{0}^{\infty} a_n \text{ diverges.}$$

This should be pretty intuitive if the terms you add don't become zero you will keep eventaully reach some sort infinity. Infinately adding 100, -1, or 0.0001 will all end up in a series that doesn't converge to a single. The only way for a series to converge is if the amount of value you add onto the series becomes zero and thus prevents the series from changing at some point.

As mentioned previously it is key to know that a series whos terms converge to zero, does not instantly make in convergent. When the limit is zero the nth term test is considered indeterminate. We are also considering what happens to the terms as they approach inifnity so like most convergence/divergence tests the starting index of the series doesn't matter at all.

**Worked Example 1**

Determine if the following series diverges or if it is indeterminate under the nth term test:

$$\sum_{n=1}^{\infty} \frac{n^2 + 1}{2n^2 + 3}$$\

We can take the limit of the terms in the series as the amount of terms approaches infinity:

$$\lim_{n\to\infty} \frac{n^2 + 1}{2n^2 + 3}$$

The two dominating terms are $n^2$ on the top and $2n^{2}$. From elementary calculus we know that the following limit is equal to $\frac{1}{2}$

$$\lim_{n\to\infty} \frac{n^2 + 1}{2n^2 + 3} = \frac{1}{2}$$

This results means that at really point in the series we will effecitvely be adding $\frac{1}{2}$ every term. Adding $\frac{1}{2}$ infinatenamount of times most definately puts the sum at infinity and therefore it diverges.

**Worked Example 2**

Determine if the following series diverge or if it is indeterminate under the nth term test:

$$\sum_{n=3}^{\infty} \frac{n^2 + 1}{n^3 + 3}$$

We can take the limit of the terms in the series as the amount of terms approaches infinity:

$$\lim_{n\to\infty} \frac{n^2 + 1}{n^3 + 3}$$

The denominator grows faster than the numerator so the we know that the terms will approach zero eventaully:

$$\lim_{n\to\infty} \frac{n^2 + 1}{n^3 + 3} = 0$$

At some point in the series the terms basically contribute nothing to the total sum of the series. As mentioned previously this does not mean that the series diverges or converges the nth term test simply isn't the right tool (indeterminate under the nth term test).

### Questions and Solutions

**Problem 1:** Determine if the following series diverge or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{1}{n}$$
<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{1}{n} = 0$$
  Indeterminate under the nth term test. Althought it might make sense for a series whos terms converge to zero to also have its summation converge, but $\frac{1}{n}$ is a perfect example. According to the nth term test it each term will eventually equal zero however, the series actually is divergent (we will learn why this is the case later)
</details>

**Problem 2:** Determine if the following series diverge or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{(-1)^n}{n}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{(-1)^n}{n} = 0$$
  Indeterminate under the nth term test. Even though the terms of the series swap signs they will get infinately close to zero. You will learn later that this series actually converge which might be a little confusing if you also did problem 1. Is it possible for $\frac{1}{n}$ to diverge and $\frac{(-1)^n}{n}$ to converge (the answer is yes, more about this later).
</details>

**Problem 3:** Determine if the following series diverge or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{(n^3}{n^2 ln(n)}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{n^3}{n^2 ln(n)} = \infty$$

  The series diverge by the nth term test. The numerator grows much faster than the denomnator so the value each term adds will continue increase. We keep adding bigger and bigger numbers which pretty obviously makes it impossible for us to converge to a single value.
</details>

**Problem 4:** Determine if the following series diverge or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{(n^n}{n!}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{n^n}{n!} = \infty$$

  The series diverges by the nth term test. 

  This limit is a little more difficult to see, but if you expand $n^n$ and $n!$ it becomes a little more obvious.

  $$n^n = (n)(n)(n)(n)(n)(n)(n)...$$
  $$n! = (n)(n-1)(n-2)(n-3)(n-4)(n-5)(n-6)....$$

  Its pretty clear that $n^n$ will out pace $n!$
  
</details>

**Problem 5:** Determine if the following series diverge or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{n^3 - 1}{n^3 + 2n + 1}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{n^3 - 1}{n^3 + 2n + 1} = 1$$

  Diverges by nth term test.
</details>

**Problem 6:** Determine if the following series diverge or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{2^n}{n!}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{2^n}{n!} = 0$$

  Indeterminate under the nth term test. $n!$ grows faster than $2^n$. Expanding $n!$ into some of its factors is a good way for determining that a factorial will always grow faster than an exponetital.
</details>

**Problem 7:** Determine if the following series diverge or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{(-1)^n}{n}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{1}{n} = 0$$
</details>

**Problem 8:** Determine if the following series diverge or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{n^2}{2^n}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{n^2}{2^n} = 0$$

  Indeterminate under the nth term test.
</details>

**Problem 9:** Determine if the following series diverge or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{1}{tan^{-1}(n)}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{1}{tan^{-1}(n)} = \frac{2}{\pi}$$

  Diverges by the nth term test. Note that $tan^{-1}(x)$ approaches $\frac{pi}{2}$ at infinity.
</details>

**Problem 10:** Determine if the following series diverge or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} sin(n)$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} sin(n) = \text{does not exist}$$

  Diverges by the nth term test. $sin(x)$ itself doesn't have a limit and therefore it converge to a single value. It will continue oscillating between values. It doesn't blow off to infinity but it most definately does not approach a singleular number either. 
</details>


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

  

