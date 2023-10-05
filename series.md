---
# Introduction to Series

This section focuses on the analysis of series. Most of the section is devoted to digging deep into infinate series and determining their behavior as the number of infinate series grows towards infinity (convergence and divergence). Later in the section, I introduce some applications of infinate series, such as the Taylor/Maclaurin series, and polynomial approximations of a function at a specific point. All of the information about series is part of the AP Calculus BC exam; however, this section does not cover everything yet (work in progress).

**Current Sections**
- Geometric Series
- Nth Term Test for Divergence
- The Integral Test and the P-Series Test
- Alternating Series Test and Alternating Series Error Bound
- Maclaurin/Taylor Series

The main things that have not been written yet are power series and numerous other convergence/divergence tests (comparison, root, and ratio tests).

---

# Geometric Series

A geometric series is a special type of series that takes the form:

$$\sum_{n=1} a_1{r}^{n-1}$$

Geometric series are series in which each subsequent term differs from the previous by some common ratio (r). The common ratio can be positive or negative. A negative common ratio implies that the signs of the terms swap. Also note that $a_1$ denotes the first term in the series. Some examples of geometric series are the following:
- 3,9,27,81... each term differs by a factor of 3
- 4,2,1,0.5,0.25,0.125,... each term differs by a factor of 0.5
- 2,-4,8,-16,32,-64,... each term differs by a factor of -2

The geometric series is one of the only forms of infinite series for which we can actually find the value it converges to. Most of this unit is about figuring out whether a series converges or diverges, and it basically says nothing about what values it reaches if the series does converge. The formula for finding the sum of a finite geometric series is the following:

$$S_n = \frac{a (r^n - 1)}{r-1}$$

- $a$ = the first term that you want to start your summation with (this does not necessarily need to be first term in the entire series. If you want to get sum of terms 2-10 $a$ would technically be the value of $a_2$)
- $r$ = the common ratio of the geometric series
- $n$ = the number of terms that you are summing over

Since we are talking about infinite series, we can see what happens to the sum of the geometric series as we let the number of terms we sum over approach infinity.

$$\lim_{n\to\infty} \frac{a(r^n - 1)}{r-1}$$
$$\lim_{n\to\infty} \frac{ar^n}{r-1} + \frac{a}{r-1}$$

Only the first term contains the variable that we are taking the limit with respect to. Notice that the value of r that we choose can actually dictate whether we can determine a finite value or not. If r is something like 100, if we let n approach infinity, then the first term will become infinity, and the sum of the geometric series will also be infinity (meaning it is divergent). However, if our common ratio is something like $-\frac{1}{4}$, the first term will approach zero at infinity, and only the second term will make the sum of the geometric series equal to $\frac{a}{1-r}$.

It turns out that the first term will only converge if it is zero, leading us to get a finite value for the series (not infinity) only if $-1 < r < 1$ (alternatively, $|r| < 1$). If the common ratio doesn't satisfy the constraint, then the geometric series blows off to infinity, and we don't converge to a single value.

In a more concise manner for some geometric series:
$$\sum_{n=1}^{\infty} a_1 (r)^{(n-1)}$$
If $|r| < 1$ then all the series will have converge to 

$$S_n = \frac{a_1}{1-r}$$
Otherwise, the geometric series diverges and approaches infinity.

---
# Nth term test

The Nth-term test for divergence is the simplest way to determine whether a series diverges. The nth term test is only able to determine whether a series is able to diverge; passing the nth term test does not make the series convergent.

##

**The nth term test for divergence**

$$ \text{If } \sum_{0}^{\infty} a_n \text{ converge, then } \lim_{n\to\infty} a_n =0 $$

$$ \text{In other words if} \lim_{n\to\infty} a_n \neq 0 \text{, then } \sum_{0}^{\infty} a_n \text{ diverges.}$$

##

