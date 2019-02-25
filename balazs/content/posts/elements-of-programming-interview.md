---
title: "Tricks for programming questions"
date: 2019-02-15T09:27:09+02:00
draft: true
---

## Primitive types

Primitive types are the fundamental in programming language you use to store
information regarding to your needs. More specifically, in the end, every information
is stored in some composite of primitive types, because whatever fancy structure you will create
in your program, it builds up by using those types.
Further read about this:

 - [1] [Wikipedia](https://en.wikibooks.org/wiki/Java_Programming/Primitive_Types)
 - [2] [GeeksforGeeks](https://www.geeksforgeeks.org/data-types-in-c/)
 - [3] [Java](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html)

### Swap

This question is a bit old, but worth to review it a bit further.
The correct answer for this:

In C:

```C
void swap(int* a, int* b) {
  *a ^= *b;
  *b ^= *a;
  *a ^= *b;
}
```
In Go:

```Go
func swap(a, b *int) {
  *a ^= *b
  *b ^= *a
  *a ^= *b
}
```

The approach uses the XOR operation. One of the property of the XOR operation
is that ```a XOR a``` is equal to 0. Now let ```a = 0011b``` and ```b = 1100b```, then ```c = a XOR b``` will be ```1111b```,
and ```a = c XOR b```, and ```b = c XOR a```. Now let c be a, then
we do not use any further space, and extract the values by using the XOR operation
property.

More references:

 - [1] https://www.geeksforgeeks.org/swap-two-numbers-without-using-temporary-variable/

### Magic

 - [1] ```A(x) = x & (x-1)``` clears the lowest set bit.
 - [2] ```B(x) = x & ~(x-1)``` equals to the lowest set bit

In examples the 5,6,7, and 8 are giving the following results:

```C
A(5) -> 4, A(6) -> 4, A(7) -> 6, A(8) -> 0
B(5) -> 1, B(6) -> 2, B(7) -> 1, B(8) -> 8
```

These are fancy, but in practice you don't use them a lot. Problems involving integers to transform them into a certain format usually requires to go through the bits, however I had a personal experience, where this magic would be useful, but I did not know it.

Couple of years ago, a [scheduling algorithm developed for multiple-tau hardware correlators](https://arxiv.org/abs/1112.1616) involved a problem to determine how many times a number can be divided by two. In the end the base bit transformation I came up with a formula of ```((x ^ (x-1)) + 1) >> 1```, but it is equal to ```x & ~(x-1)```. Things happened. This is why we need to know magics.

### Use lookup tables

Some type of problems often requires to create lookup tables. For an instance reverse bits in integer or calculate the parity of the integer at first glance need to iterate the integer from it's least significant bit to its most significant bit, and it would take 64 iteration in case of the integer has 64 bits length.

### Greatest common division

This is a traditional question on interviews and usually a restriction that you cannot use division or multiplication is given as an extra.
Now, the solution uses [euclidean algorithm](https://en.wikipedia.org/wiki/Euclidean_algorithm), and a faster form of it given in the book [Elements of Programming Interviews](https://www.amazon.com/Elements-Programming-Interviews-Insiders-Guide/dp/1479274836) written in Go looks like this:

```Go
func gcd(x, y int) int {
  if (x == 0) {
    return y
  } else if (y == 0) {
    return x
  } else if ((x & 1) == 0 && (y & 1) == 0) {
    return gcd(x >> 1, y >> 1) << 1
  } else if ((x & 1) == 0 && (y & 1) == 1)  {
    return gcd(x >> 1, y)
  } else if ((x & 1) == 1 && (y & 1) == 0)  {
    return gcd(x, y >> 1)
  } else if (x < y) {
    return gcd(x, y - x)
  }
  return gcd(x - y, y)
}
```

## Arrays
