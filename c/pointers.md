# Pointers

A pointer is a __reference__ to a value. **Pointers** points to another value 
stored elsewhere such as variables or arrays. The pointers actual value is a 
__memory address__. To get the value of the reference variable, array, or etc 
from a pointer, you must __dereference__ the pointer. Dereferencing a pointer 
means getting the value that is stored in the memory location pointed by the 
pointer. The operator `*` is used to do this, and is called the 
__dereferencing__ operator. To get the memory address of a object, you use 
the __address__ operator which is `&`. Here is an example using pointers:

```c
int i; // define a integer called i
int *p; // define a pointer called p

i = 10; // set i equal to 10
p = &i; // p points to the variable i

// prints out a memory address
printf("%p\n", p); // => 00000001

// prints out a the variable i's value when deferencing
printf("%d\n", *p); // => 10
```

What about arrays and structs? Well an array points to it's first element. 
With this, you can use pointer arithmetic to get other elements in the array.
Now with structs, accessing members of a struct pointer became so common in C 
that there is a special operator for it. It is the `->` operator called the 
arrow operator.

```c
int arr[3]; // define a integer array that contains only 3 elements
int *p1, *p2; // define two pointers

// set these two pointers to the memory address of the first element of arr
// these two statements are basically doing the same thing
p1 = arr;
p2 = &arr[0];

// prints out the memory address of the first element of the array
printf("%p\n", arr); // => 0022FF10
printf("%p\n", p1); // => 0022FF10
printf("%p\n", p2); // => 0022FF10

// loop through array elements and printing their memory addresses
int i;
for (i = 0; i < 3; i++)
  printf("%p ", *(arr + i)); // 00000001 00000002 00000003

// define a Hero struct with attack and defense attributes
struct hero
{
  int attack;
  int defense;
};

// define a struct hero and struct hero pointer
struct hero stevo;
struct hero *heroPtr;

// set heroPtr to point to stevo
heroPtr = &stevo;

// deference the heroPtr to access stevo's attributes (struct members)
(*heroPtr).attack = 10;
heroPtr->defense = 10;

// prints out all the same
printf("attack: %d, defense: %d", stevo.attack, stevo.defense); // => attack: 10, defense: 10
printf("attack: %d, defense: %d", (*heroPtr).attack, (*heroPtr).defense); // => attack: 10, defense: 10
printf("attack: %d, defense: %d", heroPtr->attack, heroPtr->defense); // => attack: 10, defense: 10
```
