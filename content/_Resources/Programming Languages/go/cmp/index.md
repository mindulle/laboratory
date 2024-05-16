Package cmp
===========

-   `import "cmp"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package cmp provides types and functions related to comparing ordered
values.

Index 
-----

-   [func Compare\[T Ordered\](x, y T) int](#Compare)
-   [func Less\[T Ordered\](x, y T) bool](#Less)
-   [type Ordered](#Ordered)

### Package files

cmp.go

func Compare 
------------

```go
func Compare[T Ordered](x, y T) int
```

Compare returns

```go
-1 if x is less than y,
 0 if x equals y,
+1 if x is greater than y.
```

For floating-point types, a NaN is considered less than any non-NaN, a
NaN is considered equal to a NaN, and -0.0 is equal to 0.0.

func Less 
---------

```go
func Less[T Ordered](x, y T) bool
```

Less reports whether x is less than y. For floating-point types, a NaN
is considered less than any non-NaN, and -0.0 is not less than (is equal
to) 0.0.

type Ordered 
---------------------------------------------

Ordered is a constraint that permits any ordered type: any type that
supports the operators \< \<= \>= \>. If future releases of Go add new
ordered types, this constraint will be modified to include them.

Note that floating-point types may contain NaN (\"not-a-number\")
values. An operator such as == or \< will always report false when
comparing a NaN value with any other value, NaN or not. See the
[Compare](#Compare) function for a consistent way to compare NaN values.

```go
type Ordered interface {
    ~int | ~int8 | ~int16 | ~int32 | ~int64 |
        ~uint | ~uint8 | ~uint16 | ~uint32 | ~uint64 | ~uintptr |
        ~float32 | ~float64 |
        ~string
}
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/cmp/>

