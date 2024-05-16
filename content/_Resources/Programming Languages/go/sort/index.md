Package sort
============

-   `import "sort"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package sort provides primitives for sorting slices and user-defined
collections.

#### [Example]

Code:

```go
package sort_test

import (
    "fmt"
    "sort"
)

type Person struct {
    Name string
    Age  int
}

func (p Person) String() string {
    return fmt.Sprintf("%s: %d", p.Name, p.Age)
}

// ByAge implements sort.Interface for []Person based on
// the Age field.
type ByAge []Person

func (a ByAge) Len() int           { return len(a) }
func (a ByAge) Swap(i, j int)      { a[i], a[j] = a[j], a[i] }
func (a ByAge) Less(i, j int) bool { return a[i].Age < a[j].Age }

func Example() {
    people := []Person{
        {"Bob", 31},
        {"John", 42},
        {"Michael", 17},
        {"Jenny", 26},
    }

    fmt.Println(people)
    // There are two ways to sort a slice. First, one can define
    // a set of methods for the slice type, as with ByAge, and
    // call sort.Sort. In this first example we use that technique.
    sort.Sort(ByAge(people))
    fmt.Println(people)

    // The other way is to use sort.Slice with a custom Less
    // function, which can be provided as a closure. In this
    // case no methods are needed. (And if they exist, they
    // are ignored.) Here we re-sort in reverse order: compare
    // the closure with ByAge.Less.
    sort.Slice(people, func(i, j int) bool {
        return people[i].Age > people[j].Age
    })
    fmt.Println(people)

    // Output:
    // [Bob: 31 John: 42 Michael: 17 Jenny: 26]
    // [Michael: 17 Jenny: 26 Bob: 31 John: 42]
    // [John: 42 Bob: 31 Jenny: 26 Michael: 17]
}
```

#### [Example (SortKeys)]

ExampleSortKeys demonstrates a technique for sorting a struct type using
programmable sort criteria.

Code:

```go
package sort_test

import (
    "fmt"
    "sort"
)

// A couple of type definitions to make the units clear.
type earthMass float64
type au float64

// A Planet defines the properties of a solar system object.
type Planet struct {
    name     string
    mass     earthMass
    distance au
}

// By is the type of a "less" function that defines the ordering of its Planet arguments.
type By func(p1, p2 *Planet) bool

// Sort is a method on the function type, By, that sorts the argument slice according to the function.
func (by By) Sort(planets []Planet) {
    ps := &planetSorter{
        planets: planets,
        by:      by, // The Sort method's receiver is the function (closure) that defines the sort order.
    }
    sort.Sort(ps)
}

// planetSorter joins a By function and a slice of Planets to be sorted.
type planetSorter struct {
    planets []Planet
    by      func(p1, p2 *Planet) bool // Closure used in the Less method.
}

// Len is part of sort.Interface.
func (s *planetSorter) Len() int {
    return len(s.planets)
}

// Swap is part of sort.Interface.
func (s *planetSorter) Swap(i, j int) {
    s.planets[i], s.planets[j] = s.planets[j], s.planets[i]
}

// Less is part of sort.Interface. It is implemented by calling the "by" closure in the sorter.
func (s *planetSorter) Less(i, j int) bool {
    return s.by(&s.planets[i], &s.planets[j])
}

var planets = []Planet{
    {"Mercury", 0.055, 0.4},
    {"Venus", 0.815, 0.7},
    {"Earth", 1.0, 1.0},
    {"Mars", 0.107, 1.5},
}

