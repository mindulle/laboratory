Package subtle
==============

-   `import "crypto/subtle"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package subtle implements functions that are often useful in
cryptographic code but require careful thought to use correctly.

Index 
-----

-   [func ConstantTimeByteEq(x, y uint8) int](#ConstantTimeByteEq)
-   [func ConstantTimeCompare(x, y \[\]byte) int](#ConstantTimeCompare)
-   [func ConstantTimeCopy(v int, x, y \[\]byte)](#ConstantTimeCopy)
-   [func ConstantTimeEq(x, y int32) int](#ConstantTimeEq)
-   [func ConstantTimeLessOrEq(x, y int) int](#ConstantTimeLessOrEq)
-   [func ConstantTimeSelect(v, x, y int) int](#ConstantTimeSelect)
-   [func XORBytes(dst, x, y \[\]byte) int](#XORBytes)

### Package files

constant\_time.go xor.go xor\_amd64.go

func ConstantTimeByteEq 
-----------------------

```go
func ConstantTimeByteEq(x, y uint8) int
```

ConstantTimeByteEq returns 1 if x == y and 0 otherwise.

func ConstantTimeCompare 
------------------------

```go
func ConstantTimeCompare(x, y []byte) int
```

ConstantTimeCompare returns 1 if the two slices, x and y, have equal
contents and 0 otherwise. The time taken is a function of the length of
the slices and is independent of the contents. If the lengths of x and y
do not match it returns 0 immediately.

func ConstantTimeCopy 
---------------------

```go
func ConstantTimeCopy(v int, x, y []byte)
```

ConstantTimeCopy copies the contents of y into x (a slice of equal
length) if v == 1. If v == 0, x is left unchanged. Its behavior is
undefined if v takes any other value.

func ConstantTimeEq 
-------------------

```go
func ConstantTimeEq(x, y int32) int
```

ConstantTimeEq returns 1 if x == y and 0 otherwise.

func ConstantTimeLessOrEq 
--------------------------------------------------------

```go
func ConstantTimeLessOrEq(x, y int) int
```

ConstantTimeLessOrEq returns 1 if x \<= y and 0 otherwise. Its behavior
is undefined if x or y are negative or \> 2\*\*31 - 1.

func ConstantTimeSelect 
-----------------------

```go
func ConstantTimeSelect(v, x, y int) int
```

ConstantTimeSelect returns x if v == 1 and y if v == 0. Its behavior is
undefined if v takes any other value.

func XORBytes 
----------------------------------------------

```go
func XORBytes(dst, x, y []byte) int
```

XORBytes sets dst\[i\] = x\[i\] \^ y\[i\] for all i \< n = min(len(x),
len(y)), returning n, the number of bytes written to dst. If dst does
not have length at least n, XORBytes panics without writing anything to
dst.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/crypto/subtle/>

