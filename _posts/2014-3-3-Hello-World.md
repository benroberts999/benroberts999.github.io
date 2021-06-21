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



<iframe width="800px" height="200px" src="https://godbolt.org/e#g:!((g:!((g:!((h:codeEditor,i:(fontScale:20,fontUsePx:'0',j:2,lang:c%2B%2B,selection:(endColumn:31,endLineNumber:20,positionColumn:31,positionLineNumber:20,selectionStartColumn:31,selectionStartLineNumber:20,startColumn:31,startLineNumber:20),source:'%23include+%3Ccassert%3E%0A%23include+%3Ccmath%3E%0A%23include+%3Cfunctional%3E%0A%23include+%3Ciostream%3E%0A%0A//+!'using!'+(alias)+for+functional+std::function%0Ausing+Function+%3D+std::function%3Cdouble(double)%3E%3B%0A%0A//+Function+that+integrates+function+f,+over+%5Ba,b%5D,+using+Simpsons+rule.%0A//+Note:+n_pts+must+be+odd+(even+sub-intervals)%0Adouble+Simpsons(Function+f,+double+a,+double+b,+int+n_pts)+%7B%0A++assert(n_pts+%25+2+!!%3D+0+%26%26+%22n_pts+must+be+odd+for+Simpsons+rule%22)%3B%0A++double+dx+%3D+(b+-+a)+/+(n_pts+-+1)%3B%0A++double+integral+%3D+(f(a)+%2B+f(b))+*+dx+/+3.0%3B%0A++for+(int+i+%3D+1%3B+i+%3C+n_pts+-+1%3B+%2B%2Bi)+%7B%0A++++//+ternary+operator:+w+%3D+condition+%3F+val_if_true+:+val_if_false%3B%0A++++//+i+%25+2+%3D%3D+0+means+(i,+mod+2)+-+is+0+if+i+is+even%0A++++double+w+%3D+(i+%25+2+%3D%3D+0)+%3F+(2.0+/+3)+:+(4.0+/+3)%3B++//+weight%0A++++double+x+%3D+a+%2B+i+*+dx%3B%0A++++integral+%2B%3D+f(x)+*+dx+*+w%3B%0A++%7D%0A++return+integral%3B%0A%7D%0A%0A//+Integrates+function+f+from+%5Ba,b%5D,+using+adaptive+method,+until+error+drops%0A//+below+err_target.+Recursive+function.%0A//+Note:+This+is+very+inefficient%3B+I+have+tried+to+make+it+simple+abd+clear+at%0A//+the+expense+of+performance%0Adouble+adaptive(Function+f,+double+a,+double+b,+double+err_target,%0A++++++++++++++++int+depth+%3D+1)+%7B%0A++//+Calculate+integral+twice,+once+with+3,+once+with+7+points%0A++//+3+is+minimum+for+Simpsons+rule%0A++double+integral_3+%3D+Simpsons(f,+a,+b,+3)%3B%0A++double+integral_7+%3D+Simpsons(f,+a,+b,+7)%3B%0A++//+Error+is+difference+between+these%0A++double+err+%3D+std::abs(integral_3+-+integral_7)%3B%0A++if+(err+%3C+err_target+%7C%7C+depth+%3E+100)+%7B%0A++++//+if+error+is+small,+or+depth+exceeds+limit,+return+best+guess%0A++++return+integral_7%3B%0A++%7D+else+%7B%0A++++double+m+%3D+(a+%2B+b)+/+2.0%3B++//+mid-point%0A++++//+divide+target+error+by+2,+since+each+domain+is+half+the+size%0A++++//+Increase+depth+counter+as+we+recursively+call+function:%0A++++return+adaptive(f,+a,+m,+err_target+/+2.0,+depth+%2B+1)+%2B%0A+++++++++++adaptive(f,+m,+b,+err_target+/+2.0,+depth+%2B+1)%3B%0A++%7D%0A%7D%0A%0Aint+main()+%7B%0A++//+test:%0A++auto+lambda+%3D+%5B%5D(double+x)+%7B%0A++++return+std::exp(-x)+*+std::sin(15.0+*+x+%2B+0.5)+/+(x+%2B+1.0e-6)%3B%0A++%7D%3B%0A++std::cout+%3C%3C+Simpsons(lambda,+0.0,+1.0,+1001)+%3C%3C+%22%5Cn%22%3B%0A++std::cout+%3C%3C+adaptive(lambda,+0.0,+1.0,+1.0e-6)+%3C%3C+%22%5Cn%22%3B%0A%7D'),l:'5',n:'0',o:'C%2B%2B+source+%232',t:'0')),k:60.4722005188949,l:'4',n:'0',o:'',s:0,t:'0'),(g:!((h:executor,i:(argsPanelShown:'1',compilationPanelShown:'0',compiler:g102,compilerOutShown:'0',execArgs:'',execStdin:'',fontScale:28,fontUsePx:'0',j:1,lang:c%2B%2B,libs:!(),options:'-std%3Dc%2B%2B11+-O3',source:2,stdinPanelShown:'1',wrap:'1'),l:'5',n:'0',o:'x86-64+gcc+10.2+Executor+(Editor+%232)+C%2B%2B',t:'0')),header:(),k:39.5277994811051,l:'4',n:'0',o:'',s:0,t:'0')),l:'2',n:'0',o:'',t:'0')),version:4"></iframe>




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
