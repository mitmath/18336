<h2 align="center">
  MIT 18.336J/6.7340J, Spring 2024 <br />
  Fast Methods for Partial Differential and Integral Equations
</h2>

Catalog description: *A unified introduction to the theory and practice of modern, near linear-time, numerical methods for large-scale partial differential and integral equations.
Topics include: preconditioned iterative methods; generalized Fast Fourier Transform and other butterfly-based methods; multiresolution approaches including multigrid algorithms, hierarchical low-rank matrix decompositions, and low and high frequency Fast Multipole Methods.
Example applications include: aircraft design, cardiovascular system modeling, electronic structure computation, and tomographic imaging.*

## Syllabus

**Lectures**: Monday/Wednesday 9:30-11:00 am in 2-136.

**Office Hours**: TBD

**Prerequisites**: This course covers advanced techniques for discretizing and solving PDEs.
Some familiarity with ordinary differential equations, partial differential equations, Fourier transforms, linear algebra, and basic numerical methods for PDEs is assumed.
It is strongly recommended that you have taken a previous course on basic numerical methods, such as [2.096/6.336/16.910](http://student.mit.edu/catalog/m6b.html#6.336), [2.097/6.339/16.920](http://student.mit.edu/catalog/m16b.html#16.920), [18.085](http://student.mit.edu/catalog/m18a.html#18.085), or [6.337/18.335](http://student.mit.edu/catalog/m18a.html#18.335).
Problem sets will involve extensive coding: they may be completed in the language of your choice. Solutions and class demos will be in **Julia**.

**Textbooks & Other Reading**: Recommended reading will be posted as the class progresses.
There is no textbook for the course, but the following books may be useful:
* Strauss "Partial Differential Equations: An Introduction". An advanced undergrad introduction to PDEs.
* Boyd "Chebyshev and Fourier Spectral Methods". Very readable and [available online](http://depts.washington.edu/ph506/Boyd.pdf).
* [Martinsson "Fast Direct Solvers for Elliptic PDEs"](https://doi.org/10.1137/1.9781611976045). Modern and concise.
* LeVeque "Finite difference methods for ordinary and partial differential equations". (MIT access through SIAM.)

**Grading**: 50% problem sets (approximately biweekly), 50% final project report and presentation.
Unless previous arrangements are made, late problem sets will be accepted for 1 week after the initial due date with a 50% penalty.

**Collaboration Policy**: Make a strong effort to solve problems on your own before discussing with any classmates.
You must write up your own code and solutions, and indicate your collaborators on your assignments.

## Problem Sets

Problem sets will be posted here (approximately biweekly) and should be submitted on [Gradescope](https://www.gradescope.com/).

## Final Projects

The final project is a 10-12 page paper and a 15 minute presentation during the last week of classes.
**The final project is broad in scope, but must include the implementation of a fast algorithm in Python or Julia along with performance and error analyses.**
The project can take the form of a "literature review project" discussing a published algorithm or a "research project" attempting to implement a new solver for a problem of your choice.

### Lit. review projects

One possibility is to review and implement an algorithm that was mentioned briefly or not covered in the course.
Such a project should follow one or several published research papers describing the algorithm, along with a new implementation.
Possible topics and suggested papers include:
* Advanced optimizations for production-level FFT implementations.
  * [Johnson & Frigo "Implementing FFTs in Practice"](https://github.com/mitmath/18336/blob/master/readings/johnson_frigo_implementing_ffts.pdf)
* Hierarchical Poincare-Steklov schemes using Chebyshev polynomials.
  * [Martinsson "The Hierarchical Poincare-Steklov (HPS) solver for elliptic PDEs: A tutorial"](https://github.com/mitmath/18336/blob/master/readings/martinsson_poincare_steklov.pdf)
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
The SIAM layout has generous margins so this is not a lot of space.
Make sure your presentation and notation is concise, but also has enough content and is not just padded out with images!

Along with your report, you must submit the code implementing your algorithms, preferably in the form of a Jupyter notebook.
Make good use of headings, text, comments, and descriptive function/variables names.
Good code is code that is easily understandable by others!

Your report and presentation should both include:
* Background information for your algorithm / physical application.
* A concise mathematical description of the algorithm you're using.
* Performance and error analysis for your implementation.

## Lecture Material and Summaries

### Lecture 1

[Notes](https://github.com/mitmath/18336/blob/master/notes/lecture_01.pdf)

* Why do we need fast PDE solvers? Modeling, simulation, design, and inference.
* Solving PDEs on the computer: discretize, solve, and analyze.
* Finite differences: epsilon accuracy, at what cost?

### Lecture 2

[Notes](https://github.com/mitmath/18336/blob/master/notes/lecture_02.pdf)

* Symmetry and structure in a simple boundary value problem.
* What structure appears in the discretization and how do we leverage it?
* Locality and sparsity, translation invariance and Toeplitz matrices.
* Fourier modes and diagonalization.

**Further reading:** Finite difference approximation review, chapters 1 and 2 in LeVeque.

