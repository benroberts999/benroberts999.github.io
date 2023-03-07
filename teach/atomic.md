---
layout: page
title: Computational Atomic Physics
permalink: /teaching/atomic/
---

## PHYS4070/7270 (Advanced Computational Physics)

Important to note: this is **not** a general overview to atomic physics.
There are many extremely important topics I am not discussing at all, e.g., spin-orbit effect, theory of angular momentum addition and coupling etc., which are crucial for understanding quantum mechanics of atoms.
However, those are essentially regular quantum mechanics, which you have seen in other courses, and do not require a computer.
Here, I focus on the aspects of many-body atomic physics for which computational calculations are essential.
Some excellent sources to pursue these other topics in more detail are books by
Sakurai [1],
Johnson [2],
Sobelman [3],
and
Bethe and Salpeter [4],
which are available in the library.

  1. J. J. Sakurai, Modern Quantum Mechanics (2011) [in particular Chapters 3, 5, 7]
  2. W. R. Johnson, Atomic Structure Theory (2007)
  3. I. I. Sobelman, Atomic Spectra and Radiative Transitions (1992)
  4. H. A. Bethe and E. E. Salpeter, Quantum Mechanics of One-and Two-Electron Atoms (1977)

## Lecture Notes

* 01: [Hydrogenlike atoms]({{ site.baseurl }}/teach/atomic/01-Atomic-Hydrogen.pdf)
* 02: [Numerical integration]({{ site.baseurl }}/teach/atomic/02-Atomic-Integration.pdf)
* 03: [Multi-electron atoms]({{ site.baseurl }}/teach/atomic/03-Atomic-HartreeFock.pdf)

## Project (first assignment)

* [Hartree-Fock for Li]({{ site.baseurl }}/teach/atomic/Project1-Atomic-2023.pdf)

## Worksheets and basic tutorials

* 01: Introduction, getting up and running: [WS01-Introduction.pdf]({{ site.baseurl }}/teach/atomic/WS01-Introduction.pdf), [WS01-Introduction.md]({{ site.baseurl }}/teach/atomic/WS01-Introduction.md)
  * Quick start guide: [QuickStart.pdf]({{ site.baseurl }}/teach/atomic/QuickStart.pdf), [QuickStart.md]({{ site.baseurl }}/teach/atomic/QuickStart.md)
* 02: Matrices, solving eigenvalue problem for Hydrogen [WS02-MatrixEigensystems.pdf]({{ site.baseurl }}/teach/atomic/WS02-MatrixEigensystems.pdf), [WS02-MatrixEigensystems.md]({{ site.baseurl }}/teach/atomic/WS02-MatrixEigensystems.md)
  * Arrays in C++: [Tutorial_Array-Vector.pdf]({{ site.baseurl }}/teach/atomic/Tutorial_Array-Vector.pdf), [Tutorial_Array-Vector.md]({{ site.baseurl }}/teach/atomic/Tutorial_Array-Vector.md)
  * Classes in C++: [Tutorial_Classes.pdf]({{ site.baseurl }}/teach/atomic/Tutorial_Classesr.pdf), [Tutorial_Classes.md]({{ site.baseurl }}/teach/atomic/Tutorial_Classes.md)
* 03: [WS03-Integration.pdf]({{ site.baseurl }}/teach/atomic/WS03-Integration.pdf), [WS03-Integration.md]({{ site.baseurl }}/teach/atomic/WS03-Integration.md)
  * Functions, templates, lambdas in C++: [Tutorial_FunctionsTemplatesFunctional.pdf]({{ site.baseurl }}/teach/atomic/Tutorial_FunctionsTemplatesFunctional.pdf), [Tutorial_FunctionsTemplatesFunctional.md]({{ site.baseurl }}/teach/atomic/Tutorial_FunctionsTemplatesFunctional.md)

## Basic tutorials (correspond to each worksheet)
* 01a

## Other C++ resources

* Intro to c++ examples: [github.com/benroberts999/cpp-cheatsheet](https://github.com/benroberts999/cpp-cheatsheet)
  * A list of several compilable examples
* [hackingcpp.com/](https://hackingcpp.com/)
  * A large array of nicely formatted tutorials, examples, and cheat-sheets.
  * Start with: [hackingcpp.com/cpp/beginners_guide](https://hackingcpp.com/cpp/beginners_guide.html)
* [cplusplus.com/](https://www.cplusplus.com/)
  * Good, lots of examples, beginner friendly
* [cppreference.com/](https://en.cppreference.com/)
  * The standard resource, extremely thorough and detailed. Not very beginner-friendly however
* [Compiler Explorer](https://godbolt.org/)
