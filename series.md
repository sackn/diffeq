## Geometric Series

A geometric series is a special type of series that takes the form:

$$\sum_{n=1} a_1{r}^{n-1}$$

Geometric series are series whos each subsequent term differs from the previous by some common ratio $r$. The common ratio can be positive or negative. A negative common ratio implies that the signs of the terms swap. Also note that $a_1$ deonates the first term in the series. Some example of geometric series are the following:
- 3,9,27,81... each differs by a factor of 3
- 4,2,1,0.5,0.25,0.125,... each differs by a factor of 0.5
- 2,-4,8,-16,32,-64,... each differs by a factor of -2

The geometric series is one of the only forms of infinate series that we can actually find the value it converges to. Most of this unit is about figuring out whether a series converge or diverge, and it basically says nothing about what values it reaches if the series does converge. The formula for finding the sum of a finite geometric series is the following:

$$S_n = \frac{a (r^n - 1)}{r-1}$$

- $a$ = the first term that you want to start your summation with (this does not necessarily need to be first term in the entire series if you want to get sum of terms 2-10 $a$ would technically be the value of $a_2$)
- $r$ = the common ratio of the geometric series
- $n$ = the number of terms that you are summing over

Since we are talking about infinate series we can see what happens to the sum of the geometric series as we let the number of terms we sum over approach infinity. 

$$\lim_{n\to\infty} \frac{a(r^n - 1)}{r-1}$$
$$\lim_{n\to\infty} \frac{ar^n}{r-1} + \frac{a}{r-1}$$

Only the first term contains the varible that we are taking the limit with respect to. Notice that the value of r that we choose can actually dictate wheter we can determine a finite value or not. If r is something like 100, if we let n approach infinity then the first term will become infinity and sum of the geometric series will also be infinity (meaning its divergent). However, if our common ratio is something like $-\frac{1}{4}$ the first term will approach zero at infinity only the second term making the sum of the geometric series equal to$\frac{a}{1-r}$. 

In turns out that the first term will only converge if zero and leading us to get a finite value for the series (not infinity) only if $-1 < r < 1$ (alternatively $|r| < 1$). If the common ratio doesn't satisfy the constraint then the geometric series blows off to ininifty and we doesn't converge to a single value.

In a more concise manner for some geometric series:
$$\sum_{n=1}^{\infty} a_1 (r)^(n-1)$$
If $|r| < 1$ then all the series will have converge to 

$$S_n = \frac{a_1}{1-r}$$
Otherwise the geometric series diverges and approaches infinity.








## Nth term test

The nth term test for divergence is the simpliest way to determine whether a series diverges. The nth term test is only able to determine whether a series is able to diverge, passing the nth term test does not make the series convergent. 

***

**The nth term test for divergence**

$$ \text{If } \sum_{0}^{\infty} a_n \text{ converge, then } \lim_{n\to\infty} a_n =0 $$

$$ \text{In other words if} \lim_{n\to\infty} a_n \neq 0 \text{, then } \sum_{0}^{\infty} a_n \text{ diverges.}$$

***

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


## The Integral Test and P-Series Test


### The Integral Test

The integral test is one of the most common methods for determining whether a series a converge or diverges and it employs improper integrals. 

***

**The Integral Test Statement**

Consider a function such that $a_n = f(x)$. If the function satisifies the following three coniditions 
- positive
- continous
- decreasing
on an interval $[m, \infty]$ where m is some positive integer then,

$$\sum_{n=1}^{\infty} a_n \text{ and } \int_{1}^{\infty} f(x) dx$$

either both converge or both diverge
***
Positive,continous, and decreasing function are all pretty self explanatory. These three conditions need to be satisfied at some point m and for any point after m for the integral test. As long there exist some positve integer m where this is the case then the integral test can be applied.

The lower limit most of the time doesn't effect the sum to be safe its probably best to set the lower limit equal to the starting index of the series.

Also, the improper integral is only able to tell whether the original series divergeces or converges. If the integral converges that DOES NOT mean that the value it converges to is the sum of the series. They have no relation what so ever. 

**Worked Example 1**

Determine whether the following series converges of diverges:

