---
layout: post
title: You're up and running!
---

Next you can update your site name, avatar and other options using the _config.yml file in the root of your repository (shown below).

![_config.yml]({{ site.baseurl }}/images/config.png)

The easiest way to make your first post is to edit this one. Go into /_posts/ and update the Hello World markdown file. For more instructions head over to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now) on GitHub.


The Uehling potential, which describes the vaccuum polarisation correction to the regular Coulomb atomic potential, is (in atomic units):
$$
\begin{align*}
V_{vp}(r) &= \int_1^\infty {\rm d}t\, \frac{-2\,Z\alpha^2}{3\pi\,r}\frac{\sqrt{t^2+1}}{t^2}
\left(1 + \frac{1}{2t^2}\right) e^{-2tr/\alpha}\\
&\approx \int_1^{1/r} {\rm d}t\, \frac{-2\,Z\alpha^2}{3\pi\,r}\frac{\sqrt{t^2+1}}{t^2}
\left(1 + \frac{1}{2t^2}\right) e^{-2tr/\alpha}\\
\text{where}~~\alpha &\approx 1/137.036
\end{align*}
$$
The approximation in the second line is rough, but comes from fact that integrand becomes very small for t>r. This potential is largest at small r, where the electric field of the nucleus is extremely strong.


**Example:**
Simple function to integrate function f from [a,b], using adaptive method
Interactive version: [https://godbolt.org/z/f865zExeY](https://godbolt.org/z/f865zExeY)

```cpp
#include <cassert>
#include <cmath>
#include <functional>
#include <iostream>

// 'using' (alias) for functional std::function
using Function = std::function<double(double)>;
```

&nbsp;

&nbsp;

```cpp
// Function that integrates function f, over [a,b], using Simpsons rule.
// Note: n_pts must be odd (even sub-intervals)
double Simpsons(Function f, double a, double b, int n_pts) {
  assert(n_pts % 2 != 0 && "n_pts must be odd for Simpsons rule");
  double dx = (b - a) / (n_pts - 1);
  double integral = (f(a) + f(b)) * dx / 3.0;
  for (int i = 1; i < n_pts - 1; ++i) {
    // ternary operator: w = condition ? val_if_true : val_if_false;
    // i % 2 == 0 means (i, mod 2) - is 0 if i is even
    double w = (i % 2 == 0) ? (2.0 / 3) : (4.0 / 3);  // weight
    double x = a + i * dx;
    integral += f(x) * dx * w;
  }
  return integral;
}
```
