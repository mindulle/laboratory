Package ring
============

-   `import "container/ring"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package ring implements operations on circular lists.

Index 
-----

-   [type Ring](#Ring)
-   [func New(n int) \*Ring](#New)
-   [func (r \*Ring) Do(f func(any))](#Ring.Do)
-   [func (r \*Ring) Len() int](#Ring.Len)
-   [func (r \*Ring) Link(s \*Ring) \*Ring](#Ring.Link)
-   [func (r \*Ring) Move(n int) \*Ring](#Ring.Move)
-   [func (r \*Ring) Next() \*Ring](#Ring.Next)
-   [func (r \*Ring) Prev() \*Ring](#Ring.Prev)
-   [func (r \*Ring) Unlink(n int) \*Ring](#Ring.Unlink)

 
### Examples

[Ring.Do](#example_Ring_Do)

[Ring.Len](#example_Ring_Len)

[Ring.Link](#example_Ring_Link)

[Ring.Move](#example_Ring_Move)

[Ring.Next](#example_Ring_Next)

[Ring.Prev](#example_Ring_Prev)

[Ring.Unlink](#example_Ring_Unlink)


### Package files

ring.go

type Ring 
---------

A Ring is an element of a circular list, or ring. Rings do not have a
beginning or end; a pointer to any ring element serves as reference to
the entire ring. Empty rings are represented as nil Ring pointers. The
zero value for a Ring is a one-element ring with a nil Value.

```go
type Ring struct {
    Value any // for use by client; untouched by this library
    // contains filtered or unexported fields
}
```

### func New 

```go
func New(n int) *Ring
```

New creates a ring of n elements.

### func (\*Ring) Do 

```go
func (r *Ring) Do(f func(any))
```

Do calls function f on each element of the ring, in forward order. The
behavior of Do is undefined if f changes \*r.

#### [Example]

Code:

```go
// Create a new ring of size 5
r := ring.New(5)

// Get the length of the ring
n := r.Len()

// Initialize the ring with some integer values
for i := 0; i < n; i++ {
    r.Value = i
    r = r.Next()
}

// Iterate through the ring and print its contents
r.Do(func(p any) {
    fmt.Println(p.(int))
})
```

Output:

```go
0
1
2
3
4
```

### func (\*Ring) Len 

```go
func (r *Ring) Len() int
```

Len computes the number of elements in ring r. It executes in time
proportional to the number of elements.

#### [Example]

Code:

```go
// Create a new ring of size 4
r := ring.New(4)

// Print out its length
fmt.Println(r.Len())
```

Output:

```go
4
```

### func (\*Ring) Link 

```go
func (r *Ring) Link(s *Ring) *Ring
```

Link connects ring r with ring s such that r.Next() becomes s and
returns the original value for r.Next(). r must not be empty.

If r and s point to the same ring, linking them removes the elements
between r and s from the ring. The removed elements form a subring and
the result is a reference to that subring (if no elements were removed,
the result is still the original value for r.Next(), and not nil).

If r and s point to different rings, linking them creates a single ring
with the elements of s inserted after r. The result points to the
element following the last element of s after insertion.

#### [Example]

Code:

```go
// Create two rings, r and s, of size 2
r := ring.New(2)
s := ring.New(2)

// Get the length of the ring
lr := r.Len()
ls := s.Len()

// Initialize r with 0s
for i := 0; i < lr; i++ {
    r.Value = 0
    r = r.Next()
}

// Initialize s with 1s
for j := 0; j < ls; j++ {
    s.Value = 1
    s = s.Next()
}

// Link ring r and ring s
rs := r.Link(s)

// Iterate through the combined ring and print its contents
rs.Do(func(p any) {
    fmt.Println(p.(int))
})
```

Output:

```go
0
0
1
1
```

### func (\*Ring) Move 

```go
func (r *Ring) Move(n int) *Ring
```

Move moves n % r.Len() elements backward (n \< 0) or forward (n \>= 0)
in the ring and returns that ring element. r must not be empty.

#### [Example]

Code:

```go
// Create a new ring of size 5
r := ring.New(5)

// Get the length of the ring
n := r.Len()

// Initialize the ring with some integer values
for i := 0; i < n; i++ {
    r.Value = i
    r = r.Next()
}

// Move the pointer forward by three steps
r = r.Move(3)

// Iterate through the ring and print its contents
r.Do(func(p any) {
    fmt.Println(p.(int))
})
```

Output:

```go
3
4
0
1
2
```

### func (\*Ring) Next 

```go
func (r *Ring) Next() *Ring
```

Next returns the next ring element. r must not be empty.

#### [Example]

Code:

```go
// Create a new ring of size 5
r := ring.New(5)

// Get the length of the ring
n := r.Len()

// Initialize the ring with some integer values
for i := 0; i < n; i++ {
    r.Value = i
    r = r.Next()
}

// Iterate through the ring and print its contents
for j := 0; j < n; j++ {
    fmt.Println(r.Value)
    r = r.Next()
}
```

Output:

```go
0
1
2
3
4
```

### func (\*Ring) Prev 

```go
func (r *Ring) Prev() *Ring
```

Prev returns the previous ring element. r must not be empty.

#### [Example]

Code:

```go
// Create a new ring of size 5
r := ring.New(5)

// Get the length of the ring
n := r.Len()

// Initialize the ring with some integer values
for i := 0; i < n; i++ {
    r.Value = i
    r = r.Next()
}

// Iterate through the ring backwards and print its contents
for j := 0; j < n; j++ {
    r = r.Prev()
    fmt.Println(r.Value)
}
```

Output:

```go
4
3
2
1
0
```

### func (\*Ring) Unlink 

```go
func (r *Ring) Unlink(n int) *Ring
```

Unlink removes n % r.Len() elements from the ring r, starting at
r.Next(). If n % r.Len() == 0, r remains unchanged. The result is the
removed subring. r must not be empty.

#### [Example]

Code:

```go
// Create a new ring of size 6
r := ring.New(6)

// Get the length of the ring
n := r.Len()

// Initialize the ring with some integer values
for i := 0; i < n; i++ {
    r.Value = i
    r = r.Next()
}

// Unlink three elements from r, starting from r.Next()
r.Unlink(3)

// Iterate through the remaining ring and print its contents
r.Do(func(p any) {
    fmt.Println(p.(int))
})
```

Output:

```go
0
4
5
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/container/ring/>

