Import `stdio`
```c
#include <stdio.h>
```

Print string to console
```c
printf("Hello World!\n");
```
Print values from variables to console
```c
printf("%d %i", myInt, myInt);
printf("%f %F", myFloat, myFloat);
printf("%lf", myDouble)
printf("%c", myChar);
printf("%s", myString);
```
The float specifier uses banker's rounding when formatting floats to a fewer decimal places than is needed to represent the number.
```c
printf("%.0f", 1.5)  // results in 2
printf("%.0f", 2.5)  // also results in 2
```