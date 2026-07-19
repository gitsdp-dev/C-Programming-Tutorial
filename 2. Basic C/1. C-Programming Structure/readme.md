# C Programming Basic Structure:
You have successfully setup your environment and read the common errors for compilation, execution and linking very carefully. You will understand the *Common Errors* section when you start your programming yourself. These errors are written according to my own experience in C 😄. 

## Structure of a Basic C Program:
```c
/* ============================================================
   1. DOCUMENTATION SECTION
   Program: Calculate Area of a Circle
   ============================================================ */

/* 2. LINK SECTION */
#include <stdio.h>

/* 3. DEFINITION SECTION */
#define PI 3.14159

/* 4. GLOBAL DECLARATION SECTION */
float calculateArea(float radius);

/* 5. MAIN FUNCTION SECTION */
main()
{
    float radius = 5.0;   // Local variable declaration
    float area;

    area = calculateArea(radius);   // Function execution

    printf("The area is: %.2f\n", area);

    return 0;   // Return statement signaling successful exit
}

/* 6. SUBPROGRAM SECTION (SECTION TO ADD USER-DEFINED FUNCTIONS) */
float calculateArea(float radius)
{
    return PI * radius * radius;
}
```