// ExampleSortKeys demonstrates a technique for sorting a struct type using programmable sort criteria.
func Example_sortKeys() {
    // Closures that order the Planet structure.
    name := func(p1, p2 *Planet) bool {
        return p1.name < p2.name
    }
    mass := func(p1, p2 *Planet) bool {
        return p1.mass < p2.mass
    }
    distance := func(p1, p2 *Planet) bool {
        return p1.distance < p2.distance
    }
    decreasingDistance := func(p1, p2 *Planet) bool {
        return distance(p2, p1)
    }

    // Sort the planets by the various criteria.
    By(name).Sort(planets)
    fmt.Println("By name:", planets)

    By(mass).Sort(planets)
    fmt.Println("By mass:", planets)

    By(distance).Sort(planets)
    fmt.Println("By distance:", planets)

    By(decreasingDistance).Sort(planets)
    fmt.Println("By decreasing distance:", planets)

    // Output: By name: [{Earth 1 1} {Mars 0.107 1.5} {Mercury 0.055 0.4} {Venus 0.815 0.7}]
    // By mass: [{Mercury 0.055 0.4} {Mars 0.107 1.5} {Venus 0.815 0.7} {Earth 1 1}]
    // By distance: [{Mercury 0.055 0.4} {Venus 0.815 0.7} {Earth 1 1} {Mars 0.107 1.5}]
    // By decreasing distance: [{Mars 0.107 1.5} {Earth 1 1} {Venus 0.815 0.7} {Mercury 0.055 0.4}]
}
```

#### [Example (SortMultiKeys)]

ExampleMultiKeys demonstrates a technique for sorting a struct type
using different sets of multiple fields in the comparison. We chain
together \"Less\" functions, each of which compares a single field.

Code:

```go
package sort_test

import (
    "fmt"
    "sort"
)

// A Change is a record of source code changes, recording user, language, and delta size.
type Change struct {
    user     string
    language string
    lines    int
}

type lessFunc func(p1, p2 *Change) bool

// multiSorter implements the Sort interface, sorting the changes within.
type multiSorter struct {
    changes []Change
    less    []lessFunc
}

// Sort sorts the argument slice according to the less functions passed to OrderedBy.
func (ms *multiSorter) Sort(changes []Change) {
    ms.changes = changes
    sort.Sort(ms)
}

// OrderedBy returns a Sorter that sorts using the less functions, in order.
// Call its Sort method to sort the data.
func OrderedBy(less ...lessFunc) *multiSorter {
    return &multiSorter{
        less: less,
    }
}

// Len is part of sort.Interface.
func (ms *multiSorter) Len() int {
    return len(ms.changes)
}

// Swap is part of sort.Interface.
func (ms *multiSorter) Swap(i, j int) {
    ms.changes[i], ms.changes[j] = ms.changes[j], ms.changes[i]
}

// Less is part of sort.Interface. It is implemented by looping along the
// less functions until it finds a comparison that discriminates between
// the two items (one is less than the other). Note that it can call the
// less functions twice per call. We could change the functions to return
// -1, 0, 1 and reduce the number of calls for greater efficiency: an
// exercise for the reader.
func (ms *multiSorter) Less(i, j int) bool {
    p, q := &ms.changes[i], &ms.changes[j]
    // Try all but the last comparison.
    var k int
    for k = 0; k < len(ms.less)-1; k++ {
        less := ms.less[k]
        switch {
        case less(p, q):
            // p < q, so we have a decision.
            return true
        case less(q, p):
            // p > q, so we have a decision.
            return false
        }
        // p == q; try the next comparison.
    }
    // All comparisons to here said "equal", so just return whatever
    // the final comparison reports.
    return ms.less[k](p, q)
}

var changes = []Change{
    {"gri", "Go", 100},
    {"ken", "C", 150},
    {"glenda", "Go", 200},
    {"rsc", "Go", 200},
    {"r", "Go", 100},
    {"ken", "Go", 200},
    {"dmr", "C", 100},
    {"r", "C", 150},
    {"gri", "Smalltalk", 80},
}

// ExampleMultiKeys demonstrates a technique for sorting a struct type using different
// sets of multiple fields in the comparison. We chain together "Less" functions, each of
// which compares a single field.
func Example_sortMultiKeys() {
    // Closures that order the Change structure.
    user := func(c1, c2 *Change) bool {
        return c1.user < c2.user
    }
    language := func(c1, c2 *Change) bool {
        return c1.language < c2.language
    }
    increasingLines := func(c1, c2 *Change) bool {
        return c1.lines < c2.lines
    }
    decreasingLines := func(c1, c2 *Change) bool {
        return c1.lines > c2.lines // Note: > orders downwards.
    }

    // Simple use: Sort by user.
    OrderedBy(user).Sort(changes)
    fmt.Println("By user:", changes)

    // More examples.
    OrderedBy(user, increasingLines).Sort(changes)
    fmt.Println("By user,<lines:", changes)

    OrderedBy(user, decreasingLines).Sort(changes)
    fmt.Println("By user,>lines:", changes)

    OrderedBy(language, increasingLines).Sort(changes)
    fmt.Println("By language,<lines:", changes)

    OrderedBy(language, increasingLines, user).Sort(changes)
    fmt.Println("By language,<lines,user:", changes)

    // Output:
    // By user: [{dmr C 100} {glenda Go 200} {gri Go 100} {gri Smalltalk 80} {ken C 150} {ken Go 200} {r Go 100} {r C 150} {rsc Go 200}]
    // By user,<lines: [{dmr C 100} {glenda Go 200} {gri Smalltalk 80} {gri Go 100} {ken C 150} {ken Go 200} {r Go 100} {r C 150} {rsc Go 200}]
    // By user,>lines: [{dmr C 100} {glenda Go 200} {gri Go 100} {gri Smalltalk 80} {ken Go 200} {ken C 150} {r C 150} {r Go 100} {rsc Go 200}]
    // By language,<lines: [{dmr C 100} {ken C 150} {r C 150} {gri Go 100} {r Go 100} {glenda Go 200} {ken Go 200} {rsc Go 200} {gri Smalltalk 80}]
    // By language,<lines,user: [{dmr C 100} {ken C 150} {r C 150} {gri Go 100} {r Go 100} {glenda Go 200} {ken Go 200} {rsc Go 200} {gri Smalltalk 80}]

}
```

#### [Example (SortWrapper)]

Code:

```go
package sort_test

import (
    "fmt"
    "sort"
)

type Grams int

func (g Grams) String() string { return fmt.Sprintf("%dg", int(g)) }

type Organ struct {
    Name   string
    Weight Grams
}

type Organs []*Organ

func (s Organs) Len() int      { return len(s) }
func (s Organs) Swap(i, j int) { s[i], s[j] = s[j], s[i] }

// ByName implements sort.Interface by providing Less and using the Len and
// Swap methods of the embedded Organs value.
type ByName struct{ Organs }

func (s ByName) Less(i, j int) bool { return s.Organs[i].Name < s.Organs[j].Name }

// ByWeight implements sort.Interface by providing Less and using the Len and
// Swap methods of the embedded Organs value.
type ByWeight struct{ Organs }

func (s ByWeight) Less(i, j int) bool { return s.Organs[i].Weight < s.Organs[j].Weight }

func Example_sortWrapper() {
    s := []*Organ{
        {"brain", 1340},
        {"heart", 290},
        {"liver", 1494},
        {"pancreas", 131},
        {"prostate", 62},
        {"spleen", 162},
    }

    sort.Sort(ByWeight{s})
    fmt.Println("Organs by weight:")
    printOrgans(s)

    sort.Sort(ByName{s})
    fmt.Println("Organs by name:")
    printOrgans(s)

    // Output:
    // Organs by weight:
    // prostate (62g)
    // pancreas (131g)
    // spleen   (162g)
    // heart    (290g)
    // brain    (1340g)
    // liver    (1494g)
    // Organs by name:
    // brain    (1340g)
    // heart    (290g)
    // liver    (1494g)
    // pancreas (131g)
    // prostate (62g)
    // spleen   (162g)
}

