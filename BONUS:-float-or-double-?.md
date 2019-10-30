When dealing with floating-point numbers, a common trick is :"if it doesn't work with float then use double !"

Exercice:
What is the expected output of this program ? Then compile it with gcc and determine if double is better than float ? 
try again with `inc=1/11` ?


| increment.c |
| -------- |
```C
#include <float.h>
#include <stdio.h>

int main(){
 int i;
 const double inc = 1.0/11.0;
 volatile double d;
 volatile float f;
 for (f = 0.0, i=0; f < 1.0; f += inc, i++) printf("%2d: Float  %.7f\n",i, f);
 for (d = 0.0, i=0; d < 1.0; d += inc, i++) printf("%2d: Double %.16f\n",i, d);
 return 0;
}

```



#
Polynomial evaluation is a common source of computational error. Polynomials are frequently used for function interpolation in libraries or user codes. As we will see, different evaluations of the same polynomial do not have the same behavior in terms of performance or numerical accuracy.

This tutorial uses the Tchebychev polynomial from ~\cite[pp.52-54]{parker1997monte}: