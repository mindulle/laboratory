Package rand
============

-   `import "crypto/rand"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package rand implements a cryptographically secure random number
generator.

Index 
-----

-   [Variables](#pkg-variables)
-   [func Int(rand io.Reader, max \*big.Int) (n \*big.Int, err
    error)](#Int)
-   [func Prime(rand io.Reader, bits int) (\*big.Int, error)](#Prime)
-   [func Read(b \[\]byte) (n int, err error)](#Read)

 
### Examples

[Read](#example_Read)


### Package files

rand.go rand\_getrandom.go rand\_unix.go util.go

Variables 
---------

Reader is a global, shared instance of a cryptographically secure random
number generator.

On Linux, FreeBSD, Dragonfly, NetBSD and Solaris, Reader uses
getrandom(2) if available, /dev/urandom otherwise. On OpenBSD and macOS,
Reader uses getentropy(2). On other Unix-like systems, Reader reads from
/dev/urandom. On Windows systems, Reader uses the ProcessPrng API. On
JS/Wasm, Reader uses the Web Crypto API. On WASIP1/Wasm, Reader uses
random\_get from wasi\_snapshot\_preview1.

```go
var Reader io.Reader
```

func Int 
--------

```go
func Int(rand io.Reader, max *big.Int) (n *big.Int, err error)
```

Int returns a uniform random value in \[0, max). It panics if max \<= 0.

func Prime 
----------

```go
func Prime(rand io.Reader, bits int) (*big.Int, error)
```

Prime returns a number of the given bit length that is prime with high
probability. Prime will return error for any error returned by rand.Read
or if bits \< 2.

func Read 
---------

```go
func Read(b []byte) (n int, err error)
```

Read is a helper function that calls Reader.Read using io.ReadFull. On
return, n == len(b) if and only if err == nil.

#### [Example]

This example reads 10 cryptographically secure pseudorandom numbers from
rand.Reader and writes them to a byte slice.

Code:

```go
c := 10
b := make([]byte, c)
_, err := rand.Read(b)
if err != nil {
    fmt.Println("error:", err)
    return
}
// The slice should now contain random bytes instead of only zeroes.
fmt.Println(bytes.Equal(b, make([]byte, c)))
```

Output:

```go
false
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/crypto/rand/>

