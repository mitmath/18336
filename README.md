## 18.336J/6.335J: Fast Methods for Partial Differential and Integral Equations 

A unified introduction to the theory and practice of modern, near linear-time, numerical methods for large-scale partial differential and integral equations. 
Topics include: preconditioned iterative methods; generalized Fast Fourier Transform and other butterfly-based methods; multiresolution approaches including multigrid algorithms, hierarchical low-rank matrix decompositions, and low and high frequency Fast Multipole Methods. 
Example applications include: aircraft design, cardiovascular system modeling, electronic structure computation, and tomographic imaging.

This semester we will focus in particular in Fourier and polynomial spectral methods, FMM, methods for integral equations, and applications to fluid dynamics and electromagnetism.

## Syllabus

**Lectures**: Tuesday/Thursday 9:30-11:00 am (2-136).  

**Office Hours**: TBD. By arrangement for now.

**Prerequisites**: This course covers advanced techniques for discretizing and solving PDEs. 
Some familiarity with ordinary differential equations, partial differential equaitons, Fourier transforms, linear algebra, and basic numerical methods for PDEs is assumed. 
It is strongly recommended that you have taken a previous course on basic numerical methods, such as [2.096/6.336/16.910](http://student.mit.edu/catalog/m6b.html#6.336), [2.097/6.339/16.920](http://student.mit.edu/catalog/m16b.html#16.920), [18.085](http://student.mit.edu/catalog/m18a.html#18.085), or [6.337/18.335](http://student.mit.edu/catalog/m18a.html#18.335).
Problem sets will involve extensive coding and are required to be completed in **Python** or **Julia** notebooks.

**Textbooks & Other Reading**: Recommended reading will be posted as the class progresses. There is no textbook for the course, but the following books may be useful:
* Strauss "Partial Differential Equations: An Introduction". An advanced undergrad intrdouction to PDEs.
* Boyd "Chebyshev and Fourier Spectral Methods". Very readable and [available online](http://depts.washington.edu/ph506/Boyd.pdf).
* LeVeque "Finite difference methods for ordinary and partial differential equations".
* LeVeque "Finite volume methods for hyperbolic problems".

**Grading**: 50% problem sets (approximately biweekly), 50% final project report and presentation.

**Collaboration Policy**: Make a strong effort to solve problems on your own before discussing with any classmates.  You must write up your own code and solutions, and indicate your collaborators on your assignments.

## Problem Sets

### Problem Set 1: Implementing an FFT.
Available on Stellar. Due on Stellar by midnight on Tuesday 09/24.

### Problem Set 2: Fourier and Finite Difference Helmholtz Solvers.
Available on Stellar. Due on Stellar by midnight on Thursday 10/17.

## Lecture Material and Summaries

### Lecture 1: Introduction to Fast Methods, PDEs, IEs

**Summary**
* Course policies
* Julia tutorial: 09/06/2019 5-7pm (32-141)
* Why fast algorithms? History of fast algorithms for the Fourier transform.
* Why PDEs? Models for physical systems. Classes of PDEs. Elliptic regularity theorem.
* Why integral equations? Better conditioning from using exact solution formulae.

**Related Reading**
* [Top ten algorithms of the 20th century](https://github.com/mitmath/18336/blob/master/readings/siam_news_top_10_algorithms.pdf)

### Lecture 2: Fast Fourier transforms

**Summary**
* Continuous FT, discrete FT.
* History of FFTs. Facts that make FFTs possible.
* Radix-2 Cooley-Tukey algorithm.
* Radix-3 and algorithms for prime N.

**Related Reading**
* [Johnson & Frigo "Implementing FFTs in Practice"](https://github.com/mitmath/18336/blob/master/readings/johnson_frigo_implementing_ffts.pdf).

### Lecture 3: Some applications of FFTs

**Summary**
* Problem Set 1 assigned: due on Stellar by midnight on Tuesday 09/24.
* Sine, cosine, and Chebyshev transforms.
* Fast matrix-vector products using FFTs.
  * Circulant matrices: diagonalization using DFT.
  * Toeplitz matrices: embedding into circulant form.
  * Hankel matrices: converison to Toeplitz form.

### Lecture 4: Finite differences and fast Poisson solvers in 1D

**Summary**
* Review of finite difference methods.
* Spectral preconditioning for fast Poisson solvers in 1D:
  * Periodic BCs using FFTs.
  * Dirichlet BCs using DSTs.
  * Neumann BCs using DCTs.
  * Gauge fixing.
  
### Lecture 5: Fast finite difference solvers in multiple dimensions

**Summary**
* Sylvester equations, Bartels-Stewart algorithm.
* Kronecker products and block matrices.
* Fast matrix-vector products with structured block matrices.
* Fast Poisson solvers in multiple dimensions.
* Extensions to other PDEs, e.g. Helmholtz.
* Limitations and alternatives for non-constant coefficients.

### Lecture 6: Domain decomposition methods

**Summary**
* Extensions to other domains.
* Schur complement / Poincare-Steklov method for domain decomposition.
  * Connecting two 1D segments.
  * Connecting two 2D boxes.
  * Heirarchical Poincare-Steklov method for multiple connections.
* Distorted domains.

**Related Reading**
* [Martinsson "The Hierarchical Poincare-Steklov (HPS) solver for elliptic PDEs: A tutorial"](https://github.com/mitmath/18336/blob/master/readings/marinsson_poincare_steklov.pdf)

### Lecture 7: Introduction to spectral methods

**Summary**
* Wrap up domain decomposition and distorted domains. Comparison to finite elements.
* Introduction to spectral methods.
  * Spectral representations of functions.
  * Rates of convergence.
  * Truncation and discretization error.
  * Convergence of Fourier series.
  
**Related Reading**
* Boyd chapters 1 & 2.

### Lecture 8: Fourier spectral methods I

**Summary**
* Weighted residual method for discretizing PDEs.
* Fourier solver for Poisson equation with periodic BCs.
  * Comparison to finite difference solver. Eigenvalue corrections.
* Fourier spectral collocation.
* Sine and cosine solvers for Poisson equation with Dirichlet/Neumann BCs.
  * Conditions on forcing for exponential convergence.
  
**Related Reading**
* Boyd chapter 3.
  
### Lecture 9: Fourier spectral methods II

**Summary**
* Parity mixing.
* Extending to multiple dimensions via direct products.
* Extending to systems of equations. Maintaining bandedness.
* Pseudospectral method for evaluating nonlinearities.
