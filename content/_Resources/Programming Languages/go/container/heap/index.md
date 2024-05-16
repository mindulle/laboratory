Package heap
============

-   `import "container/heap"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package heap provides heap operations for any type that implements
heap.Interface. A heap is a tree with the property that each node is the
minimum-valued node in its subtree.

The minimum element in the tree is the root, at index 0.

A heap is a common way to implement a priority queue. To build a
priority queue, implement the Heap interface with the (negative)
priority as the ordering for the Less method, so Push adds items while
Pop removes the highest-priority item from the queue. The Examples
include such an implementation; the file example\_pq\_test.go has the
complete source.

#### [Example (IntHeap)]

This example inserts several ints into an IntHeap, checks the minimum,
and removes them in order of priority.

Code:

```go
// This example demonstrates an integer heap built using the heap interface.
package heap_test

import (
    "container/heap"
    "fmt"
)

// An IntHeap is a min-heap of ints.
type IntHeap []int

func (h IntHeap) Len() int           { return len(h) }
func (h IntHeap) Less(i, j int) bool { return h[i] < h[j] }
func (h IntHeap) Swap(i, j int)      { h[i], h[j] = h[j], h[i] }

func (h *IntHeap) Push(x any) {
    // Push and Pop use pointer receivers because they modify the slice's length,
    // not just its contents.
    *h = append(*h, x.(int))
}

func (h *IntHeap) Pop() any {
    old := *h
    n := len(old)
    x := old[n-1]
    *h = old[0 : n-1]
    return x
}

// This example inserts several ints into an IntHeap, checks the minimum,
// and removes them in order of priority.
func Example_intHeap() {
    h := &IntHeap{2, 1, 5}
    heap.Init(h)
    heap.Push(h, 3)
    fmt.Printf("minimum: %d\n", (*h)[0])
    for h.Len() > 0 {
        fmt.Printf("%d ", heap.Pop(h))
    }
    // Output:
    // minimum: 1
    // 1 2 3 5
}
```

#### [Example (PriorityQueue)]

This example creates a PriorityQueue with some items, adds and
manipulates an item, and then removes the items in priority order.

Code:

```go
// This example demonstrates a priority queue built using the heap interface.
package heap_test

import (
    "container/heap"
    "fmt"
)

// An Item is something we manage in a priority queue.
type Item struct {
    value    string // The value of the item; arbitrary.
    priority int    // The priority of the item in the queue.
    // The index is needed by update and is maintained by the heap.Interface methods.
    index int // The index of the item in the heap.
}

// A PriorityQueue implements heap.Interface and holds Items.
type PriorityQueue []*Item

func (pq PriorityQueue) Len() int { return len(pq) }

func (pq PriorityQueue) Less(i, j int) bool {
    // We want Pop to give us the highest, not lowest, priority so we use greater than here.
    return pq[i].priority > pq[j].priority
}

func (pq PriorityQueue) Swap(i, j int) {
    pq[i], pq[j] = pq[j], pq[i]
    pq[i].index = i
    pq[j].index = j
}

func (pq *PriorityQueue) Push(x any) {
    n := len(*pq)
    item := x.(*Item)
    item.index = n
    *pq = append(*pq, item)
}

func (pq *PriorityQueue) Pop() any {
    old := *pq
    n := len(old)
    item := old[n-1]
    old[n-1] = nil  // avoid memory leak
    item.index = -1 // for safety
    *pq = old[0 : n-1]
    return item
}

// update modifies the priority and value of an Item in the queue.
func (pq *PriorityQueue) update(item *Item, value string, priority int) {
    item.value = value
    item.priority = priority
    heap.Fix(pq, item.index)
}

// This example creates a PriorityQueue with some items, adds and manipulates an item,
// and then removes the items in priority order.
func Example_priorityQueue() {
    // Some items and their priorities.
    items := map[string]int{
        "banana": 3, "apple": 2, "pear": 4,
    }

    // Create a priority queue, put the items in it, and
    // establish the priority queue (heap) invariants.
    pq := make(PriorityQueue, len(items))
    i := 0
    for value, priority := range items {
        pq[i] = &Item{
            value:    value,
            priority: priority,
            index:    i,
        }
        i++
    }
    heap.Init(&pq)

    // Insert a new item and then modify its priority.
    item := &Item{
        value:    "orange",
        priority: 1,
    }
    heap.Push(&pq, item)
    pq.update(item, item.value, 5)

    // Take the items out; they arrive in decreasing priority order.
    for pq.Len() > 0 {
        item := heap.Pop(&pq).(*Item)
        fmt.Printf("%.2d:%s ", item.priority, item.value)
    }
    // Output:
    // 05:orange 04:pear 03:banana 02:apple
}
```

Index 
-----

-   [func Fix(h Interface, i int)](#Fix)
-   [func Init(h Interface)](#Init)
-   [func Pop(h Interface) any](#Pop)
-   [func Push(h Interface, x any)](#Push)
-   [func Remove(h Interface, i int) any](#Remove)
-   [type Interface](#Interface)

 
### Examples

[Package (IntHeap)](#example__intHeap)

[Package (PriorityQueue)](#example__priorityQueue)


### Package files

heap.go

func Fix 
---------------------------------------

```go
func Fix(h Interface, i int)
```

Fix re-establishes the heap ordering after the element at index i has
changed its value. Changing the value of the element at index i and then
calling Fix is equivalent to, but less expensive than, calling Remove(h,
i) followed by a Push of the new value. The complexity is O(log n) where
n = h.Len().

func Init 
---------

```go
func Init(h Interface)
```

Init establishes the heap invariants required by the other routines in
this package. Init is idempotent with respect to the heap invariants and
may be called whenever the heap invariants may have been invalidated.
The complexity is O(n) where n = h.Len().

func Pop 
--------

```go
func Pop(h Interface) any
```

Pop removes and returns the minimum element (according to Less) from the
heap. The complexity is O(log n) where n = h.Len(). Pop is equivalent to
Remove(h, 0).

func Push 
---------

```go
func Push(h Interface, x any)
```

Push pushes the element x onto the heap. The complexity is O(log n)
where n = h.Len().

func Remove 
-----------

```go
func Remove(h Interface, i int) any
```

Remove removes and returns the element at index i from the heap. The
complexity is O(log n) where n = h.Len().

type Interface 
--------------

The Interface type describes the requirements for a type using the
routines in this package. Any type that implements it may be used as a
min-heap with the following invariants (established after Init has been
called or if the data is empty or sorted):

```go
!h.Less(j, i) for 0 <= i < h.Len() and 2*i+1 <= j <= 2*i+2 and j < h.Len()
```

Note that Push and Pop in this interface are for package heap\'s
implementation to call. To add and remove things from the heap, use
heap.Push and heap.Pop.

```go
type Interface interface {
    sort.Interface
    Push(x any) // add x as element Len()
    Pop() any   // remove and return element Len() - 1.
}
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/container/heap/>