func printOrgans(s []*Organ) {
    for _, o := range s {
        fmt.Printf("%-8s (%v)\n", o.Name, o.Weight)
    }
}
```

Index 
-----

-   [func Find(n int, cmp func(int) int) (i int, found bool)](#Find)
-   [func Float64s(x \[\]float64)](#Float64s)
-   [func Float64sAreSorted(x \[\]float64) bool](#Float64sAreSorted)
-   [func Ints(x \[\]int)](#Ints)
-   [func IntsAreSorted(x \[\]int) bool](#IntsAreSorted)
-   [func IsSorted(data Interface) bool](#IsSorted)
-   [func Search(n int, f func(int) bool) int](#Search)
-   [func SearchFloat64s(a \[\]float64, x float64) int](#SearchFloat64s)
-   [func SearchInts(a \[\]int, x int) int](#SearchInts)
-   [func SearchStrings(a \[\]string, x string) int](#SearchStrings)
-   [func Slice(x any, less func(i, j int) bool)](#Slice)
-   [func SliceIsSorted(x any, less func(i, j int) bool)
    bool](#SliceIsSorted)
-   [func SliceStable(x any, less func(i, j int) bool)](#SliceStable)
-   [func Sort(data Interface)](#Sort)
-   [func Stable(data Interface)](#Stable)
-   [func Strings(x \[\]string)](#Strings)
-   [func StringsAreSorted(x \[\]string) bool](#StringsAreSorted)
-   [type Float64Slice](#Float64Slice)
-   [func (x Float64Slice) Len() int](#Float64Slice.Len)
-   [func (x Float64Slice) Less(i, j int) bool](#Float64Slice.Less)
-   [func (p Float64Slice) Search(x float64) int](#Float64Slice.Search)
-   [func (x Float64Slice) Sort()](#Float64Slice.Sort)
-   [func (x Float64Slice) Swap(i, j int)](#Float64Slice.Swap)
-   [type IntSlice](#IntSlice)
-   [func (x IntSlice) Len() int](#IntSlice.Len)
-   [func (x IntSlice) Less(i, j int) bool](#IntSlice.Less)
-   [func (p IntSlice) Search(x int) int](#IntSlice.Search)
-   [func (x IntSlice) Sort()](#IntSlice.Sort)
-   [func (x IntSlice) Swap(i, j int)](#IntSlice.Swap)
-   [type Interface](#Interface)
-   [func Reverse(data Interface) Interface](#Reverse)
-   [type StringSlice](#StringSlice)
-   [func (x StringSlice) Len() int](#StringSlice.Len)
-   [func (x StringSlice) Less(i, j int) bool](#StringSlice.Less)
-   [func (p StringSlice) Search(x string) int](#StringSlice.Search)
-   [func (x StringSlice) Sort()](#StringSlice.Sort)
-   [func (x StringSlice) Swap(i, j int)](#StringSlice.Swap)

 
### Examples

[Package](#example_)

[Float64s](#example_Float64s)

[Float64sAreSorted](#example_Float64sAreSorted)

[Ints](#example_Ints)

[IntsAreSorted](#example_IntsAreSorted)

[Reverse](#example_Reverse)

[Search](#example_Search)

[SearchFloat64s](#example_SearchFloat64s)

[SearchInts](#example_SearchInts)

[Search
(DescendingOrder)](#example_Search_descendingOrder)

[Slice](#example_Slice)

[SliceStable](#example_SliceStable)

[Strings](#example_Strings)

[Package (SortKeys)](#example__sortKeys)

[Package (SortMultiKeys)](#example__sortMultiKeys)

[Package (SortWrapper)](#example__sortWrapper)


### Package files

search.go slice.go sort.go zsortfunc.go zsortinterface.go

func Find 
------------------------------------------

```go
func Find(n int, cmp func(int) int) (i int, found bool)
```

Find uses binary search to find and return the smallest index i in \[0,
n) at which cmp(i) \<= 0. If there is no such index i, Find returns i =
n. The found result is true if i \< n and cmp(i) == 0. Find calls cmp(i)
only for i in the range \[0, n).

To permit binary search, Find requires that cmp(i) \> 0 for a leading
prefix of the range, cmp(i) == 0 in the middle, and cmp(i) \< 0 for the
final suffix of the range. (Each subrange could be empty.) The usual way
to establish this condition is to interpret cmp(i) as a comparison of a
desired target value t against entry i in an underlying indexed data
structure x, returning \<0, 0, and \>0 when t \< x\[i\], t == x\[i\],
and t \> x\[i\], respectively.

For example, to look for a particular string in a sorted, random-access
list of strings:

```go
i, found := sort.Find(x.Len(), func(i int) int {
    return strings.Compare(target, x.At(i))
})
if found {
    fmt.Printf("found %s at entry %d\n", target, i)
} else {
    fmt.Printf("%s not found, would insert at %d", target, i)
}
```

func Float64s 
-------------

```go
func Float64s(x []float64)
```

Float64s sorts a slice of float64s in increasing order. Not-a-number
(NaN) values are ordered before other values.

Note: consider using the newer slices.Sort function, which runs faster.

#### [Example]

Code:

```go
s := []float64{5.2, -1.3, 0.7, -3.8, 2.6} // unsorted
sort.Float64s(s)
fmt.Println(s)