$$\sum_{n=2}^{\infty} \frac{1}{n ln(n)}$$

We can turn our discrete sequence of terms into the following continous function (basically just swapping all n's for x's):

$$f(x) = \frac{1}{xln(x)}$$

In order to use the integral test the function needs to satisfty the three conditions (positive, contionous, and decreasing). On the domain $(1, \infty]$ its pretty clear that the function will continous and positive. Also since the denominator is growing faster than the numerator the function is also decreasing for atlaest $x > 1$.

Since our function meets the three conditiosn we can check the converge of its improper integral to determine whether the orginal series also converges. 

$$\int_{n=2}^{\infty} \frac{1}{xln(x)} dx$$

Using a the u-substituion of $u=ln(x)$ our integral then becomes:

$$\int_{n=2}^{\infty} \frac{1}{u}du$$

The fundamnetal theorem of calculus doesn't like it when we have a non-finite value as the limit so we can write the upper limit in terms as a limit. 

$$\lim_{b\to\infty} \int_{n=2}^{b} \frac{1}{u} du$$

After integrating,

$$\lim_{b\to\infty} ( ln(ln(b)) - ln(ln(2))) = \infty$$

Our improper diverges, so according to the integral test the original series of also diverges.


### The P-Series Test

The P-series test an extremely fast test that can be used to determine the convergence or divergence of simple series. The p-series test will work on the series of the following form (where p is some positive number): 

$$\sum_{n=1}^{\infty} \frac{1}{n^p} = \frac{1}{1^p} + \frac{1}{2^p} + \frac{1}{3^p} + ...$$

The result of the p-series test on convergence can be directly derived use the p series test:

**Worked Example 2**

For the following seires determine whether it converges or not (again p is some positive number):

$$\sum_{n=1}^{\infty} \frac{1}{n^p}$$

We know the corresponding function:

$$f(x) = \frac{1}{x^p}$$

From inspection its pretty obvious that as long as p is a some positive number we are always continous, decreasing, and positive for any x>1. That means that we can employ the integral test to determine its convergence.

$$\int_{1}^{\infty} \frac{1}{x^p} dx$$
$$\lim_{b\to\infty} \int_{1}^{b} \frac{1}{x^p} dx$$

After integrating:

$$ \lim_{b\to\infty} (\frac{-1}{(1-p)x^{1-p}} \vert_{1}^{b})$$

$$ \lim_{b\to\infty} \frac{-1}{(1-p)b^{p-1} - \frac{-1}{(1-p)1^{p-1}} $$

For convergence we only need to worry about the first term. Note that if p is a really big number like 100 then the denominator will grow infinately and make the first term zero allowing our integral to converge. However, if the p value is really small like $\frac{1}{4}$ then the first term will diverge to infinity. The threshold for when the integral starts diverging is at one. If p is strictly greater than 1 the integral will converge else it will diverge.

Since if the convergence/divergence is the same as the series if p is strictly greater than 1 the series will also converge else it will diverge. 

***
**The P-Series Test**
For any positive integer k and p the series:

$$\sum_{n=k}^{\infty} \frac{1}{n^p}$$

will converge if $p>1$ and will diverge if $p \leq 1$
***

That means according to the p-series test the following series will converge:

$$\sum_{n=1}^{\infty} \frac{1}{n^2}$$

$$\sum_{n=1}^{\infty} \frac{1}{n^{\frac{9}{2}}}$$

and the two following series will diverge:

$$\sum_{n=1}^{\infty} \frac{1}{n^{\frac{1}{3}}}$$

$$\sum_{n=1}^{\infty} \frac{1}{n^{\frac{1}{100}}}$$

As a side point, we have a special name for the series where $p=1$. It is called the harominic series and it diverges according to the p-series test. 

$$\sum_{n=1}^{\infty} \frac{1}{n}$$

### Questions and Solutions

**Problem 1:** Determine if the following series diverge or converges:

$$\sum_{n=0}^{\infty} \frac{1}{n{\frac{5}{2}}}$$

<details>
  <summary>Solution</summary>
  Since $p = \frac{5}{2}$ the series converges by the p-series test
</details>


**Problem 2:** Determine if the following series diverge or converges:

$$\sum_{n=0}^{\infty} \frac{1}{\sqrt{n}}}$$

