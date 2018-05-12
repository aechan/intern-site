# Pointers

Pointers are the big difference between Java and C++. While pointers are technically in Java, they aren't really a tool that's available to the progammer to use at will like they are in C++.

A pointer is simply a variable that stores the memory address of some data.

```cpp
// an integer a has been allocated
// and given the value 10
int a;
a = 10;

// we now allocate an int pointer pa
// the int* notation simply tells us
// that this is a pointer type that points
// to an integer.
int* pa;

// here we use the dereference operator & to
// get the memory address of a and store that
// in our pointer pa.
pa = &a;
```

Hopefully this example should clarify the syntax of pointers a bit clearer. Now let's do something a bit more complicated with pointers.

```cpp
// declare two ints and assign them values
int a, b;
a = 10;
b = 20;

// declare two int pointers and assign them
// the addresses of our two ints
int* pa, pb;
pa = &a;
pa = &b;

// now the challenge is, to change the value of a without
// ever using the variable a.
// here's how
(*pa)++;
// now a = 11
// the * operator when used on a pointer dereferences the pointer
// allowing us to directly access the value at that memory address
// in this case we are accessing the value stored at &a aka a itself.
```

This example is definitely more complex. To break it down, we introduce two new operators here, the * pointer dereference operator and the & dereference operator (aka "address of" operator).