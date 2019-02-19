# EXAM REVIEW

## Unit 1

### C program structure

1. variables/types

- char: single charcater
- int: single digit value 0-9
- float: single-precision floating point value (7 decimal digits)
- double; double-precision floating point value (15 decimal digits)
- void: Absence of type

3. loops

- For loops will run while the middle statement is satisfied.
```c
for(int i = 0; i < 10; i ++){
//CODE
}
```
- While loops work similarly, except only has a single argument.
```c
while(i < 10){
//CODE
}
```


4. conditionals

- Comparison Operators: ==, >=, <=, != same as many other languages

- Logical Operators: 
- ||: Logical or
- &&: Logical and
- !: Logical not

5. main()

The main() function is where the program starts. Code will be executed from here first.

6. printf()

- %d: Prints a decimal (integer) numer
- %f: Prints a floating point number
```c
printf("&1.1f", float_number);
//This will specify the width and precision when printing the float.

//For example: the following will print the float with 4 total width, and a precision of 2 after the dot.
printf("&4.2f", float_numer);
```
- %c: Prints a single character
- %s: Prints a string
- %g: Prints a floating point number using scientific notation
- %p: Prints a pointer (formatted as a hexadecmal value)


## Unit 2

### Memory model

1. Declaring variables

when declaring a variable such as  
```c
int x = 4;
```

A location in memory is reserved, to store integers, and is tagged with the name 'X'

Arrays and such will reserve many boxes in memory consecutively.

Once a memory box has been reserved for a specific type, it cannot be changed.

2. Assigning values to variables/Variables inside functions

When assigning variables inside functions, they are local to that function.

for example

```c
#include<stdio.h>
//this variable can be accessed by any function without passing through.
int x = 2;

int main(){
//this variable can only be accessed by main() unless passed through
  int y = 5;
  return 0;
}
```

Usage:

```c
#include<stdio.h>
int x;

//this function doesn't take an input, simply squares the global variable "x".
int square()
{
  x=x*x;
}

int main()
{
  x = 5;
  square();
   printf("The final value of x is %d\n",x);
}
```

3. TypeCasting

- TypeCasting does not round the numbers

```c
#include<stdio.h>

int main(){
  int x;
  // Implicit TypeCasting
  x = 3/2;
  
  //Explicit TypeCasting
  x = (int) 5/3
  return 0;
}
```


4. Arrays, how they operate inside memory

When declaring an Array of any size in c, the declaration variable automatically becomes the pointer to the first item.

```c
int x[3] = {1,2,3};
printf("%d", *x);
//This will yield 1.
```

Strings behave in a similar way.

## Unit 3

### Compound data types

We never want to pass compound data types by value, instead we use pointers. 

### Linked Lists
```c
#include<stdio.h>

typedef struct car {

} car;

const int max_cars = 4;

void printlist(){
  printf("print");
}

void addcar(){
  printf("print");
}

int main(){
  cars car[max_cars];
  int carnum = 0;
}

```
