Package slices
==============

-   `import "slices"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package slices defines various functions useful with slices of any type.

Index 
-----

-   [func BinarySearch\[S \~\[\]E, E cmp.Ordered\](x S, target E) (int,
    bool)](#BinarySearch)
-   [func BinarySearchFunc\[S \~\[\]E, E, T any\](x S, target T, cmp
    func(E, T) int) (int, bool)](#BinarySearchFunc)
-   [func Clip\[S \~\[\]E, E any\](s S) S](#Clip)
-   [func Clone\[S \~\[\]E, E any\](s S) S](#Clone)
-   [func Compact\[S \~\[\]E, E comparable\](s S) S](#Compact)
-   [func CompactFunc\[S \~\[\]E, E any\](s S, eq func(E, E) bool)
    S](#CompactFunc)
-   [func Compare\[S \~\[\]E, E cmp.Ordered\](s1, s2 S) int](#Compare)
-   [func CompareFunc\[S1 \~\[\]E1, S2 \~\[\]E2, E1, E2 any\](s1 S1, s2
    S2, cmp func(E1, E2) int) int](#CompareFunc)
-   [func Contains\[S \~\[\]E, E comparable\](s S, v E) bool](#Contains)
-   [func ContainsFunc\[S \~\[\]E, E any\](s S, f func(E) bool)
    bool](#ContainsFunc)
-   [func Delete\[S \~\[\]E, E any\](s S, i, j int) S](#Delete)
-   [func DeleteFunc\[S \~\[\]E, E any\](s S, del func(E) bool)
    S](#DeleteFunc)
-   [func Equal\[S \~\[\]E, E comparable\](s1, s2 S) bool](#Equal)
-   [func EqualFunc\[S1 \~\[\]E1, S2 \~\[\]E2, E1, E2 any\](s1 S1, s2
    S2, eq func(E1, E2) bool) bool](#EqualFunc)
-   [func Grow\[S \~\[\]E, E any\](s S, n int) S](#Grow)
-   [func Index\[S \~\[\]E, E comparable\](s S, v E) int](#Index)
-   [func IndexFunc\[S \~\[\]E, E any\](s S, f func(E) bool)
    int](#IndexFunc)
-   [func Insert\[S \~\[\]E, E any\](s S, i int, v \...E) S](#Insert)
-   [func IsSorted\[S \~\[\]E, E cmp.Ordered\](x S) bool](#IsSorted)
-   [func IsSortedFunc\[S \~\[\]E, E any\](x S, cmp func(a, b E) int)
    bool](#IsSortedFunc)
-   [func Max\[S \~\[\]E, E cmp.Ordered\](x S) E](#Max)
-   [func MaxFunc\[S \~\[\]E, E any\](x S, cmp func(a, b E) int)
    E](#MaxFunc)
-   [func Min\[S \~\[\]E, E cmp.Ordered\](x S) E](#Min)
-   [func MinFunc\[S \~\[\]E, E any\](x S, cmp func(a, b E) int)
    E](#MinFunc)
-   [func Replace\[S \~\[\]E, E any\](s S, i, j int, v \...E)
    S](#Replace)
-   [func Reverse\[S \~\[\]E, E any\](s S)](#Reverse)
-   [func Sort\[S \~\[\]E, E cmp.Ordered\](x S)](#Sort)
-   [func SortFunc\[S \~\[\]E, E any\](x S, cmp func(a, b E)
    int)](#SortFunc)
-   [func SortStableFunc\[S \~\[\]E, E any\](x S, cmp func(a, b E)
    int)](#SortStableFunc)

 
### Examples

[BinarySearch](#example_BinarySearch)

[BinarySearchFunc](#example_BinarySearchFunc)

[Compact](#example_Compact)

[CompactFunc](#example_CompactFunc)

[Compare](#example_Compare)

[CompareFunc](#example_CompareFunc)

[ContainsFunc](#example_ContainsFunc)

[Delete](#example_Delete)

[DeleteFunc](#example_DeleteFunc)

[Equal](#example_Equal)

[EqualFunc](#example_EqualFunc)

[Index](#example_Index)

[IndexFunc](#example_IndexFunc)

[Insert](#example_Insert)

[IsSorted](#example_IsSorted)

[IsSortedFunc](#example_IsSortedFunc)

[Max](#example_Max)

[MaxFunc](#example_MaxFunc)

[Min](#example_Min)

[MinFunc](#example_MinFunc)

[Replace](#example_Replace)

[Reverse](#example_Reverse)

[Sort](#example_Sort)

[SortFunc
(CaseInsensitive)](#example_SortFunc_caseInsensitive)

[SortFunc (MultiField)](#example_SortFunc_multiField)

[SortStableFunc](#example_SortStableFunc)


### Package files

slices.go sort.go zsortanyfunc.go zsortordered.go

func BinarySearch 
-----------------

```go
func BinarySearch[S ~[]E, E cmp.Ordered](x S, target E) (int, bool)
```

BinarySearch searches for target in a sorted slice and returns the
position where target is found, or the position where target would
appear in the sort order; it also returns a bool saying whether the
target is really found in the slice. The slice must be sorted in
increasing order.

#### [Example]

Code:

```go
names := []string{"Alice", "Bob", "Vera"}
n, found := slices.BinarySearch(names, "Vera")
fmt.Println("Vera:", n, found)
n, found = slices.BinarySearch(names, "Bill")
fmt.Println("Bill:", n, found)
```

Output:

```go
Vera: 2 true
Bill: 1 false
```

func BinarySearchFunc 
---------------------

```go
func BinarySearchFunc[S ~[]E, E, T any](x S, target T, cmp func(E, T) int) (int, bool)
```

BinarySearchFunc works like [BinarySearch](#BinarySearch), but uses a
custom comparison function. The slice must be sorted in increasing
order, where \"increasing\" is defined by cmp. cmp should return 0 if
the slice element matches the target, a negative number if the slice
element precedes the target, or a positive number if the slice element
follows the target. cmp must implement the same ordering as the slice,
such that if cmp(a, t) \< 0 and cmp(b, t) \>= 0, then a must precede b
in the slice.

#### [Example]

Code:

```go
type Person struct {
    Name string
    Age  int
}
people := []Person{
    {"Alice", 55},
    {"Bob", 24},
    {"Gopher", 13},
}
n, found := slices.BinarySearchFunc(people, Person{"Bob", 0}, func(a, b Person) int {
    return cmp.Compare(a.Name, b.Name)
})
fmt.Println("Bob:", n, found)
```

Output:

```go
Bob: 1 true
```

func Clip 
---------

```go
func Clip[S ~[]E, E any](s S) S
```

Clip removes unused capacity from the slice, returning
s\[:len(s):len(s)\].

func Clone 
----------

```go
func Clone[S ~[]E, E any](s S) S
```

Clone returns a copy of the slice. The elements are copied using
assignment, so this is a shallow clone.

func Compact 
------------

```go
func Compact[S ~[]E, E comparable](s S) S
```

Compact replaces consecutive runs of equal elements with a single copy.
This is like the uniq command found on Unix. Compact modifies the
contents of the slice s and returns the modified slice, which may have a
smaller length. When Compact discards m elements in total, it might not
modify the elements s\[len(s)-m:len(s)\]. If those elements contain
pointers you might consider zeroing those elements so that objects they
reference can be garbage collected.

#### [Example]

Code:

```go
seq := []int{0, 1, 1, 2, 3, 5, 8}
seq = slices.Compact(seq)
fmt.Println(seq)
```

Output:

```go
[0 1 2 3 5 8]
```

func CompactFunc 
----------------

```go
func CompactFunc[S ~[]E, E any](s S, eq func(E, E) bool) S
```

CompactFunc is like [Compact](#Compact) but uses an equality function to
compare elements. For runs of elements that compare equal, CompactFunc
keeps the first one.

#### [Example]

Code:

```go
names := []string{"bob", "Bob", "alice", "Vera", "VERA"}
names = slices.CompactFunc(names, func(a, b string) bool {
    return strings.ToLower(a) == strings.ToLower(b)
})
fmt.Println(names)
```

Output:

```go
[bob alice Vera]
```

func Compare 
------------

```go
func Compare[S ~[]E, E cmp.Ordered](s1, s2 S) int
```

Compare compares the elements of s1 and s2, using cmp.Compare on each
pair of elements. The elements are compared sequentially, starting at
index 0, until one element is not equal to the other. The result of
comparing the first non-matching elements is returned. If both slices
are equal until one of them ends, the shorter slice is considered less
than the longer one. The result is 0 if s1 == s2, -1 if s1 \< s2, and +1
if s1 \> s2.

#### [Example]

Code:

```go
names := []string{"Alice", "Bob", "Vera"}
fmt.Println("Equal:", slices.Compare(names, []string{"Alice", "Bob", "Vera"}))
fmt.Println("V < X:", slices.Compare(names, []string{"Alice", "Bob", "Xena"}))
fmt.Println("V > C:", slices.Compare(names, []string{"Alice", "Bob", "Cat"}))
fmt.Println("3 > 2:", slices.Compare(names, []string{"Alice", "Bob"}))
```

Output:

```go
Equal: 0
V < X: -1
V > C: 1
3 > 2: 1
```

func CompareFunc 
----------------

```go
func CompareFunc[S1 ~[]E1, S2 ~[]E2, E1, E2 any](s1 S1, s2 S2, cmp func(E1, E2) int) int
```

CompareFunc is like [Compare](#Compare) but uses a custom comparison
function on each pair of elements. The result is the first non-zero
result of cmp; if cmp always returns 0 the result is 0 if len(s1) ==
len(s2), -1 if len(s1) \< len(s2), and +1 if len(s1) \> len(s2).

#### [Example]

Code:

```go
numbers := []int{0, 43, 8}
strings := []string{"0", "0", "8"}
result := slices.CompareFunc(numbers, strings, func(n int, s string) int {
    sn, err := strconv.Atoi(s)
    if err != nil {
        return 1
    }
    return cmp.Compare(n, sn)
})
fmt.Println(result)
```

Output:

```go
1
```

func Contains 
-------------

```go
func Contains[S ~[]E, E comparable](s S, v E) bool
```

Contains reports whether v is present in s.

func ContainsFunc 
-----------------

```go
func ContainsFunc[S ~[]E, E any](s S, f func(E) bool) bool
```

ContainsFunc reports whether at least one element e of s satisfies f(e).

#### [Example]

Code:

```go
numbers := []int{0, 42, -10, 8}
hasNegative := slices.ContainsFunc(numbers, func(n int) bool {
    return n < 0
})
fmt.Println("Has a negative:", hasNegative)
hasOdd := slices.ContainsFunc(numbers, func(n int) bool {
    return n%2 != 0
})
fmt.Println("Has an odd number:", hasOdd)
```

Output:

```go
Has a negative: true
Has an odd number: false
```

func Delete 
-----------

```go
func Delete[S ~[]E, E any](s S, i, j int) S
```

Delete removes the elements s\[i:j\] from s, returning the modified
slice. Delete panics if s\[i:j\] is not a valid slice of s. Delete is
O(len(s)-j), so if many items must be deleted, it is better to make a
single call deleting them all together than to delete one at a time.
Delete might not modify the elements s\[len(s)-(j-i):len(s)\]. If those
elements contain pointers you might consider zeroing those elements so
that objects they reference can be garbage collected.

#### [Example]

Code:

```go
letters := []string{"a", "b", "c", "d", "e"}
letters = slices.Delete(letters, 1, 4)
fmt.Println(letters)
```

Output:

```go
[a e]
```

func DeleteFunc 
---------------

```go
func DeleteFunc[S ~[]E, E any](s S, del func(E) bool) S
```

DeleteFunc removes any elements from s for which del returns true,
returning the modified slice. When DeleteFunc removes m elements, it
might not modify the elements s\[len(s)-m:len(s)\]. If those elements
contain pointers you might consider zeroing those elements so that
objects they reference can be garbage collected.

#### [Example]

Code:

```go
seq := []int{0, 1, 1, 2, 3, 5, 8}
seq = slices.DeleteFunc(seq, func(n int) bool {
    return n%2 != 0 // delete the odd numbers
})
fmt.Println(seq)
```

Output:

```go
[0 2 8]
```

func Equal 
----------

```go
func Equal[S ~[]E, E comparable](s1, s2 S) bool
```

Equal reports whether two slices are equal: the same length and all
elements equal. If the lengths are different, Equal returns false.
Otherwise, the elements are compared in increasing index order, and the
comparison stops at the first unequal pair. Floating point NaNs are not
considered equal.

#### [Example]

Code:

```go
numbers := []int{0, 42, 8}
fmt.Println(slices.Equal(numbers, []int{0, 42, 8}))
fmt.Println(slices.Equal(numbers, []int{10}))
```

Output:

```go
true
false
```

func EqualFunc 
--------------

```go
func EqualFunc[S1 ~[]E1, S2 ~[]E2, E1, E2 any](s1 S1, s2 S2, eq func(E1, E2) bool) bool
```

EqualFunc reports whether two slices are equal using an equality
function on each pair of elements. If the lengths are different,
EqualFunc returns false. Otherwise, the elements are compared in
increasing index order, and the comparison stops at the first index for
which eq returns false.

#### [Example]

Code:

```go
numbers := []int{0, 42, 8}
strings := []string{"000", "42", "0o10"}
equal := slices.EqualFunc(numbers, strings, func(n int, s string) bool {
    sn, err := strconv.ParseInt(s, 0, 64)
    if err != nil {
        return false
    }
    return n == int(sn)
})
fmt.Println(equal)
```

Output:

```go
true
```

func Grow 
---------

```go
func Grow[S ~[]E, E any](s S, n int) S
```

Grow increases the slice\'s capacity, if necessary, to guarantee space
for another n elements. After Grow(n), at least n elements can be
appended to the slice without another allocation. If n is negative or
too large to allocate the memory, Grow panics.

func Index 
----------

```go
func Index[S ~[]E, E comparable](s S, v E) int
```

Index returns the index of the first occurrence of v in s, or -1 if not
present.

#### [Example]

Code:

```go
numbers := []int{0, 42, 8}
fmt.Println(slices.Index(numbers, 8))
fmt.Println(slices.Index(numbers, 7))
```

Output:

```go
2
-1
```

func IndexFunc 
--------------

```go
func IndexFunc[S ~[]E, E any](s S, f func(E) bool) int
```

IndexFunc returns the first index i satisfying f(s\[i\]), or -1 if none
do.

#### [Example]

Code:

```go
numbers := []int{0, 42, -10, 8}
i := slices.IndexFunc(numbers, func(n int) bool {
    return n < 0
})
fmt.Println("First negative at index", i)
```

Output:

```go
First negative at index 2
```

func Insert 
-----------

```go
func Insert[S ~[]E, E any](s S, i int, v ...E) S
```

Insert inserts the values v\... into s at index i, returning the
modified slice. The elements at s\[i:\] are shifted up to make room. In
the returned slice r, r\[i\] == v\[0\], and r\[i+len(v)\] == value
originally at r\[i\]. Insert panics if i is out of range. This function
is O(len(s) + len(v)).

#### [Example]

Code:

```go
names := []string{"Alice", "Bob", "Vera"}
names = slices.Insert(names, 1, "Bill", "Billie")
names = slices.Insert(names, len(names), "Zac")
fmt.Println(names)
```

Output:

```go
[Alice Bill Billie Bob Vera Zac]
```

func IsSorted 
-------------

```go
func IsSorted[S ~[]E, E cmp.Ordered](x S) bool
```

IsSorted reports whether x is sorted in ascending order.

#### [Example]

Code:

```go
fmt.Println(slices.IsSorted([]string{"Alice", "Bob", "Vera"}))
fmt.Println(slices.IsSorted([]int{0, 2, 1}))
```

Output:

```go
true
false
```

func IsSortedFunc 
-----------------

```go
func IsSortedFunc[S ~[]E, E any](x S, cmp func(a, b E) int) bool
```

IsSortedFunc reports whether x is sorted in ascending order, with cmp as
the comparison function as defined by [SortFunc](#SortFunc).

#### [Example]

Code:

```go
names := []string{"alice", "Bob", "VERA"}
isSortedInsensitive := slices.IsSortedFunc(names, func(a, b string) int {
    return cmp.Compare(strings.ToLower(a), strings.ToLower(b))
})
fmt.Println(isSortedInsensitive)
fmt.Println(slices.IsSorted(names))
```

Output:

```go
true
false
```

func Max 
--------

```go
func Max[S ~[]E, E cmp.Ordered](x S) E
```

Max returns the maximal value in x. It panics if x is empty. For
floating-point E, Max propagates NaNs (any NaN value in x forces the
output to be NaN).

#### [Example]

Code:

```go
numbers := []int{0, 42, -10, 8}
fmt.Println(slices.Max(numbers))
```

Output:

```go
42
```

func MaxFunc 
------------

```go
func MaxFunc[S ~[]E, E any](x S, cmp func(a, b E) int) E
```

MaxFunc returns the maximal value in x, using cmp to compare elements.
It panics if x is empty. If there is more than one maximal element
according to the cmp function, MaxFunc returns the first one.

#### [Example]

Code:

```go
type Person struct {
    Name string
    Age  int
}
people := []Person{
    {"Gopher", 13},
    {"Alice", 55},
    {"Vera", 24},
    {"Bob", 55},
}
firstOldest := slices.MaxFunc(people, func(a, b Person) int {
    return cmp.Compare(a.Age, b.Age)
})
fmt.Println(firstOldest.Name)
```

Output:

```go
Alice
```

func Min 
--------

```go
func Min[S ~[]E, E cmp.Ordered](x S) E
```

Min returns the minimal value in x. It panics if x is empty. For
floating-point numbers, Min propagates NaNs (any NaN value in x forces
the output to be NaN).

#### [Example]

Code:

```go
numbers := []int{0, 42, -10, 8}
fmt.Println(slices.Min(numbers))
```

Output:

```go
-10
```

func MinFunc 
------------

```go
func MinFunc[S ~[]E, E any](x S, cmp func(a, b E) int) E
```

MinFunc returns the minimal value in x, using cmp to compare elements.
It panics if x is empty. If there is more than one minimal element
according to the cmp function, MinFunc returns the first one.

#### [Example]

Code:

```go
type Person struct {
    Name string
    Age  int
}
people := []Person{
    {"Gopher", 13},
    {"Bob", 5},
    {"Vera", 24},
    {"Bill", 5},
}
firstYoungest := slices.MinFunc(people, func(a, b Person) int {
    return cmp.Compare(a.Age, b.Age)
})
fmt.Println(firstYoungest.Name)
```

Output:

```go
Bob
```

func Replace 
------------

```go
func Replace[S ~[]E, E any](s S, i, j int, v ...E) S
```

Replace replaces the elements s\[i:j\] by the given v, and returns the
modified slice. Replace panics if s\[i:j\] is not a valid slice of s.

#### [Example]

Code:

```go
names := []string{"Alice", "Bob", "Vera", "Zac"}
names = slices.Replace(names, 1, 3, "Bill", "Billie", "Cat")
fmt.Println(names)
```

Output:

```go
[Alice Bill Billie Cat Zac]
```

func Reverse 
------------

```go
func Reverse[S ~[]E, E any](s S)
```

Reverse reverses the elements of the slice in place.

#### [Example]

Code:

```go
names := []string{"alice", "Bob", "VERA"}
slices.Reverse(names)
fmt.Println(names)
```

Output:

```go
[VERA Bob alice]
```

func Sort 
---------

```go
func Sort[S ~[]E, E cmp.Ordered](x S)
```

Sort sorts a slice of any ordered type in ascending order. When sorting
floating-point numbers, NaNs are ordered before other values.

#### [Example]

Code:

```go
smallInts := []int8{0, 42, -10, 8}
slices.Sort(smallInts)
fmt.Println(smallInts)
```

Output:

```go
[-10 0 8 42]
```

func SortFunc 
-------------

```go
func SortFunc[S ~[]E, E any](x S, cmp func(a, b E) int)
```

SortFunc sorts the slice x in ascending order as determined by the cmp
function. This sort is not guaranteed to be stable. cmp(a, b) should
return a negative number when a \< b, a positive number when a \> b and
zero when a == b.

SortFunc requires that cmp is a strict weak ordering. See
https://en.wikipedia.org/wiki/Weak_ordering#Strict_weak_orderings>.

#### [Example (CaseInsensitive)]

Code:

```go
names := []string{"Bob", "alice", "VERA"}
slices.SortFunc(names, func(a, b string) int {
    return cmp.Compare(strings.ToLower(a), strings.ToLower(b))
})
fmt.Println(names)
```

Output:

```go
[alice Bob VERA]
```

#### [Example (MultiField)]

Code:

```go
type Person struct {
    Name string
    Age  int
}
people := []Person{
    {"Gopher", 13},
    {"Alice", 55},
    {"Bob", 24},
    {"Alice", 20},
}
slices.SortFunc(people, func(a, b Person) int {
    if n := cmp.Compare(a.Name, b.Name); n != 0 {
        return n
    }
    // If names are equal, order by age
    return cmp.Compare(a.Age, b.Age)
})
fmt.Println(people)
```

Output:

```go
[{Alice 20} {Alice 55} {Bob 24} {Gopher 13}]
```

func SortStableFunc 
-------------------

```go
func SortStableFunc[S ~[]E, E any](x S, cmp func(a, b E) int)
```

SortStableFunc sorts the slice x while keeping the original order of
equal elements, using cmp to compare elements in the same way as
[SortFunc](#SortFunc).

#### [Example]

Code:

```go
type Person struct {
    Name string
    Age  int
}
people := []Person{
    {"Gopher", 13},
    {"Alice", 20},
    {"Bob", 24},
    {"Alice", 55},
}
// Stable sort by name, keeping age ordering of Alices intact
slices.SortStableFunc(people, func(a, b Person) int {
    return cmp.Compare(a.Name, b.Name)
})
fmt.Println(people)
```

Output:

```go
[{Alice 20} {Alice 55} {Bob 24} {Gopher 13}]
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/slices/>

