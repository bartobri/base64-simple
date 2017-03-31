![Version](https://img.shields.io/badge/Version-0.1.0-green.svg)
[![Donate](https://img.shields.io/badge/Tips-PayPal_and_Bitcoin-green.svg)](https://github.com/bartobri/tips)

Base64 Simple
=============

The goal of this project is to provide a dynamically linked library that
makes it dead-simple to encode and decode base64 strings from within your
program code. See the Usage section for more info.

**NOTE:** This library only works with null-terminated strings. If you wish
to encode/decode data that includes null characters, this library is not
for you.

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
#include <string.h>
#include "base64simple.h"

int main(void) {
	char *decoded, *encoded;
	size_t len;

	decoded = "This is a decoded string.";
	len = strlen(decoded);

	// Encoding
	encoded = base64simple_encode(decoded, len);
	if (encoded == NULL) {
		printf("Insufficient Memory!\n");
	} else {
		printf("Encoded: %s\n", encoded);
	}

	// Decoding
	size = strlen(encoded);
	decoded = base64simple_decode(encoded, size, &r_size);
	printf("Decoded string length: %d\n", r_size);

	return 0;
}
```

**Compiling**

You must tell the compiler to include the base64simple library.

```
gcc myprogram.c -lbase64simple
```

**Functions**

`char *base64simple_encode(char *s, size_t n)`

The base64simple_encode() function encodes the first **n** bytes of the
character string pointed to by **s**. It returns a pointer to a null-terminated
string containing the encoded result. A null poointer is returned if there
is insufficient memory for the encoded string.

`char *base64simple_decode(char *s, size_t n, size_t *x)`

The base64simple_decode() function decodes the first **n** bytes of the
character string pointed to by **s** (unless it encounters the base64
end-of-stream signature before that). It returns a pointer to an unsigned
character string containing the decoded result, and it assigns the length
of the decoded string to **x**. Note that this string is *NOT* null
terminated, so you must use the value of **x** to examine the contents
without encountering an out-of-bounds error. A null pointer is returned if **s**
is not properly encoded, or if there is insufficient memory for the decoded
string.

License
-------

This program is free software; you can redistribute it and/or modify it under the terms of the the
MIT License (MIT). See [LICENSE](LICENSE) for more details.
