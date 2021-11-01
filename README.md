<h2 align="center">
  MIT 18.336J/6.335J, Fall 2021 <br />
  Fast Methods for Partial Differential and Integral Equations
</h2>

This course broadly covers modern numerical methods for solving large-scale partial differential and integral equations.
The focus varies year to year and is often updated to include state-of-the-art techniques.
This semester we will foucs in particular on Fourier and modern polynomial spectral methods, the fast multipole method, boundary integral equations, and applications to fluid dynamics and electromagnetism.

Catalog description: *A unified introduction to the theory and practice of modern, near linear-time, numerical methods for large-scale partial differential and integral equations.
Topics include: preconditioned iterative methods; generalized Fast Fourier Transform and other butterfly-based methods; multiresolution approaches including multigrid algorithms, hierarchical low-rank matrix decompositions, and low and high frequency Fast Multipole Methods.
Example applications include: aircraft design, cardiovascular system modeling, electronic structure computation, and tomographic imaging.*

## Syllabus

**Lectures**: Tuesday/Thursday 11:00-12:30 PM in room 2-131.

**Office Hours**: In-person times TBD, by appointment via zoom.

**Prerequisites**: This course covers advanced techniques for discretizing and solving PDEs.
Some familiarity with ordinary differential equations, partial differential equaitons, Fourier transforms, linear algebra, and basic numerical methods for PDEs is assumed.
It is strongly recommended that you have taken a previous course on basic numerical methods, such as [2.096/6.336/16.910](http://student.mit.edu/catalog/m6b.html#6.336), [2.097/6.339/16.920](http://student.mit.edu/catalog/m16b.html#16.920), [18.085](http://student.mit.edu/catalog/m18a.html#18.085), or [6.337/18.335](http://student.mit.edu/catalog/m18a.html#18.335).
Problem sets will involve extensive coding and are required to be completed in **Python** or **Julia** notebooks.

**Textbooks & Other Reading**: Recommended reading will be posted as the class progresses.
There is no textbook for the course, but the following books may be useful:
* Strauss "Partial Differential Equations: An Introduction". An advanced undergrad introduction to PDEs.
* Boyd "Chebyshev and Fourier Spectral Methods". Very readable and [available online](http://depts.washington.edu/ph506/Boyd.pdf).
* [Martinsson "Fast Direct Solvers for Elliptic PDEs"](https://doi.org/10.1137/1.9781611976045). Modern and concise.
* LeVeque "Finite difference methods for ordinary and partial differential equations".

**Grading**: 50% problem sets (approximately biweekly), 50% final project report and presentation.
Unless previous arrangements are made, late problem sets will be accepted for 1 week after the initial due date with a 50% penalty.

**Collaboration Policy**: Make a strong effort to solve problems on your own before discussing with any classmates.
You must write up your own code and solutions, and indicate your collaborators on your assignments.

## Problem Sets

### Problem Set 1: Fast Fourier Transforms
<!-- Material finished 09/14. Due on 09/23. -->

### Problem Set 2: Fourier and Finite Difference Helmholtz Solvers
<!-- Material finished 10/07. Due on 10/12. -->

### Problem Set 3: Chebyshev Collocation
<!-- Material finished 10/19. Due on 10/28. -->

### Problem Set 4: Ultraspherical Method
<!-- Material finished 10/21. Due on 11/12. -->

### Problem Set 5: Low-Rank Methods
<!-- Material finished 11/04. Due on 11/23. -->

## Final Projects

The final project is a 10-12 page paper and a 15 minute presentation during the last week of classes.
**The final project is broad in scope, but must include the implementation of a fast algorithm in Python or Julia along with performance and error analyses.**
The project can take the form a "literature review project" discussing a published algorithm or a "research project" attempting to implement a new solver for a problem of your choice.

### Lit. review projects

One possibility is to review and implement an algorithm that was mentioned briefly or not covered in the course.
Such a project should follow one or several published research papers describing the algorithm, along with a new implementation.
Possible topics and suggested papers include:
* Advanced optimizations for production-level FFT implementations.
  * [Johnson & Frigo "Implementing FFTs in Practice"](https://github.com/mitmath/18336/blob/master/readings/johnson_frigo_implementing_ffts.pdf)
* Hierarchical Poincare-Steklov schemes using Chebyshev polynomails.
  * [Martinsson "The Hierarchical Poincare-Steklov (HPS) solver for elliptic PDEs: A tutorial"](https://github.com/mitmath/18336/blob/master/readings/martinsson_poincare_steklov.pdf)
* Parity-mixing in sine/cosine solvers.
  * [Vasil et al. "A new method for fast transforms in parity-mixed PDEs"](https://github.com/mitmath/18336/blob/master/readings/vasil_parity_mixing.pdf)
* Rectangular collocation with aliasing analysis.
  * [Driscoll & Hale "Rectangular spectral collocation"](https://doi.org/10.1093/imanum/dru062)
* Alternating direction implicit scheme for multidimensional Chebyshev Poisson solvers.
  * [Fortunato & Townsend "Fast Poisson solvers for spectral methods"](https://arxiv.org/abs/1710.11259)
* Bivariate orthogonal polynomials on triangles.
  * [Olver et al. "A Sparse Spectral Method on Triangles"](https://doi.org/10.1137/19M1245888)
* Non-uniform Fast Fourier Transforms.
  * [Barnett et al. "A Parallel Nonuniform Fast Fourier Transform Library Based on an 'Exponential of Semicircle' Kernel"](https://doi.org/10.1137/18M120885X)
* Sparse spectral elements.
  * [Fortunato et al. "The ultraspherical spectral element method"](https://doi.org/10.1016/j.jcp.2020.110087)
  
### Research projects
  
Another option is to use the methods covered in class to implement a fast solver for a research problem in your field.
This should include:
* A discussion of the scientific problem and a brief derivation of the model PDE.
* Mention of the current commonly used methods in the field for the problem.
* A fast implementation of a new solver for the problem, or a related first-step.
* Discussion of the prospects and limitations of fast/high-order techniques for this problem in the future.

The goal should be producing a functional solver matching or improving on existing techniques in certain cases.
However, it is understood that this may not turn out to be feasible (or even possible), and that's what makes it research!
In that case, an implementation for a related toy model is expected, along with an analysis of the barriers to making a solver for the original problem.

### Report & presentation format

Your report should be written in the style a SIAM article, using the [SIAM article LaTeX templates](https://www.siam.org/publications/journals/about-siam-journals/information-for-authors#LaTex2e-Standard).
Your report should be between 10 and 12 pages.
The SIAM layout is very spacious so this is not a lot of space.
Make sure your presentation and notation is concise, but also has enough content and is not just padded out with images!

Along with your report, you must submit the code implementing your algorithms, preferably in the form of a Jupyter notebook.
Make good use of headings, text, comments, and descriptive function/variables names.
Good code is code that is easily understandable by others!

Your report and presentation should both include:
* Background information for your algorithm / physical application.
* A concise mathematical description of the algorithm you're using.
* Performance and error analysis of your implementation.

## Lecture Material and Summaries

### Lecture 1: Introduction to fast methods, PDEs, IEs
<!-- Thursday Sept 9 -->

**Summary**
* Course policies
* Why fast algorithms? History of fast algorithms for the Fourier transform.
* Why PDEs? Models for physical systems. Classes of PDEs. Elliptic regularity theorem.
* Why integral equations? Better conditioning from using exact solution formulae.

**Related Reading**
* [Cipra "Top ten algorithms of the 20th century"](https://github.com/mitmath/18336/blob/master/readings/siam_news_top_10_algorithms.pdf)

### Lecture 2: Fourier transforms
<!-- Tuesday Sept 14 -->
<!-- Necessary for pset 1 -->

**Summary**
* Continuous FT, discrete FT.
* History of FFTs. Facts that make FFTs possible.
* Radix-2 Cooley-Tukey algorithm.
* Radix-3 and algorithms for prime N.
* Sine, cosine, and other Fourier-related transforms.

**Related Reading**
* [Johnson & Frigo "Implementing FFTs in Practice"](https://github.com/mitmath/18336/blob/master/readings/johnson_frigo_implementing_ffts.pdf).

### Lecture 3: PDE discretization and preconditioning
<!-- Thursday Sept 16 -->

**Summary**
* Discretizing linear boundary value problems.
* Discretizing nonlinear / initial value problems.
* Direct solvers and their complexity.
* Iterative solvers and their convergence.
* Fourier preconditioning using FFTs.
  * Circulant matrices: diagonalization using DFT.
  * Toeplitz matrices: embedding into circulant form.
  * Hankel matrices: converison to Toeplitz form.

### Lecture 4: Finite differences and fast Poisson solvers in 1D
<!-- Tuesday Sept 21 -->

**Summary**
* Review of finite difference methods.
* Spectral preconditioning for fast Poisson solvers in 1D:
  * Periodic BCs using FFTs.
  * Dirichlet BCs using DSTs.
  * Neumann BCs using DCTs.
  * Gauge fixing.
  
### Lecture 5: Fast finite difference solvers in multiple dimensions
<!-- Thursday Sept 23 -->

**Summary**
* Sylvester equations, Bartels-Stewart algorithm.
* Kronecker products and block matrices.
* Fast linear algebra with structured block matrices.
* Fast Poisson solvers in multiple dimensions.
* Extensions to other PDEs, e.g. Helmholtz.
* Limitations and alternatives for non-constant coefficients.

### Lecture 6: Domain decomposition methods
<!-- Tuesday Sept 28 -->

**Summary**
* Extensions to other domains.
* Schur complement / Poincare-Steklov method for domain decomposition.
  * Connecting two 1D segments.
  * Connecting two 2D boxes.
  * Heirarchical Poincare-Steklov method for multiple connections.
* Distorted domains.

**Related Reading**
* [Martinsson "The Hierarchical Poincare-Steklov (HPS) solver for elliptic PDEs: A tutorial"](https://github.com/mitmath/18336/blob/master/readings/martinsson_poincare_steklov.pdf)

### Lecture 7: Introduction to spectral methods
<!-- Thursday Sept 30 -->

**Summary**
* Spectral representations of functions.
* Rates of convergence.
* Truncation and discretization error.
* Convergence of Fourier series.

**Related Reading**
* Boyd chapters 1 & 2.

### Lecture 8: Fourier spectral methods I
<!-- Tuesday October 5 -->

**Summary**
* Weighted residual method for discretizing PDEs.
* Fourier solver for Poisson equation with periodic BCs.
  * Comparison to finite difference solver. Eigenvalue corrections.
* Fourier spectral collocation.
* Sine and cosine solvers for Poisson equation with Dirichlet/Neumann BCs.
  * Conditions on forcing for exponential convergence.
  * Parity mixing.

**Related Reading**
* Boyd chapter 3.
* [Vasil et al. "A new method for fast transforms in parity-mixed PDEs"](https://github.com/mitmath/18336/blob/master/readings/vasil_parity_mixing.pdf)

### Lecture 9: Fourier spectral methods II
<!-- Thursday October 7 -->
<!-- Necessary for pset 2 -->

**Summary**
* Extending to multiple dimensions via direct products.
* Extending to systems of equations. Maintaining bandedness.
* Pseudospectral method for evaluating nonlinearities.
* Aliasing errors, dealiasing rules for arbitrary-order nonlinearities.
* Examples: Dedalus code, Yeung group turbulence simulations.

**Related Reading**
* [Yeung & Ravikumar "Advancing understanding of turbulence through extreme-scale computation: Intermittency and simulations at large problem sizes"](https://github.com/mitmath/18336/blob/master/readings/yeung_fourier_turbulence.pdf)

### Lecture 10: Polynomial interpolation
<!-- Tuesday October 12 -->

**Summary**
* Polynomial interpolation.
  * Lagrange representation.
  * Lebesgue constant of equispaced points. Runge phenomenon.
  * Lebesgue constant of Chebyshev nodes.
* Overview of orthogonal polynomials.
  * Chebyshev polynomials.
  * Convergence of Chebyshev series. Singularities in elliptical coordinates.
* Gaussian quadrature.
  * Deriving nodes and weights.
  * Discretization error from polynomial interpolation on Gaussian quadrature nodes.

**Related Reading**
* Boyd chapter 4.

### Lecture 11: Chebyshev collocation methods
<!-- Thursday October 14 -->

**Summary**
* Convergence of Gegenbauer polynomials. Legendre polynomials and finite elements.
* Collocation matrices for differentiation.
* Collocation matrices for multiplication.  Aliasing errors.
* Roots vs extrema grid.
* Boundary bordering. Generalized tau equivalence.
* Rectangular collocation. Generalized tau equivalence.

**Related Reading**
* [Driscoll & Hale "Rectangular spectral collocation"](https://doi.org/10.1093/imanum/dru062)

### Lecture 12: Dense Chebyshev spectral methods
<!-- Tuesday October 19 -->
<!-- Necessary for pset 3 -->

**Summary**
* Newton's method in function space for nonlinear ODEs.
* Chebyshev recursion formulae.
* T-to-T matrices for differentiation.
* T-to-T matrices for multiplication. Band-limited expansions.
* Classical tau method for boundary conditions.

### Lecture 13: Sparse Chebyshev spectral methods
<!-- Thursday October 21 -->
<!-- Necessary for pset 4 -->

**Summary**
* Chebyshev-T derivatives are Chebyshev-U polynomials.
* T-to-U differentiation and conversion matrices.
* Differentiation and conversion between ultraspherical polynomials.
* Ultraspherical method for arbitrary-order linear ODEs. Generalized tau equivalence.
* Woodbury matrix identity for banded + multi-bordered matrices.

**Related Reading**
* [Olver & Townsend "A Fast and Well-Conditioned Spectral Method"](https://doi.org/10.1137/120865458)

### Lecture 14: Multidimensional sparse methods
<!-- Tuesday October 26 -->

**Summary**
* Block-banded formulation for systems of equations.
* Pseudospectral method for nonlinear IVPs.
* Polynomial spectral methods in multiple dimensions:
  * Chebyshev-Chebyshev, alternating direction implicit scheme
  * Fourier-Chebyshev for periodic layers, cylinders, etc.
* Example: incompressible Navier-Stokes without splitting.
* Examples using the Dedalus code.
  
**Related Reading**
* [Fortunato & Townsend "Fast Poisson solvers for spectral methods"](https://arxiv.org/abs/1710.11259)

### Lecture 15: Sparse methods for curvilinear domains
<!-- Thursday October 28 -->

**Summary**
* Spectral methods with coordinate singularities:
  * Non-smoothness of vector/tensor components.
  * Radial regularity of Fourier components in polar coordinates.
* Radial regularity of vector/tensor components in polar coordinates.
* Modified Jacobi bases for tensors in the disk.
* Spin-weighted spherical harmonics for tensors on the sphere.
* Examples using the Dedalus code.
  
**Related Reading**
* [Vasil et al. "Tensor calculus in polar coordinates using Jacobi polynomials"](https://doi.org/10.1016/j.jcp.2016.08.013)
* [Vasil et al. "Tensor calculus in spherical coordinates using Jacobi polynomials. Part-I: Mathematical analysis and derivations"](https://doi.org/10.1016/j.jcpx.2019.100013)
* [Lecoanet et al. "Tensor calculus in spherical coordinates using Jacobi polynomials. Part-II: Implementation and examples"](https://doi.org/10.1016/j.jcpx.2019.100012)

### Lecture 16: Introduction to low-rank methods
<!-- Tuesday November 2 -->

**Summary**
* Scale separation in gravity.
  * Direct N-body using Newton's law for point masses.
  * Poisson equation for gravitational potential using Gauss's law for continuous distributions.
  * Both are limited in between: many point masses or well-separated distributions.
  * Green's function gives integral equation for potential: low rank for well-separated distributions.
* Singular value decomposition.
  * Basic definition and derivation.
  * Optimal low-rank approximations using truncated SVDs. 

### Lecture 17: Approximating low-rank interactions
<!-- Thursday November 4 -->
<!-- Necessary for pset 5 -->

**Summary**
* Fast matrix-vector products using low-rank approximations.
* Low-rank approximations to functions. Fast inner products for integral equations.
* Low-rank nature of gravitational interaction.
  * Projection: merging sources to compress the operator domain.
  * Interpolation: merging measurements to compress the operator range.
  * Duality of projection and interpolation.
* Numerically approximating the SVD using Gaussian elimination for matrices and functions.

### Lecture 18: Fast multipole methods
<!-- Tuesday November 9 -->

**Summary**
* Analytical low-rank expansions using Taylor series.
* 2D and 3D multipole expansions. Error estimates.
* Hierarchical decompositions for error control.
* Barnes-Hut and FMM in 2D. Comparison to direct methods.

**Related Reading**
* [Beatson & Greengard "A short course on fast mulitpole methods"](https://github.com/mitmath/18336/blob/master/readings/beatson_greengard_fmm.pdf)

### Lecture 19: Formulating boundary integral equations
<!-- Tuesday November 16 -->

**Summary**
* From PDEs to integral equations: complicated boundaries, exterior problems.
* Basic ideas from potential theory for Laplace equation:
  * Fictitious charges.
  * Single-layer potentials.
  * Double-layer potentials.
* Weakly singular kernels. Compact operators. First and second kind Fredholm integral equations. 

**Related Reading**
* [Demanet's 18.336 2014 Class Notes](https://github.com/mitmath/18336/blob/master/readings/demanet_18336_2014_notes.pdf)

### Lecture 20: Discretizing boundary integral equations
<!-- Thursday November 18 -->

**Summary**
* Global quadrature discretizations.
* Quadrature for weakly singular kernels.
* Panel-based discretizations.
* Domains with corners. Diadic refinement.

**Related Reading**
* [Martinsson's lectures from 2014 CBMS/NSF Conference on Fast Direct Solvers](http://amath.colorado.edu/faculty/martinss/2014_CBMS/lectures.html).

### Lecture 21: Advanced boundary integral equations
<!-- Tuesday November 23 -->

**Summary**
* BIEs for other equations:
  * Stokes flow. Stokeslets and Stresslets.
  * Linear elasticity.
  * Helmholtz. Spurious resonances and combined field forms.
  * Time-harmonic Maxwell.
* Summary and comparison to PDE solvers.

**Related Reading**
* [Martinsson's lectures from 2014 CBMS/NSF Conference on Fast Direct Solvers](http://amath.colorado.edu/faculty/martinss/2014_CBMS/lectures.html).

<!-- Presentation day 1: Tuesday November 30 -->
<!-- Presentation day 2: Thursday December 2 -->
<!-- Presentation day 3: Tuesday December 7 -->
<!-- Presentation day 4: Thursday December 9 -->
