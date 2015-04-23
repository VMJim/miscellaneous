---
title: "Model Selection with t-stat and F-stat"
author: "jvm"
date: "April 21, 2015"
---

As this thread is not receiving the attention I think it deserves, let me also write out the t-statistic and F-statistic cases. I will *cut* some *corners* because this is quite a cumbersome exercise -- as you will see -- that relies on some serious matrix algebra.

What is the F-statistic? Glad you asked. In case of testing if a single coefficient is zero, say $$ b_j $$ -- we call this model the restricted model --, the F-stat is usually expressed as:

$$ F = \frac{ SSR_{restricted} - SSR } {s^2} $$, 

where $$ s^2 = SSR/(n-k) $$ is the unbiased estimator of the error's variance and SSR is the Sum of Squared Residuals of the unrestricted model. Selecting the model with the the lowest $$ SSR_{restricted} $$ among the available models is equivalent to dropping the least significant variable from the model (the F-test is a right-*tailed* test).

**If you trust me that $$ F_{stat} = t_{stat}^2 $$ we're done.** If not continue reading.

The definition of the t-statistic in the linear regression model may be stated as follows:

$$ \frac {  b_{j} } { s * \sqrt{ (X'X)_{jj}^{-1}  } }$$ squaring gives:  

$$ \frac {  {b_j}^{2}  } { {s^2} * (X'X)_{jj}^{-1} }  $$ because $s^2$ appears in the numerators of both $$F$$ and $$t^2$$, we may simplify the demonstrandum to:  

$$ SSR_{restricted} - SSR = \frac{ b_{j}^2 }{ (X'X)_{jj}^{-1} } $$ proving this is not as easy as it seems. ;)  

Where $$ (X'X)_{jj}^{-1} $$ denotes the j-th diagonal element of the inverse of $$ X'X $$ where $$ X $$ is the n-by-k design matrix.  

In the linear regression model it holds that $$ SSR_{restricted} - SSR = b_{j} x_{j}'( I - X_{-j}( X_{-j}'X_{-j} )^{-1}X_{-j}' ) x_{j} b_j = b_{j}^2 x_{j}'( I - X_{-j}( X_{-j}'X_{-j} )^{-1}X_{-j}' ) x_{j} $$ ( can be found in any intermediate/advanced treatment on linear regression, e.g. [Heij et al. (2005)](http://global.oup.com/booksites/content/0199268010/) ). 

The demonstrandum now further simplifies to  $$ \frac{1} {x_{j}'( I - X_{-j}( X_{-j}'X_{-j} )^{-1}X_{-j}' ) x_{j} } = (X'X)_{jj}^{-1} $$. That this last equation is true, can be seen by partioning the design matrix $$ X $$ as $$ [X_{-j} \vdots x_j] $$, then $$ X'X $$ equals:

$$
\begin{bmatrix} 
X_{-j}'X_{-j} & X_{-j}'x_j \\
x_{j}'X_{-j} & x_j'x_j  \\
\end{bmatrix} .
$$

Using the result on the inverse of block matrices in [Matrix Cookbook Chapter 9.1.3](https://duckduckgo.com/?q=matrix+cookbook), we find that the j-th diagonal element of $$ (X'X)^{-1} $$ is indeed equal the last expression of the demonstrandum given above. Q.E.D.
