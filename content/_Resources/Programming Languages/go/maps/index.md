Package maps
============

-   `import "maps"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package maps defines various functions useful with maps of any type.

Index 
-----

-   [func Clone\[M \~map\[K\]V, K comparable, V any\](m M) M](#Clone)
-   [func Copy\[M1 \~map\[K\]V, M2 \~map\[K\]V, K comparable, V
    any\](dst M1, src M2)](#Copy)
-   [func DeleteFunc\[M \~map\[K\]V, K comparable, V any\](m M, del
    func(K, V) bool)](#DeleteFunc)
-   [func Equal\[M1, M2 \~map\[K\]V, K, V comparable\](m1 M1, m2 M2)
    bool](#Equal)
-   [func EqualFunc\[M1 \~map\[K\]V1, M2 \~map\[K\]V2, K comparable, V1,
    V2 any\](m1 M1, m2 M2, eq func(V1, V2) bool) bool](#EqualFunc)

 
### Examples

[DeleteFunc](#example_DeleteFunc)

[EqualFunc](#example_EqualFunc)


### Package files

maps.go

func Clone 
----------

```go
func Clone[M ~map[K]V, K comparable, V any](m M) M
```

Clone returns a copy of m. This is a shallow clone: the new keys and
values are set using ordinary assignment.

func Copy 
---------

```go
func Copy[M1 ~map[K]V, M2 ~map[K]V, K comparable, V any](dst M1, src M2)
```

Copy copies all key/value pairs in src adding them to dst. When a key in
src is already present in dst, the value in dst will be overwritten by
the value associated with the key in src.

func DeleteFunc 
---------------

```go
func DeleteFunc[M ~map[K]V, K comparable, V any](m M, del func(K, V) bool)
```

DeleteFunc deletes any key/value pairs from m for which del returns
true.

#### [Example]

Code:

```go
m := map[string]int{
    "one":   1,
    "two":   2,
    "three": 3,
    "four":  4,
}
maps.DeleteFunc(m, func(k string, v int) bool {
    return v%2 != 0 // delete odd values
})
fmt.Println(m)
```

Output:

```go
map[four:4 two:2]
```

func Equal 
----------

```go
func Equal[M1, M2 ~map[K]V, K, V comparable](m1 M1, m2 M2) bool
```

Equal reports whether two maps contain the same key/value pairs. Values
are compared using ==.

func EqualFunc 
--------------

```go
func EqualFunc[M1 ~map[K]V1, M2 ~map[K]V2, K comparable, V1, V2 any](m1 M1, m2 M2, eq func(V1, V2) bool) bool
```

EqualFunc is like Equal, but compares values using eq. Keys are still
compared with ==.

#### [Example]

Code:

```go
m1 := map[int]string{
    1:    "one",
    10:   "Ten",
    1000: "THOUSAND",
}
m2 := map[int][]byte{
    1:    []byte("One"),
    10:   []byte("Ten"),
    1000: []byte("Thousand"),
}
eq := maps.EqualFunc(m1, m2, func(v1 string, v2 []byte) bool {
    return strings.ToLower(v1) == strings.ToLower(string(v2))
})
fmt.Println(eq)
```

Output:

```go
true
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/maps/>

