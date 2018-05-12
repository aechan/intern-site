# Methods

```cpp
#include <stdio.h>

int main() {
    sayHello();
}

void sayHello() {
    printf("Hello");
}
```

In Java, this seems like perfectly valid code, aside from the `#include` statement which we will go over later. The caveat is that the C++ compiler will reject this because when the `sayHello()` method is called on line 4, `sayHello()` had not yet been declared, so the C++ compiler has no idea what it is. To fix this, we can declare the method before using it like in the example below.

```cpp
#include <stdio.h>

void sayHello() {
    printf("Hello");
}

int main() {
    sayHello();
}
```

This will output `Hello` to the terminal successfully because we declared and defined `sayHello()` before using it. But, what if we don't want all our methods defined at the top of the file? In this case we declare a method stub which tells the compiler, "there is a method called `sayHello()` that takes no arguments and returns void", which is enough information for the compiler to allow you to use the method before defining it like we can in Java. The example below shows how to declare a method stub.

```cpp
#include <stdio.h>

void sayHello();

int main() {
    sayHello();
}

void sayHello() {
    printf("Hello");
}
```

This is how to properly declare, define and invoke a method in C++, but the issue is now we'll have a bunch of ugly method stubs polluting the top of the source file. This is where header files come into play.