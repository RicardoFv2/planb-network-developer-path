---
tags: [bitcoin-core, compilation, developer-track]
title: Building Bitcoin Core
---

# Building Bitcoin Core from Source

[[index|← Return to Index]]

Building Bitcoin Core directly from the source code rather than downloading a pre-compiled binary is a fundamental skill for developers and serious node operators.

## General Steps

The standard process follows these steps (example for Unix-like systems):

1. **Install Dependencies:** You must install compilers (`gcc` or `clang`), `make`, `autoconf`, `libtool`, and libraries like `boost`, `libevent`, `sqlite3` (for the wallet), etc.
2. **Clone the Repository:** Get the code using `git clone https://github.com/bitcoin/bitcoin.git`.
3. **Autogen:** Run `./autogen.sh` to generate the configure script.
4. **Configure:** Run `./configure`. You can pass flags to customize the build. Common flags:
   - `--without-gui`: Builds only `bitcoind` and command-line tools, stripping out Qt/GUI dependencies, speeding up compilation.
   - `--disable-wallet`: Compiles without wallet support if you only need a routing node or are developing non-wallet features.
5. **Compile:** Run `make` (or `make -j N` where N is the number of CPU cores to parallelize the build).

Building from source allows you to verify what you run and the ability to test new changes manually.

---

[[index|← Return to Index]]