This should be pretty intuitive; if the terms you add don't become zero, you will eventually reach some sort of infinity. Infinitely adding 100, -1, or 0.0001 will all end up in a series that doesn't converge to a single. The only way for a series to converge is if the amount of value you add to the series becomes zero, which prevents the series from changing at some point.

As mentioned previously, it is key to know that a series whose terms converge to zero does not instantly become convergent. When the limit is zero, the nth-term test is considered indeterminate. We are also considering what happens to the terms as they approach infinity, so like most convergence and divergence tests, the starting index of the series doesn't matter at all.

##

**Worked Example 1**

Determine if the following series diverges or if it is indeterminate under the nth term test:

$$\sum_{n=1}^{\infty} \frac{n^2 + 1}{2n^2 + 3}$$

We can take the limit of the terms in the series as the number of terms approaches infinity:

$$\lim_{n\to\infty} \frac{n^2 + 1}{2n^2 + 3}$$

The two dominating terms are $n^2$ on top and $2n^{2}$. From elementary calculus, we know that the following limit is equal to $\frac{1}{2}$.

$$\lim_{n\to\infty} \frac{n^2 + 1}{2n^2 + 3} = \frac{1}{2}$$

This result means that at this point in the series, we will effectively be adding $\frac{1}{2}$ every term. Adding $\frac{1}{2}$ infinately many times most definitely puts the sum at infinity, and therefore it diverges.

##

**Worked Example 2**

Determine if the following series diverges or if it is indeterminate under the nth term test:

$$\sum_{n=3}^{\infty} \frac{n^2 + 1}{n^3 + 3}$$

We can take the limit of the terms in the series as the number of terms approaches infinity:

$$\lim_{n\to\infty} \frac{n^2 + 1}{n^3 + 3}$$

The denominator grows faster than the numerator, so we know that the terms will approach zero eventually.

$$\lim_{n\to\infty} \frac{n^2 + 1}{n^3 + 3} = 0$$

At some point in the series, the terms basically contribute nothing to the total sum of the series. As mentioned previously, this does not mean that the series diverges or converges; the nth term test simply isn't the right tool (indeterminate under the nth term test).

##

### Questions and Solutions

**Problem 1:** Determine if the following series diverges or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{1}{n}$$
<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{1}{n} = 0$$
  Indeterminate under the nth term test. Although it might make sense for a series whose terms converge to zero to also have its summation converge, $\frac{1}{n}$ is a perfect example. According to the nth term test, each term will eventually equal zero; however, the series is actually divergent (we will learn why this is the case later).
</details>

**Problem 2:** Determine if the following series diverges or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{(-1)^n}{n}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{(-1)^n}{n} = 0$$
  Indeterminate under the nth term test. Even though the terms of the series swap signs, they will definitely get close to zero. You will learn later that this series actually converges, which might be a little confusing if you also did problem 1. Is it possible for $\frac{1}{n}$ to diverge and $\frac{(-1)^n}{n}$ to converge (the answer is yes; more about this later).
</details>

**Problem 3:** Determine if the following series diverges or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{n^3}{n^2 ln(n)}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{n^3}{n^2 ln(n)} = \infty$$

  The series diverges by the nth term test. The numerator grows much faster than the denominator, so the value each term adds will continue to increase. We keep adding bigger and bigger numbers, which pretty obviously makes it impossible for us to converge on a single value.
</details>

**Problem 4:** Determine if the following series diverges or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{n^n}{n!}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{n^n}{n!} = \infty$$

  The series diverges by the nth term test. 

  This limit is a little more difficult to see, but if you expand $n^n$ and $n!$, it becomes a little more obvious.

  $$n^n = (n)(n)(n)(n)(n)(n)(n)...$$
  $$n! = (n)(n-1)(n-2)(n-3)(n-4)(n-5)(n-6)....$$

  Its pretty clear that $n^n$ will out pace $n!$
  
</details>

