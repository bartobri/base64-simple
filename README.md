![Version](https://img.shields.io/badge/Version-0.1.0-green.svg)
[![Donate](https://img.shields.io/badge/Tips-PayPal_and_Bitcoin-green.svg)](https://github.com/bartobri/tips)

Base64 Simple
=============

The goal of this project is to provide a dynamically linked library that
makes it dead-simple to encode and decode base64 strings from within your
program code. See the Usage section for more info.

Table of Contents
-----------------

1. [Download and Install](#download-and-install)
2. [Usage](#usage)
3. [License](#license)

Download and Install
--------------------

In order to download and build this library, you will need to have `git`,
`gcc`, and `make` installed. Install them from your package manager if not
already installed.

```
$ which make
/usr/bin/make

$ which gcc
/usr/bin/gcc

$ which git
/usr/bin/git
```

Download and Install:

```
$ git clone https://github.com/bartobri/base64-simple.git
$ cd base64-simple
$ make
$ sudo make install
```

Uninstall:

```
$ sudo make uninstall
```

Usage
-----

**Synopsys**

myprogram.c
```
#include <stdio.h>
#include "base64simple.h"

int main(void) {
	char *decoded;
	char *encoded;
    
	decoded = "This is a decoded string";
    
	// Encoding a character string
	encoded = base64simple_encode(decoded);
	printf("Encoded: %s\n", encoded);
    
	// Decoding a character string
	decoded = base64simple_decode(encoded);
	printf("Decoded: %s\n", decoded);
    
	return 0;
}
```

**Compiling**

You must tell the compiler to include the base64simple library.

```
gcc myprogram.c -lbase64simple
```

**Functions**

`char *base64simple_encode(char *)`

`char *base64simple_decode(char *)`

I've tried t make usage as simple as possible. Each function takes
a pointer to a string and and returns the encoded or decoded version,
also as a pointer to a string. Note that the memory for the return string
is dynamically allocated, so you may wish to free when it is no longer
needed if memory is a concern.

Also note that base64simple_decode() will return a NULL pointer if it
encounters an error when decoding. This only happens when it encounters
an improperly encoded string as input.

License
-------

This program is free software; you can redistribute it and/or modify it under the terms of the the
MIT License (MIT). See [LICENSE](LICENSE) for more details.