s = []float64{math.Inf(1), math.NaN(), math.Inf(-1), 0.0} // unsorted
sort.Float64s(s)
fmt.Println(s)
```

Output:

```go
[-3.8 -1.3 0.7 2.6 5.2]
[NaN -Inf 0 +Inf]
```

func Float64sAreSorted 
----------------------

```go
func Float64sAreSorted(x []float64) bool
```

Float64sAreSorted reports whether the slice x is sorted in increasing
order, with not-a-number (NaN) values before any other values.

Note: consider using the newer slices.IsSorted function, which runs
faster.

#### [Example]

Code:

```go
s := []float64{0.7, 1.3, 2.6, 3.8, 5.2} // sorted ascending
fmt.Println(sort.Float64sAreSorted(s))

s = []float64{5.2, 3.8, 2.6, 1.3, 0.7} // sorted descending
fmt.Println(sort.Float64sAreSorted(s))

s = []float64{5.2, 1.3, 0.7, 3.8, 2.6} // unsorted
fmt.Println(sort.Float64sAreSorted(s))
```

Output:

```go
true
false
false
```

func Ints 
---------

```go
func Ints(x []int)
```

Ints sorts a slice of ints in increasing order.

Note: consider using the newer slices.Sort function, which runs faster.

#### [Example]

Code:

```go
s := []int{5, 2, 6, 3, 1, 4} // unsorted
sort.Ints(s)
fmt.Println(s)
```

Output:

```go
[1 2 3 4 5 6]
```

func IntsAreSorted 
------------------

```go
func IntsAreSorted(x []int) bool
```

IntsAreSorted reports whether the slice x is sorted in increasing order.

Note: consider using the newer slices.IsSorted function, which runs
faster.

#### [Example]

Code:

```go
s := []int{1, 2, 3, 4, 5, 6} // sorted ascending
fmt.Println(sort.IntsAreSorted(s))

s = []int{6, 5, 4, 3, 2, 1} // sorted descending
fmt.Println(sort.IntsAreSorted(s))

s = []int{3, 2, 4, 1, 5} // unsorted
fmt.Println(sort.IntsAreSorted(s))
```

Output:

```go
true
false
false
```

func IsSorted 
-------------

```go
func IsSorted(data Interface) bool
```

IsSorted reports whether data is sorted.

Note: in many situations, the newer slices.IsSortedFunc function is more
ergonomic and runs faster.

func Search 
-----------

```go
func Search(n int, f func(int) bool) int
```

Search uses binary search to find and return the smallest index i in
\[0, n) at which f(i) is true, assuming that on the range \[0, n), f(i)
== true implies f(i+1) == true. That is, Search requires that f is false
for some (possibly empty) prefix of the input range \[0, n) and then
true for the (possibly empty) remainder; Search returns the first true
index. If there is no such index, Search returns n. (Note that the \"not
found\" return value is not -1 as in, for instance, strings.Index.)
Search calls f(i) only for i in the range \[0, n).

A common use of Search is to find the index i for a value x in a sorted,
indexable data structure such as an array or slice. In this case, the
argument f, typically a closure, captures the value to be searched for,
and how the data structure is indexed and ordered.

For instance, given a slice data sorted in ascending order, the call
Search(len(data), func(i int) bool \{ return data\[i\] \>= 23 \}) returns
the smallest index i such that data\[i\] \>= 23. If the caller wants to
find whether 23 is in the slice, it must test data\[i\] == 23
separately.

Searching data sorted in descending order would use the \<= operator
instead of the \>= operator.

To complete the example above, the following code tries to find the
value x in an integer slice data sorted in ascending order:

```go
x := 23
i := sort.Search(len(data), func(i int) bool { return data[i] >= x })
if i < len(data) && data[i] == x {
    // x is present at data[i]
} else {
    // x is not present in data,
    // but i is the index where it would be inserted.
}
```

As a more whimsical example, this program guesses your number:

```go
func GuessingGame() {
    var s string
    fmt.Printf("Pick an integer from 0 to 100.\n")
    answer := sort.Search(100, func(i int) bool {
        fmt.Printf("Is your number <= %d? ", i)
        fmt.Scanf("%s", &s)
        return s != "" && s[0] == 'y'
    })
    fmt.Printf("Your number is %d.\n", answer)
}
```

#### [Example]

This example demonstrates searching a list sorted in ascending order.

Code:

```go
a := []int{1, 3, 6, 10, 15, 21, 28, 36, 45, 55}
x := 6

