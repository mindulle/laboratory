Command arena
=============

The arena package provides the ability to allocate memory for a
collection of Go values and free that space manually all at once,
safely. The purpose of this functionality is to improve efficiency:
manually freeing memory before a garbage collection delays that cycle.
Less frequent cycles means the CPU cost of the garbage collector is
incurred less frequently.

This functionality in this package is mostly captured in the Arena type.
Arenas allocate large chunks of memory for Go values, so they\'re likely
to be inefficient for allocating only small amounts of small Go values.
They\'re best used in bulk, on the order of MiB of memory allocated on
each use.

Note that by allowing for this limited form of manual memory allocation
that use-after-free bugs are possible with regular Go values. This
package limits the impact of these use-after-free bugs by preventing
reuse of freed memory regions until the garbage collector is able to
determine that it is safe. Typically, a use-after-free bug will result
in a fault and a helpful error message, but this package reserves the
right to not force a fault on freed memory. That means a valid
implementation of this package is to just allocate all memory the way
the runtime normally would, and in fact, it reserves the right to
occasionally do so for some Go values.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/arena/>

