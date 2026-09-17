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

# Getting Started in C
This lab will be getting used to Code::Blocks, and trying different additions to familiarise yourself with the environment and the syntax.

## printf()
As you have noticed, the initial startup of Code::Blocks has a code template that looks like:

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("Hello world!\n");
    return 0;
}
```

Which shows the baseline structure of a C program. The first 2 lines, which start with <code>#include</code>, are known as the libraries of C. These are a collection of programs and commands that allow us to quickly integrate them into our program. for example, the library <code>stdio.h</code> (standard input output), contains the function <code>printf</code> that is used in the default code.
## Tasks

1. Change the initial code to print your your name
2. add a second printf(), to print your course name
3. what happens if you remove \n from your printf() statement?

# Comments

Comments are an important documentation method to ensure your code is interpretable to other people. Any words after // are ignored by your program.

```c
// A comment
printf("Hello World\n"); // A comment after some code
```

## Inputs and Outputs

With C it is straight forward to input information, as well as output information as we have seen. For this code we have declared an integer with<code>int n;</code>, which is an empty variable that the code can now change.

```c
#include <stdio.h>

int main()
{
    int n; //declare an integer

    printf("Please enter a number: "); // Prompt the user
    scanf("%d", &n); // reading an integer input
    printf("You entered: %d\n", n); // printing an integer output
    return 0;
}
```

Run this code and see what happens. The terminal will wait for a user input before printing it out again. The syntax for <code>%d</code> and <code>&n</code> will be covered in a later lab, but just know %d is to let the program know it is looking for an integer, and <code>&n</code> is to inform the program where to save the entered value.

## Tasks

1.Change the program so that it asks for the users age
2.add a second integer, and ask the user to ask for a second input

tip: make sure the two integers have different names, such as "n" and "m"

3.Look at the code snippets below, without running it, what would you expect to see on the terminal? Run it and see if you are correct.
```c
#include <stdio.h>

int main()
{
    int x = 10;
    printf("%d\n", x);

    x = 25;
    printf("%d\n", x);

    return 0;
}
```

```c
#include <stdio.h>

int main()
{
    int x = 10;
    int y = 300;

    printf("%d\n", x);
    printf("%d\n", x);

    return 0;
}
```