i := sort.Search(len(a), func(i int) bool { return a[i] >= x })
if i < len(a) && a[i] == x {
    fmt.Printf("found %d at index %d in %v\n", x, i, a)
} else {
    fmt.Printf("%d not found in %v\n", x, a)
}
```

Output:

```go
found 6 at index 2 in [1 3 6 10 15 21 28 36 45 55]
```

#### [Example (DescendingOrder)]

This example demonstrates searching a list sorted in descending order.
The approach is the same as searching a list in ascending order, but
with the condition inverted.

Code:

```go
a := []int{55, 45, 36, 28, 21, 15, 10, 6, 3, 1}
x := 6

i := sort.Search(len(a), func(i int) bool { return a[i] <= x })
if i < len(a) && a[i] == x {
    fmt.Printf("found %d at index %d in %v\n", x, i, a)
} else {
    fmt.Printf("%d not found in %v\n", x, a)
}
```

Output:

```go
found 6 at index 7 in [55 45 36 28 21 15 10 6 3 1]
```

func SearchFloat64s 
-------------------

```go
func SearchFloat64s(a []float64, x float64) int
```

SearchFloat64s searches for x in a sorted slice of float64s and returns
the index as specified by Search. The return value is the index to
insert x if x is not present (it could be len(a)). The slice must be
sorted in ascending order.

#### [Example]

This example demonstrates searching for float64 in a list sorted in
ascending order.

Code:

```go
a := []float64{1.0, 2.0, 3.3, 4.6, 6.1, 7.2, 8.0}

x := 2.0
i := sort.SearchFloat64s(a, x)
fmt.Printf("found %g at index %d in %v\n", x, i, a)

x = 0.5
i = sort.SearchFloat64s(a, x)
fmt.Printf("%g not found, can be inserted at index %d in %v\n", x, i, a)
```

Output:

```go
found 2 at index 1 in [1 2 3.3 4.6 6.1 7.2 8]
0.5 not found, can be inserted at index 0 in [1 2 3.3 4.6 6.1 7.2 8]
```

func SearchInts 
---------------

```go
func SearchInts(a []int, x int) int
```

SearchInts searches for x in a sorted slice of ints and returns the
index as specified by Search. The return value is the index to insert x
if x is not present (it could be len(a)). The slice must be sorted in
ascending order.

#### [Example]

This example demonstrates searching for int in a list sorted in
ascending order.

Code:

```go
a := []int{1, 2, 3, 4, 6, 7, 8}

x := 2
i := sort.SearchInts(a, x)
fmt.Printf("found %d at index %d in %v\n", x, i, a)