**Problem 5:** Determine if the following series diverges or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{n^3 - 1}{n^3 + 2n + 1}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{n^3 - 1}{n^3 + 2n + 1} = 1$$

  Diverges by nth term test.
</details>

**Problem 6:** Determine if the following series diverges or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{2^n}{n!}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{2^n}{n!} = 0$$

  Indeterminate under the nth term test. $n!$ grows faster than $2^n$. Expanding $n!$ into some of its factors is a good way for determining that a factorial will always grow faster than an exponetital.
</details>

**Problem 7:** Determine if the following series diverges or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{(-1)^n}{n}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{1}{n} = 0$$
</details>

**Problem 8:** Determine if the following series diverges or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{n^2}{2^n}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{n^2}{2^n} = 0$$

  Indeterminate under the nth term test.
</details>

**Problem 9:** Determine if the following series diverges or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} \frac{1}{tan^{-1}(n)}$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} \frac{1}{tan^{-1}(n)} = \frac{2}{\pi}$$

  Diverges by the nth term test. Note that $tan^{-1}(x)$ approaches $\frac{\pi}{2}$ at infinity.
</details>

**Problem 10:** Determine if the following series diverges or if it is indeterminate under the nth term test:

$$\sum_{n=0}^{\infty} sin(n)$$

<details>
  <summary>Solution</summary>
  $$\lim_{n\to\infty} sin(n) = \text{does not exist}$$

  Diverges by the nth term test. $sin(x)$ itself doesn't have a limit and therefore it converge to a single value. It will continue oscillating between values. It doesn't blow off to infinity but it most definately does not approach a singleular number either. 
</details>

##

---
# The Integral Test and P-Series Test

### The Integral Test

The integral test is one of the most common methods for determining whether a series converges or diverges, and it employs improper integrals.

##

**The Integral Test Statement**

Consider a function such that $a_n = f(x)$. If the function satisifies the following three coniditions 
- positive
- continous
- decreasing
on an interval $[m, \infty]$ where m is some positive integer then,

$$\sum_{n=1}^{\infty} a_n \text{ and } \int_{1}^{\infty} f(x) dx$$

either both converge or both diverge
##

Positive, constant, and decreasing functions are all pretty self-explanatory. These three conditions need to be satisfied at some point m and at any point after m for the integral test. As long as there is some positive integer m where this is the case, then the integral test can be applied.

The lower limit Most of the time, this doesn't affect the sum. To be safe, it's probably best to set the lower limit equal to the starting index of the series.

Also, the improper integral is only able to tell whether the original series diverges or converges. If the integral converges, that does not mean that the value it converges to is the sum of the series. They have no relation, what so ever.

##

**Worked Example 1**

Determine whether the following series converges or diverges:

$$\sum_{n=2}^{\infty} \frac{1}{n ln(n)}$$

We can turn our discrete sequence of terms into the following continuous function (basically just swapping all n's for x's):

$$f(x) = \frac{1}{xln(x)}$$

In order to use the integral test, the function needs to satisfy the three conditions (positive, continuous, and decreasing). On the domain $(1, \infty]$ it's pretty clear that the function will be continuous and positive. Also, since the denominator is growing faster than the numerator, the function is also decreasing for at $x > 1$.

Since our function meets the three conditions, we can check the convergence of its improper integral to determine whether the original series also converges.

$$\int_{n=2}^{\infty} \frac{1}{xln(x)} dx$$

Using the u substitution of $u=ln(x), our integral then becomes:

$$\int_{n=2}^{\infty} \frac{1}{u}du$$

The fundamental theorem of calculus doesn't like it when we have a non-finite value as the limit, so we can write the upper limit in terms of a limit.

$$\lim_{b\to\infty} \int_{n=2}^{b} \frac{1}{u} du$$

After integrating,

$$\lim_{b\to\infty} ( ln(ln(b)) - ln(ln(2))) = \infty$$

Our improper integral diverges, so according to the integral test, the original series also diverges.

##

### The P-Series Test