<details>
  <summary>Solution</summary>
  Since $p = \frac{1}{2}$ the series diverges by the p-series test
</details>

**Problem 3:** Determine if the following series diverge or converges:

$$\sum_{n=0}^{\infty} \frac{n}{n^2 + 1}$$

<details>
  <summary>Solution</summary>
  
  $$f(x) \frac{x}{x^2 + 1}$$
  
  From inspection we know that the series positive, contionous, and decreasing for all $x>1$.

  $$\int_{0}^{\infty} \frac{x}{x^2 + 1} dx$$
  
  $$\lim_{b\to\infty} \int_{0}^{b} \frac{x}{x^2 + 1} dx$$

  Using the u-substituion $u = x^2 + 1$.

  $$\frac{1}{2} \lim_{b\to\infty} ln|x^2+1| \vert_{0}^{b}$$

  $$\frac{1}{2} \lim_{b\to\infty} ln|b^2 + 1| - ln|1| = \infty$$

  The integral diveges so therefor the original series also diverges. 

  
</details>





## Taylor / Maclaurin Series

**The Maclaurin Series of e^{x}**

We can start by listing out a few of the deriviatve of $e^{x}$ and there values as the center of the taylor series (c=0)

$$f(x) = e^{x} \qquad f(x) = e^0 = 1$$

$$f'(x) = e^{x} \qquad f'(x) = 1$$

$$f''(x) = e^{x} \qquad f''(x) = 1$$

$$f'''(x) = e^{x} \qquad f'''(x) = 1$$

We know that a Macluarin series expansion takes the following form

$$\sum_{n=0}^{\infty} \frac{f^{(n)}(0)x^n}{n!}$$

As shown above $f^{(n)}(0)$ will always be one so the taylor series expansion of $e^x$ is the following;

$$e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!}$$

**The Maclaurin Series of sin(x)**

We can again start by listing out a few deriviatves of $sin(x)$ and there vaues at the center of the taylor series (c=0)

$$f(x) = sin(x) \qquad f(0) = 0$$

$$f'(x) = cos(x) \qquad f'(0) = 1$$

$$f''(x) = -sin(x) \qquad f''(0) = 0$$

$$f'''(x) = -cos(x) \qquad f'''(0) = -1$$

$$f''''(x) = sin(x) \qquad f''''(0) = 0$$

$$f'''''(x) = cos(x) \qquad f''''(0) = 1$$

Note all terms of the taylor series actually contribute so we can write a series that only hits those that do add add value. The only important terms are the even terms. In other words only terms with indicies $2n+1$ need to be considered. Between the even terms of the series they also swap signs so we will need $(-1)^n$ (since it starts positive). Considering all of those things we get that the series expansion of $sin(x)$

$$e^x = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{(2n+1)!}$$

Our series skips all of the odd terms and adjust for that fact by having the exponent on x and the exponent on n be adjusted skip every other term starting from the 2nd term. It would recommend looking into the series an proving to yourself that this does indeed describe the behavior of $f^{n}(x)$

**The Maclaurin Series of cos(x)**

The Maclaurin series for cos(x) is super similar to the expansion of sin(x) as is probably expected. If we list our some derivaitves and there values at 0 we get:

$$f(x) = cos(x) \qquad f(0) = 1$$

$$f'(x) = -sin(x) \qquad f'(0) = 0$$

$$f''(x) = -cos(x) \qquad f''(0) = -1$$

$$f'''(x) = sin(x) \qquad f'''(0) = 0$$

$$f''''(x) = cos(x) \qquad f''''(0) = 1$$

$$f'''''(x) = -sin(x) \qquad f''''(0) = 0$$

Cosine is the same story as sine except for that fact that odd terms (terms 1,3,5,7,...) are the only ones that contribute rather than even terms. The Macularin expansion for cosine is the following:

$$e^x = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n}}{(2n)!}$$

### Common Taylor Series Expansions (cenetered at zero) to remember:

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

  

