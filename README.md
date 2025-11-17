# clsUtil

[![Repo Size](https://img.shields.io/badge/repo-ready-blue)](https://github.com/)
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)]

A comprehensive C++ utility class providing a wide range of helper functions for random number generation, array manipulations, string encryption/decryption, and numeric to text conversion. Designed for use in Visual Studio Community 2022 but compatible with modern C++ compilers.

---

## Table of Contents

* [Features](#features)
* [Prerequisites](#prerequisites)
* [Installation](#installation)
* [Quick Usage](#quick-usage)
* [API Reference](#api-reference)
* [Examples](#examples)
* [Contributing](#contributing)
* [License](#license)

---

## Features

* Random number generation and character generation (small letters, capital letters, digits, special characters, mixed).
* Random word and key generation.
* Array helpers: fill, shuffle, sum, average, copy, reverse, find, count, prime checking, palindrome check.
* String encryption and decryption with a simple shift cipher.
* Numeric to English text conversion.
* Swap helpers for int, double, string, and custom `clsDate` objects.

---

## Prerequisites

* Visual Studio Community 2022 (recommended)
* C++11 or newer
* `clsDate.h` and `Global.h` available in the project

---

## Installation

1. Copy `clsUtil.h` to your project directory.
2. Add the file to your project in Visual Studio: right-click project → Add → Existing Item → select `clsUtil.h`.
3. Ensure `clsDate.h` and `Global.h` are accessible.

---

## Quick Usage

```cpp
#include <iostream>
#include "clsUtil.h"
using namespace std;

int main() {
    clsUtil::Srand(); // initialize random seed

    cout << "Random number (1-100): " << clsUtil::RandomNumber(1, 100) << endl;

    string key = clsUtil::GenerateKey(clsUtil::enCharType::Mix);
    cout << "Generated key: " << key << endl;

    int arr[5];
    clsUtil::FillArrayWithRandomNumbers(arr, 5, 0, 50);
    clsUtil::PrintArrayElements(arr, 5);

    cout << "Number to text: " << clsUtil::NumberToText(12345) << endl;

    return 0;
}
```

---

## API Reference

### Random Generation

* `static void Srand()` — Initialize random seed.
* `static int RandomNumber(int From, int To)` — Returns random number in range.
* `enum enCharType { SmallLetter, CapitalLetter, SpecialCharacter, Digit, Mix }`
* `static char GetRandomCharacter(const enCharType& CharType)`
* `static string GenerateWord(const enCharType& CharType, short WordLength)`
* `static string GenerateKey(const enCharType& CharType)`
* `static void GenerateKeys(short NumberOfKeys, const enCharType& CharType)`

### Array Utilities

* Fill, copy, shuffle arrays of int, double, string.
* Count positive, negative, odd, even numbers.
* Check primes and extract to arrays.
* Sum and average of numbers.
* Swap elements.
* Reverse arrays.
* Check palindrome arrays.
* Count occurrences.
* Find positions.
* Copy odd numbers.
* Get number type (Odd/Even).

### String Utilities

* `static string EncryptText(string Text, short EncryptionKey)`
* `static string DecryptText(string Text, short EncryptionKey)`
* `static string Tabs(short HowManyTabs)`

### Numeric Conversion

* `static string NumberToText(int Number)` — Converts integer numbers to English words.

---

## Examples

### Generate Random Keys

```cpp
clsUtil::Srand();
clsUtil::GenerateKeys(5, clsUtil::enCharType::Mix);
```

### Array Manipulations

```cpp
int arr[5];
clsUtil::FillArrayWithRandomNumbers(arr, 5, 1, 100);
clsUtil::ShuffleArray(arr, 5);
clsUtil::PrintArrayElements(arr, 5);
```

### Encrypt and Decrypt Text

```cpp
string secret = "HelloWorld";
string encrypted = clsUtil::EncryptText(secret, 5);
string decrypted = clsUtil::DecryptText(encrypted, 5);
```

### Number to Text

```cpp
cout << clsUtil::NumberToText(1234567) << endl;
// Output: One Million Two Hundred Thirty Four Thousands Five Hundred Sixty Seven
```

---

## Contributing

Contributions, bug fixes, and feature requests are welcome. Open an issue or submit a pull request with details and test cases.

---

## License

This project is licensed under MIT License. See the LICENSE file for details.
