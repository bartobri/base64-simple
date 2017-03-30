![Version](https://img.shields.io/badge/Version-0.1.0-green.svg)
[![Donate](https://img.shields.io/badge/Tips-PayPal_and_Bitcoin-green.svg)](https://github.com/bartobri/tips)

Base64 Simple
=============

Desc Coming...

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
```
include "base64simple.h"

int main(void) {

    // Coming...
    
    return 0;
}
```

**Functions**

`char base64simple_enc(char *)`

Desc Coming...

`char base64simple_dec(char *)`

Desc Coming...

**Compiling**

You must tell the compiler to include the base64simple library.

```
gcc myprogram.c -lbase64simple
```

License
-------

This program is free software; you can redistribute it and/or modify it under the terms of the the
MIT License (MIT). See [LICENSE](LICENSE) for more details.
