# bint.h
A C++ Wrapper for GMP Arbitrary Precision Library

bint is a custom C++ class that wraps the GMP (GNU Multiple Precision) library to provide intuitive and user-friendly support for arbitrary-precision integers. This class supports arithmetic, bitwise, comparison, and modular operations with both small and large integers, including support for hexadecimal and decimal string inputs.

## Usage Example

```cpp
#include "bint.h"
#include <iostream>

int main() {
    bint a = 0;                  // Default constructor
    bint b = 42;                 // Constructor from int
    bint c = "123456789";       // Constructor from decimal string
    bint d = "0x1a2b3c";       // Constructor from hex string

    std::cout << "b + c = " << (b + c) << std::endl;
    std::cout << "c - b = " << (c - b) << std::endl;
    std::cout << "b * d = " << (b * d) << std::endl;
    std::cout << "c / b = " << (c / b) << std::endl;
    std::cout << "c % b = " << (c % b) << std::endl;

    bint largeDec = "1234567890123456789012345678901234567890";
    bint largeHex = "0xffffffffffffffffffffffffffffffffffffffff";
    std::cout << "largeDec + largeHex = " << (largeDec + largeHex) << std::endl;
    std::cout << "Modular inverse of 123456789 mod 1000000007 = " << bint(123456789).modInverse(1000000007) << std::endl;

    return 0;
}
```

Compile and run:
```sh
g++ -std=c++17 main.cpp -lgmp -lgmpxx -o main
./main
```

This example demonstrates arithmetic, bitwise, and modular operations using the bint class.

