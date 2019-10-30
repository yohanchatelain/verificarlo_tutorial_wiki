Example

what is wrong with this program? Use verificarlo to analyse it.

| exercice1.c |
| -------- |
```C
#include <float.h>
#include <stdio.h>

/* Show the dangers of counting with inexact floating point values --   */
/* (accidentally) double gets it `wrong' and float gets it `right'.     */

int main(){
 const double sixth = 1.0/6.0;
 volatile double d;
 volatile float f;
 for (f = 0.0; f < 1.0; f += sixth) printf("Here with float %.7f\n", f);
 for (d = 0.0; d < 1.0; d += sixth) printf("Here with double %.16f\n", d);
 return 0;
}
```



Understand that Verificarlo is intended to helps users to catch how a change on the input(s) and internal operations affects the output. Hence it also helps to determine how input error bars and internal operations become output error bars. 

#
Polynomial evaluation is a common source of computational error. Polynomials are frequently used for function interpolation in libraries or user codes. As we will see, different evaluations of the same polynomial do not have the same behavior in terms of performance or numerical accuracy.

This tutorial uses the Tchebychev polynomial from ~\cite[pp.52-54]{parker1997monte}: