Package list
============

-   `import "container/list"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package list implements a doubly linked list.

To iterate over a list (where l is a \*List):

```go
for e := l.Front(); e != nil; e = e.Next() {
    // do something with e.Value
}
```

#### [Example]

Code:

```go
// Create a new list and put some numbers in it.
l := list.New()
e4 := l.PushBack(4)
e1 := l.PushFront(1)
l.InsertBefore(3, e4)
l.InsertAfter(2, e1)

// Iterate through list and print its contents.
for e := l.Front(); e != nil; e = e.Next() {
    fmt.Println(e.Value)
}
```

Output:

```go
1
2
3
4
```

Index 
-----

-   [type Element](#Element)
-   [func (e \*Element) Next() \*Element](#Element.Next)
-   [func (e \*Element) Prev() \*Element](#Element.Prev)
-   [type List](#List)
-   [func New() \*List](#New)
-   [func (l \*List) Back() \*Element](#List.Back)
-   [func (l \*List) Front() \*Element](#List.Front)
-   [func (l \*List) Init() \*List](#List.Init)
-   [func (l \*List) InsertAfter(v any, mark \*Element)
    \*Element](#List.InsertAfter)
-   [func (l \*List) InsertBefore(v any, mark \*Element)
    \*Element](#List.InsertBefore)
-   [func (l \*List) Len() int](#List.Len)
-   [func (l \*List) MoveAfter(e, mark \*Element)](#List.MoveAfter)
-   [func (l \*List) MoveBefore(e, mark \*Element)](#List.MoveBefore)
-   [func (l \*List) MoveToBack(e \*Element)](#List.MoveToBack)
-   [func (l \*List) MoveToFront(e \*Element)](#List.MoveToFront)
-   [func (l \*List) PushBack(v any) \*Element](#List.PushBack)
-   [func (l \*List) PushBackList(other \*List)](#List.PushBackList)
-   [func (l \*List) PushFront(v any) \*Element](#List.PushFront)
-   [func (l \*List) PushFrontList(other \*List)](#List.PushFrontList)
-   [func (l \*List) Remove(e \*Element) any](#List.Remove)

 
### Examples

[Package](#example_)


### Package files

list.go

type Element 
------------

Element is an element of a linked list.

```go
type Element struct {

    // The value stored with this element.
    Value any
    // contains filtered or unexported fields
}
```

### func (\*Element) Next 

```go
func (e *Element) Next() *Element
```

Next returns the next list element or nil.

### func (\*Element) Prev 

```go
func (e *Element) Prev() *Element
```

Prev returns the previous list element or nil.

type List 
---------

List represents a doubly linked list. The zero value for List is an
empty list ready to use.

```go
type List struct {
    // contains filtered or unexported fields
}
```

### func New 

```go
func New() *List
```

New returns an initialized list.

### func (\*List) Back 

```go
func (l *List) Back() *Element
```

Back returns the last element of list l or nil if the list is empty.

### func (\*List) Front 

```go
func (l *List) Front() *Element
```

Front returns the first element of list l or nil if the list is empty.

### func (\*List) Init 

```go
func (l *List) Init() *List
```

Init initializes or clears list l.

### func (\*List) InsertAfter 

```go
func (l *List) InsertAfter(v any, mark *Element) *Element
```

InsertAfter inserts a new element e with value v immediately after mark
and returns e. If mark is not an element of l, the list is not modified.
The mark must not be nil.

### func (\*List) InsertBefore 

```go
func (l *List) InsertBefore(v any, mark *Element) *Element
```

InsertBefore inserts a new element e with value v immediately before
mark and returns e. If mark is not an element of l, the list is not
modified. The mark must not be nil.

### func (\*List) Len 

```go
func (l *List) Len() int
```

Len returns the number of elements of list l. The complexity is O(1).

### func (\*List) MoveAfter 

```go
func (l *List) MoveAfter(e, mark *Element)
```

MoveAfter moves element e to its new position after mark. If e or mark
is not an element of l, or e == mark, the list is not modified. The
element and mark must not be nil.

### func (\*List) MoveBefore 

```go
func (l *List) MoveBefore(e, mark *Element)
```

MoveBefore moves element e to its new position before mark. If e or mark
is not an element of l, or e == mark, the list is not modified. The
element and mark must not be nil.

### func (\*List) MoveToBack 

```go
func (l *List) MoveToBack(e *Element)
```

MoveToBack moves element e to the back of list l. If e is not an element
of l, the list is not modified. The element must not be nil.

### func (\*List) MoveToFront 

```go
func (l *List) MoveToFront(e *Element)
```

MoveToFront moves element e to the front of list l. If e is not an
element of l, the list is not modified. The element must not be nil.

### func (\*List) PushBack 

```go
func (l *List) PushBack(v any) *Element
```

PushBack inserts a new element e with value v at the back of list l and
returns e.

### func (\*List) PushBackList 

```go
func (l *List) PushBackList(other *List)
```

PushBackList inserts a copy of another list at the back of list l. The
lists l and other may be the same. They must not be nil.

### func (\*List) PushFront 

```go
func (l *List) PushFront(v any) *Element
```

PushFront inserts a new element e with value v at the front of list l
and returns e.

### func (\*List) PushFrontList 

```go
func (l *List) PushFrontList(other *List)
```

PushFrontList inserts a copy of another list at the front of list l. The
lists l and other may be the same. They must not be nil.

### func (\*List) Remove 

```go
func (l *List) Remove(e *Element) any
```

Remove removes e from l if e is an element of list l. It returns the
element value e.Value. The element must not be nil.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/container/list/>

