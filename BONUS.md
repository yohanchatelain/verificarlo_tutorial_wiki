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