The P-series test is an extremely fast test that can be used to determine the convergence or divergence of simple series. The p-series test will work on the series of the following form (where p is some positive number):

$$\sum_{n=1}^{\infty} \frac{1}{n^p} = \frac{1}{1^p} + \frac{1}{2^p} + \frac{1}{3^p} + \quad ...$$

The result of the p-series test on convergence can be directly derived using the p-series test:

##

**Worked Example 2**

For the following seizures, determine whether they converge or not (again, p is some positive number):

$$\sum_{n=1}^{\infty} \frac{1}{n^p}$$

We know the corresponding function:

$$f(x) = \frac{1}{x^p}$$

From inspection, it's pretty obvious that as long as p is some positive number, we are always continuous, decreasing, and positive for any x > 1. That means that we can employ the integral test to determine its convergence.

$$\int_{1}^{\infty} \frac{1}{x^p} dx$$
$$\lim_{b\to\infty} \int_{1}^{b} \frac{1}{x^p} dx$$

After integrating:

$$ \lim_{b\to\infty} (\frac{-1}{(1-p)x^{1-p}} \vert_{1}^{b})$$

$$ \lim_{b\to\infty} \frac{-1}{(1-p)b^{p-1}} - \frac{-1}{(1-p)1^{p-1}} $$

For convergence, we only need to worry about the first term. Note that if p is a really big number like 100, then the denominator will grow indefinitely and make the first term zero, allowing our integral to converge. However, if the p value is really small, like $\frac{1}{4}$, then the first term will diverge to infinity. The threshold for when the integral starts diverging is one. If p is strictly greater than 1, the integral will converge; otherwise, it will diverge.

##

Since if the convergence or divergence is the same as the series, if p is strictly greater than 1, the series will also converge; otherwise, it will diverge.

##

**The P-Series Test**
For any positive integer k and p the series:

$$\sum_{n=k}^{\infty} \frac{1}{n^p}$$

will converge if $p>1$ and will diverge if $p \leq 1$


##

That means, according to the p-series test, the following series will converge:

$$\sum_{n=1}^{\infty} \frac{1}{n^2}$$

$$\sum_{n=1}^{\infty} \frac{1}{n^{\frac{9}{2}}}$$

and the two following series will diverge:

$$\sum_{n=1}^{\infty} \frac{1}{n^{\frac{1}{3}}}$$

$$\sum_{n=1}^{\infty} \frac{1}{n^{\frac{1}{100}}}$$

As a side note, we have a special name for the series where p = 1.It is called the harominic series, and it diverges according to the p-series test.

$$\sum_{n=1}^{\infty} \frac{1}{n}$$

## 

### Questions and Solutions

**Problem 1:** Determine if the following series diverge or converges:

$$\sum_{n=0}^{\infty} \frac{1}{n^{\frac{5}{2}}}$$

<details>
  <summary>Solution</summary>
  Since $p = \frac{5}{2}$ the series converges by the p-series test
</details>


**Problem 2:** Determine if the following series diverge or converges:

$$\sum_{n=0}^{\infty} \frac{1}{\sqrt{n}}$$

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

**Problem 4:** Determine if the following series diverges or converges:

$$\sum_{n=2}^{\infty} \frac{1}{n (ln(n))^2}$$

<details>
  <summary>Solution</summary>
  
  $$f(x) = \frac{1}{x (ln(x))^2}$$

  From inspection we know that the series positive, contionous, and decreasing for all $x>1$.

  $$\int_{2}^{\infty} \frac{1}{x (ln(x))^2} dx$$
  
  $$\lim_{b\to\infty} \int_{2}^{b} \frac{1}{x (ln(x))^2} dx$$

  Using the u-substiution $u = ln(x)$:

  $$\lim_{b\to\infty} \int_{2}^{b} \frac{1}{u^2} du $$

  $$\lim_{b\to\infty} -\frac{1}{ln(x)} \vert_{2}^{b}  $$

  $$\lim_{b\to\infty} -\frac{1}{ln(b)} + \frac{1}{ln(2)}  = \frac{1}{ln(2)} $$

  Our integral converges to a finite value that means that our original series also converges. However, keep in mind that $\frac{1}{ln(2)}$ is not the total sum of the series.

</details>

---
  
# Alternating Series

Alternating series are series in which every subsequent term switches signs. The two most common alternating series take the form of the following (where $a_n$ can be basically anything):

$$\sum_{n=0}^{\infty} (-1)^n a_n$$

$$\sum_{n=0}^{\infty} (-1)^{n+1} a_n$$

These series are both alternating. The only difference is that the first series starts with a positive term, while the second series starts with a negative term. When it comes to convergence, whether the series starts off with a positive or negative term won't matter.

The term that causes the series to swap signs every term is called the "alternator" in the above series, which would be $(-1)^n$ and $(-1)^{n+1}$. The alternators like $(-1)^n$ are the most common, but they are not the only ones. Consider the following alternating series:

$$\sum_{n=0}^{\infty} cos(n \pi)a_n$$

Since n can only be an integer, the term $cos(n\pi)$ is the alternator as it swaps between 1 and -1 (starting with 1). It can be rewritten as $(-1)^n$.

##

**Alternating Series Test**
If $a_n$ >0. Then the alternating series of either of the forms

$$\sum_{n=1}^{\infty} (-1)^n a_n \text{  and  } \sum_{n=1}^{\infty} (-1)^{n+1} a_n$$

will converge if the following two conditions are satisifed:
- $\lim_{n\to\infty} a_n = 0$
- $a_{n+1} \leq a_n$ for all n (non-increasing)

##

I want to clear up that when determining convergence with the alternating series test, we do the limit of everything that isn't alternating $a_n$. Notice that the alternating series has extremely lenient conditions for convergence. It turns out that there are certain $a_n$ (the non-alternating poriton) that will only converge if they are attached to an alternator. This topic will be discussed more later when I talk about absolute and conditional convergence.

##

**Worked Example**

Determine whether the following series is convergent or divergent:

$$\sum_{n=1}^{\infty} \frac{(-1)^n}{n}$$

We easily recognize that this is an alternating series because of $(-1)^n$, and we know that $a_n > 0$ because $\frac{1}{n} > 0$. We can test the first condition (the limit goes to zero) and figure out that the series satisfies it.

$$\lim_{n\to\infty} \frac{1}{n} = 0$$

For the second condition, we know that $a_n = \frac{1}{n}$ and $a_{n+1} = \frac{1}{n+1}$. We can easily prove that the series is non-decreasing:

$$a_{n+1} \leq a_{n}$$

$$\frac{1}{n+1} \leq \frac{1}{n}$$

$$n+1 \geq n$$

Since our series satisfies both conditions, that means it converges by the alternating series test.

##

**Alternating Series Error Bound**

So far in this series section, we have talked a lot about convergence and divergence, but not what the actual value of the series is. Unfortunately, when it comes to altering series, there isn't a super good way to determine the value. Like all series, we can approximate the infinite sum by just adding the first 100 terms. However, what is different about the alternating series is that we can get an extremely tight error bound on how inaccurate our "approximation" is.

With the alternating series, we can figure out how far we can possibly be from the true value when we add up the first n terms. Obviously, the more terms we add up, the closer we will be to the true value, but we can't do that, so the next best thing is figuring out how far off we potentially are.

##

**Alternating Series Error Bound**

If an alternating seeries converges. Then the error of adding up the first n terms to the real sum is equal to first unused term in the series. M

$$Error = |S-S_n| \leq |a_{n+1}|$$

##

**Worked Example**

Find the range of possible values of the following alternating series if you add the first six terms:

$$\sum_{n=1}^{\infty} \frac{(-1)^{(n-1)}}{n}$$

First, we can enumerate the first six terms of the series and get their sum:

$$\frac{1}{1} - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \frac{1}{5} - \frac{1}{6} = \frac{37}{60}$$

We used the first 6 terms, so our first unused term, $a_n+1$, is the 7th term, which is $\frac{1}{7}$. That means the maximum amount that $\frac{37}{60}$ can be off from the real answer is $\frac{1}{7}$ in either the positive or negative direction.

$$Error = |S-\frac{37}{60}| \leq |\frac{1}{7}|$$

With that information on the maximum error in another direction, we can figure out that the value that the alternating series converges to must lie somewhere within the following range of values:

$$\frac{37}{60} - \frac{1}{7} \geq S \leq \frac{37}{60} + \frac{1}{7}$$

Or as a decimal approximation (safely rounded to three decimals)

$$0.473 \geq S \leq 0.760 $$

In order to have some closure, the infinate series is actually equal to $ln(2)$.

$$\sum_{n=1}^{\infty} \frac{(-1)^{(n-1)}}{n}  ln(2)$$

The true value of $ln(2)$ definitely falls within the error bounds.

$$0.473 \geq 0.693 \leq 0.760 $$

##

### Questions and Soltuions

**Question 1**

**Problem 1:** Determine if the following series diverges or converges:

$$\sum_{n=1}^{\infty} \frac{(-1)^n n^2}{n^3 + 1}$$

<details>
  <summary>Solution</summary>
  First condition is satisifed:

  $$\lim_{n\to\infty} \frac{n^2}{n^3 + 1} = 0$$
  
  Second Coniditon is satisifed through inspection. The denominator grows faster than the numerator so the value of each term is always decreasing (which implies $a_{n+1} \leq a_n$ )

  $$\frac{(n+1)^2}{(n+1)^3 + 1} \leq \frac{n^2}{n^3 + 1}$$

  Therefore the series convergeces by the altnerating series test. 
  
</details>

**Problem 2:** Determine if the following series diverges or converges:

$$\sum_{n=1}^{\infty} \frac{(-1)^{n+3}}{3n + 2}$$

<details>
  <summary>Solution</summary>
  The first coniditon is not satifisfied 

  $$\lim_{n\to\infty} \frac{n+3}{3n+2} = \frac{1}{3}$$
  $$\lim_{n\to\infty} a_n \neq 0$$
  
  Therefore the series diverges by the altnerating series test. 

</details>

**Problem 3:** Determine if the following series diverges or converges:

$$\sum_{n=0}^{\infty} \frac{cos(n\pi) ln(n+1)}{n+1}$$

<details>
  <summary>Solution</summary>
  Notice that the alternator in this series is $cos(n\pi)$ and not the standard $(-1)^n$

  The first condition is satisified 

  $$\lim_{n\to\infty} \frac{ln(n+1)}{n+1} = 0$$

  Second Coniditon is satisifed through inspection. The denominator grows faster than the numerator so the value of each term is always decreasing (which implies $a_{n+1} \leq a_n$ )

  $$\frac{ln(n+2)}{n+2} \leq \frac{ln(n+1)}{n+1}$$

  Therefore the series converges by the alternating series test. 
  
</details>

**Problem 4:** Determine if the following series diverges or converges:

$$\sum_{n=1}^{\infty} (-1)^n cos(n)$$

<details>
  <summary>Solution</summary>
  The first condition is not satifiseid (since the limit of cos(n) as it n approaches infinity doesnt exist):

  $$\lim_{n\to\infty} cos(n) = DNE$$

  Therefore the series diverges by the alternating series test.
  
</details>

**Problem 5:** Determine if the following series diverges or converges:

$$\sum_{n=1}^{\infty} (-1)^n \frac{sin(n)}{n}$$

<details>
  <summary>Solution</summary>
  The first conidtion is satisfied:

  $$\lim_{n\to\infty} \frac{sin(n)}{n} = 0$$
  
  However, if you thought real hard you might have recognized that you can't even apply the alternating series test in this scenario. The alternating series test only works when $a_n$ is positive. 

  Alternating series are known for swapping signs every term but if $a_n$ can be negative then the sign swap might not be every other term. At integers n sin(n) can most definately be a negative number/

  We can't find convergence of this series with the altnerating series test and we will need to wait until later.


**Problem 6:** Determine if the follwoing series diverges or converges:

$$\sum_{n=1}^{\infty} (-1)^n \frac{n!}{n^n}$$

<details>
  <summary>Solution</summary>
  The the first condition is noy satisifed($n!$ grows faster than $n^n$):

  $$\lim_{n\to\infty} \frac{n!}{n^n} = \infty$$

  Therfore the series diverges by the altnerating series test. 

  
</details>

---

# Taylor / Maclaurin Series

##

**The Maclaurin Series of e^{x}**

We can start by listing out a few of the derivatives of $e^{x}$ and their values as the center of the Taylor series (c = 0).

$$f(x) = e^{x} \qquad f(x) = e^0 = 1$$

$$f'(x) = e^{x} \qquad f'(x) = 1$$

$$f''(x) = e^{x} \qquad f''(x) = 1$$

$$f'''(x) = e^{x} \qquad f'''(x) = 1$$

We know that a Macluarin series expansion takes the following form

$$\sum_{n=0}^{\infty} \frac{f^{(n)}(0)x^n}{n!}$$

As shown above, $f^{(n)}(0)$ will always be one, so the Taylor series expansion of $e^x$ is the following:

$$e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!}$$

##

**The Maclaurin Series of sin(x)**

We can again start by listing out a few derivatives of sin(x) and their values at the center of the Taylor series (c = 0).

$$f(x) = sin(x) \qquad f(0) = 0$$

$$f'(x) = cos(x) \qquad f'(0) = 1$$

$$f''(x) = -sin(x) \qquad f''(0) = 0$$

$$f'''(x) = -cos(x) \qquad f'''(0) = -1$$

$$f''''(x) = sin(x) \qquad f''''(0) = 0$$

$$f'''''(x) = cos(x) \qquad f''''(0) = 1$$

Note that all terms in the Taylor series actually contribute, so we can write a series that only hits those that add value. The only important terms are the even terms. In other words, only terms with the indicator $2n+1$ need to be considered. Between the even terms of the series, they also swap signs, so we will need $(-1)^n$ (since it starts positive). Considering all of those things, we get that the series expansion of $sin(x)$

$$e^x = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{(2n+1)!}$$

Our series skips all of the odd terms and adjusts for that fact by having the exponent on x and the exponent on n be adjusted. We skip every other term, starting from the 2nd term. It would recommend looking into the series and proving to yourself that this does indeed describe the behavior of $f^{n}(x)$.

##

**The Maclaurin Series of cos(x)**

The Maclaurin series for cos(x) is super similar to the expansion of sin(x), as is probably expected. If we list some variables and their values at 0, we get:

$$f(x) = cos(x) \qquad f(0) = 1$$

$$f'(x) = -sin(x) \qquad f'(0) = 0$$

$$f''(x) = -cos(x) \qquad f''(0) = -1$$

$$f'''(x) = sin(x) \qquad f'''(0) = 0$$

$$f''''(x) = cos(x) \qquad f''''(0) = 1$$

$$f'''''(x) = -sin(x) \qquad f''''(0) = 0$$

Cosine is the same story as sine except for the fact that odd terms (terms 1, 3, 5, 7, etc.) are the only ones that contribute rather than even terms. The Macularin expansion for cosine is the following:

$$e^x = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n}}{(2n)!}$$

##

### Common Taylor Series Expansions (cenetered at zero) to remember:

$$e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!}$$

$$sin(x) = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{(2n+1)!}$$

$$cos(x) = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n}}{(2n)!}$$

$$tan^{-1}(x) = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{2n+1}$$

##

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

  