x = 5
i = sort.SearchInts(a, x)
fmt.Printf("%d not found, can be inserted at index %d in %v\n", x, i, a)
```

Output:

```go
found 2 at index 1 in [1 2 3 4 6 7 8]
5 not found, can be inserted at index 4 in [1 2 3 4 6 7 8]
```

func SearchStrings 
------------------

```go
func SearchStrings(a []string, x string) int
```

SearchStrings searches for x in a sorted slice of strings and returns
the index as specified by Search. The return value is the index to
insert x if x is not present (it could be len(a)). The slice must be
sorted in ascending order.

func Slice 
-----------------------------------------

```go
func Slice(x any, less func(i, j int) bool)
```

Slice sorts the slice x given the provided less function. It panics if x
is not a slice.

The sort is not guaranteed to be stable: equal elements may be reversed
from their original order. For a stable sort, use SliceStable.

The less function must satisfy the same requirements as the Interface
type\'s Less method.

#### [Example]

Code:

```go
people := []struct {
    Name string
    Age  int
}{
    {"Gopher", 7},
    {"Alice", 55},
    {"Vera", 24},
    {"Bob", 75},
}
sort.Slice(people, func(i, j int) bool { return people[i].Name < people[j].Name })
fmt.Println("By name:", people)

sort.Slice(people, func(i, j int) bool { return people[i].Age < people[j].Age })
fmt.Println("By age:", people)
```

Output:

```go
By name: [{Alice 55} {Bob 75} {Gopher 7} {Vera 24}]
By age: [{Gopher 7} {Vera 24} {Alice 55} {Bob 75}]
```

func SliceIsSorted 
-------------------------------------------------

```go
func SliceIsSorted(x any, less func(i, j int) bool) bool
```

SliceIsSorted reports whether the slice x is sorted according to the
provided less function. It panics if x is not a slice.

func SliceStable 
-----------------------------------------------

```go
func SliceStable(x any, less func(i, j int) bool)
```

SliceStable sorts the slice x using the provided less function, keeping
equal elements in their original order. It panics if x is not a slice.

The less function must satisfy the same requirements as the Interface
type\'s Less method.

#### [Example]

Code:

```go
people := []struct {
    Name string
    Age  int
}{
    {"Alice", 25},
    {"Elizabeth", 75},
    {"Alice", 75},
    {"Bob", 75},
    {"Alice", 75},
    {"Bob", 25},
    {"Colin", 25},
    {"Elizabeth", 25},
}

// Sort by name, preserving original order
sort.SliceStable(people, func(i, j int) bool { return people[i].Name < people[j].Name })
fmt.Println("By name:", people)

