---
hide:
  - navigation # Hides the left navigation sidebar
  - toc        # Hides the right Table of Contents
lightbox: true
---
<style>
  .md-header {
    display: none !important;
  }
</style>

# Variables, Data Types, Libraries, Inputs and Output in C

## Variables and Data Types

Variables refers to the data that will be used by the code in various means. C needs explicitly informing what data type it is storing in each variable, to ensure it can carry out the correct calculations.

| Data Type | Description | Example | Size |
| :---: | :--- | :--- | :---: |
| <code style="color: #005cc5; font-weight: bold;">int</code> | Signed integer (whole numbers) | `int radius = 6;` | 16 or 32 bits |
| <code style="color: #005cc5; font-weight: bold;">char</code> | Single ASCII character or 8-bit integer | `char status = 'A';` | 8 bits (1 byte) |
| <code style="color: #005cc5; font-weight: bold;">float</code> | Single-precision floating-point number | `float voltage = 3.3f;` | 32 bits (4 bytes) |

## Declaring Variables

Similar to the previous lab, where we declared int, we can declare other variables in the same way

```c
#include <stdio.h>

int main()
{
    int age;
    float temperature = 21.5;
    char grade = 'A';

    int age = 25;
    return 0;
}
```
As shown with <code>int</code>, you can declare any variable and assign a value later.

## Output Variables

In C, to output a variable, we will need to use format specifiers. each variable has its own format specifiers.

| Data Type | Format Specifier |
| :---: | :---: |
| <code style="color: #005cc5; font-weight: bold;">int</code> | %d |
| <code style="color: #005cc5; font-weight: bold;">char</code> | %c|
| <code style="color: #005cc5; font-weight: bold;">float</code> | %f |

An example of using a format specifier for a float is shown below:
```c

int main()
{
    float temperature = 21.5;
    printf("Temperature: %f\n", temperature);
    printf("Temperature: %.2f\n", temperature); // two decimal places
    return 0;
}
```

### Task
1. Write a program that can output a character, as well as an integer

2. Write a program that can accept an integer input, and print the integer.

Hint: In Lab 1 we discussed inputs and outputs.

## Basic Operators
Operators allow the program to change the variables given, such as arithmetic and character alteration.

Below is the standard operators

```c
int a = 10;
int b = 3;

printf("Addition: %d\n", a + b);
printf("Subtraction: %d\n", a - b);
printf("Multiplication: %d\n", a * b);
printf("Division: %d\n", a / b);
```

### Exercises

1. Run the above code, are these results correct? Why or why not?
2. What happens if you modify the code to have a and b as type float?
Tip: The printf function will need changed to accept these new numbers correctly.

## Practice

1.Write a program that accepts the radius of a circle and calculate its circumference. Print the circumference to the terminal. (use float variables, give results to 2 decimal places )
<details>
  <summary>Hint</summary>
  <br>
  <p>a.	Create 2 variables: one to store the radius (r) and one for the circumference (circum)</p>

  <p>b.	Use a <code>printf</code> statement to prompt the user to enter the radius of the circle</p>

  <p>c.	Use <code>scanf</code> with %f to store the radius value</p>

  <p>d.	Calculate the circumference (circum = 2*3.142*r)</p>

  <p>e.	Print the circumference to the screen to 2 dp (use %.2f) using a <code>printf</code> statement</p>

  <br>
</details>
2.Expand this program to calculate the area of the circle, and print the area to the terminal