// Sort by age preserving name order
sort.SliceStable(people, func(i, j int) bool { return people[i].Age < people[j].Age })
fmt.Println("By age,name:", people)
```

Output:

```go
By name: [{Alice 25} {Alice 75} {Alice 75} {Bob 75} {Bob 25} {Colin 25} {Elizabeth 75} {Elizabeth 25}]
By age,name: [{Alice 25} {Bob 25} {Colin 25} {Elizabeth 25} {Alice 75} {Alice 75} {Bob 75} {Elizabeth 75}]
```

func Sort 
---------

```go
func Sort(data Interface)
```

Sort sorts data in ascending order as determined by the Less method. It
makes one call to data.Len to determine n and O(n\*log(n)) calls to
data.Less and data.Swap. The sort is not guaranteed to be stable.

Note: in many situations, the newer slices.SortFunc function is more
ergonomic and runs faster.

func Stable 
------------------------------------------

```go
func Stable(data Interface)
```

Stable sorts data in ascending order as determined by the Less method,
while keeping the original order of equal elements.

It makes one call to data.Len to determine n, O(n\*log(n)) calls to
data.Less and O(n\*log(n)\*log(n)) calls to data.Swap.

Note: in many situations, the newer slices.SortStableFunc function is
more ergonomic and runs faster.

func Strings 
------------

```go
func Strings(x []string)
```

Strings sorts a slice of strings in increasing order.

Note: consider using the newer slices.Sort function, which runs faster.

#### [Example]

Code:

```go
s := []string{"Go", "Bravo", "Gopher", "Alpha", "Grin", "Delta"}
sort.Strings(s)
fmt.Println(s)
```

Output:

```go
[Alpha Bravo Delta Go Gopher Grin]
```

func StringsAreSorted 
---------------------

```go
func StringsAreSorted(x []string) bool
```

StringsAreSorted reports whether the slice x is sorted in increasing
order.

Note: consider using the newer slices.IsSorted function, which runs
faster.

type Float64Slice 
-----------------

Float64Slice implements Interface for a \[\]float64, sorting in
increasing order, with not-a-number (NaN) values ordered before other
values.

```go
type Float64Slice []float64
```

### func (Float64Slice) Len 

```go
func (x Float64Slice) Len() int
```

### func (Float64Slice) Less 

```go
func (x Float64Slice) Less(i, j int) bool
```

Less reports whether x\[i\] should be ordered before x\[j\], as required
by the sort Interface. Note that floating-point comparison by itself is
not a transitive relation: it does not report a consistent ordering for
not-a-number (NaN) values. This implementation of Less places NaN values
before any others, by using:

```go
x[i] < x[j] || (math.IsNaN(x[i]) && !math.IsNaN(x[j]))
```

### func (Float64Slice) Search 

```go
func (p Float64Slice) Search(x float64) int
```

Search returns the result of applying SearchFloat64s to the receiver and
x.

### func (Float64Slice) Sort 

```go
func (x Float64Slice) Sort()
```

Sort is a convenience method: x.Sort() calls Sort(x).

### func (Float64Slice) Swap 

```go
func (x Float64Slice) Swap(i, j int)
```

type IntSlice 
-------------

IntSlice attaches the methods of Interface to \[\]int, sorting in
increasing order.

```go
type IntSlice []int
```

### func (IntSlice) Len 

```go
func (x IntSlice) Len() int
```

### func (IntSlice) Less 

```go
func (x IntSlice) Less(i, j int) bool
```

### func (IntSlice) Search 

```go
func (p IntSlice) Search(x int) int
```

Search returns the result of applying SearchInts to the receiver and x.

### func (IntSlice) Sort 

```go
func (x IntSlice) Sort()
```

Sort is a convenience method: x.Sort() calls Sort(x).

### func (IntSlice) Swap 

```go
func (x IntSlice) Swap(i, j int)
```

type Interface 
--------------

An implementation of Interface can be sorted by the routines in this
package. The methods refer to elements of the underlying collection by
integer index.

```go
type Interface interface {
    // Len is the number of elements in the collection.
    Len() int

    // Less reports whether the element with index i
    // must sort before the element with index j.
    //
    // If both Less(i, j) and Less(j, i) are false,
    // then the elements at index i and j are considered equal.
    // Sort may place equal elements in any order in the final result,
    // while Stable preserves the original input order of equal elements.
    //
    // Less must describe a transitive ordering:
    //  - if both Less(i, j) and Less(j, k) are true, then Less(i, k) must be true as well.
    //  - if both Less(i, j) and Less(j, k) are false, then Less(i, k) must be false as well.
    //
    // Note that floating-point comparison (the < operator on float32 or float64 values)
    // is not a transitive ordering when not-a-number (NaN) values are involved.
    // See Float64Slice.Less for a correct implementation for floating-point values.
    Less(i, j int) bool

    // Swap swaps the elements with indexes i and j.
    Swap(i, j int)
}
```

### func Reverse 

```go
func Reverse(data Interface) Interface
```

Reverse returns the reverse order for data.

#### [Example]

Code:

```go
s := []int{5, 2, 6, 3, 1, 4} // unsorted
sort.Sort(sort.Reverse(sort.IntSlice(s)))
fmt.Println(s)
```

Output:

```go
[6 5 4 3 2 1]
```

type StringSlice 
----------------

StringSlice attaches the methods of Interface to \[\]string, sorting in
increasing order.

```go
type StringSlice []string
```

### func (StringSlice) Len 

```go
func (x StringSlice) Len() int
```

### func (StringSlice) Less 

```go
func (x StringSlice) Less(i, j int) bool
```

### func (StringSlice) Search 

```go
func (p StringSlice) Search(x string) int
```

Search returns the result of applying SearchStrings to the receiver and
x.

### func (StringSlice) Sort 

```go
func (x StringSlice) Sort()
```

Sort is a convenience method: x.Sort() calls Sort(x).

### func (StringSlice) Swap 

```go
func (x StringSlice) Swap(i, j int)
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/sort/>

