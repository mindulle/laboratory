Package atomic
==============

- `import "sync/atomic"`
- [Overview](#pkg-overview)
- [Index](#pkg-index)
- [Examples](#pkg-examples)

Overview
--------

Package atomic provides low-level atomic memory primitives useful for
implementing synchronization algorithms.

These functions require great care to be used correctly. Except for
special, low-level applications, synchronization is better done with
channels or the facilities of the sync package. Share memory by
communicating; don\'t communicate by sharing memory.

The swap operation, implemented by the SwapT functions, is the atomic
equivalent of:

```go
old = *addr
*addr = new
return old
```

The compare-and-swap operation, implemented by the CompareAndSwapT
functions, is the atomic equivalent of:

```go
if *addr == old {
    *addr = new
    return true
}
return false
```

The add operation, implemented by the AddT functions, is the atomic
equivalent of:

```go
*addr += delta
return *addr
```

The load and store operations, implemented by the LoadT and StoreT
functions, are the atomic equivalents of \"return \*addr\" and \"\*addr
= val\".

In the terminology of the Go memory model, if the effect of an atomic
operation A is observed by atomic operation B, then A "synchronizes
before" B. Additionally, all the atomic operations executed in a program
behave as though executed in some sequentially consistent order. This
definition provides the same semantics as C++\'s sequentially consistent
atomics and Java\'s volatile variables.

Index
-----

- [func AddInt32(addr \*int32, delta int32) (new int32)](#AddInt32)
- [func AddInt64(addr \*int64, delta int64) (new int64)](#AddInt64)
- [func AddUint32(addr \*uint32, delta uint32) (new
    uint32)](#AddUint32)
- [func AddUint64(addr \*uint64, delta uint64) (new
    uint64)](#AddUint64)
- [func AddUintptr(addr \*uintptr, delta uintptr) (new
    uintptr)](#AddUintptr)
- [func CompareAndSwapInt32(addr \*int32, old, new int32) (swapped
    bool)](#CompareAndSwapInt32)
- [func CompareAndSwapInt64(addr \*int64, old, new int64) (swapped
    bool)](#CompareAndSwapInt64)
- [func CompareAndSwapPointer(addr \*unsafe.Pointer, old, new
    unsafe.Pointer) (swapped bool)](#CompareAndSwapPointer)
- [func CompareAndSwapUint32(addr \*uint32, old, new uint32) (swapped
    bool)](#CompareAndSwapUint32)
- [func CompareAndSwapUint64(addr \*uint64, old, new uint64) (swapped
    bool)](#CompareAndSwapUint64)
- [func CompareAndSwapUintptr(addr \*uintptr, old, new uintptr)
    (swapped bool)](#CompareAndSwapUintptr)
- [func LoadInt32(addr \*int32) (val int32)](#LoadInt32)
- [func LoadInt64(addr \*int64) (val int64)](#LoadInt64)
- [func LoadPointer(addr \*unsafe.Pointer) (val
    unsafe.Pointer)](#LoadPointer)
- [func LoadUint32(addr \*uint32) (val uint32)](#LoadUint32)
- [func LoadUint64(addr \*uint64) (val uint64)](#LoadUint64)
- [func LoadUintptr(addr \*uintptr) (val uintptr)](#LoadUintptr)
- [func StoreInt32(addr \*int32, val int32)](#StoreInt32)
- [func StoreInt64(addr \*int64, val int64)](#StoreInt64)
- [func StorePointer(addr \*unsafe.Pointer, val
    unsafe.Pointer)](#StorePointer)
- [func StoreUint32(addr \*uint32, val uint32)](#StoreUint32)
- [func StoreUint64(addr \*uint64, val uint64)](#StoreUint64)
- [func StoreUintptr(addr \*uintptr, val uintptr)](#StoreUintptr)
- [func SwapInt32(addr \*int32, new int32) (old int32)](#SwapInt32)
- [func SwapInt64(addr \*int64, new int64) (old int64)](#SwapInt64)
- [func SwapPointer(addr \*unsafe.Pointer, new unsafe.Pointer) (old
    unsafe.Pointer)](#SwapPointer)
- [func SwapUint32(addr \*uint32, new uint32) (old
    uint32)](#SwapUint32)
- [func SwapUint64(addr \*uint64, new uint64) (old
    uint64)](#SwapUint64)
- [func SwapUintptr(addr \*uintptr, new uintptr) (old
    uintptr)](#SwapUintptr)
- [type Bool](#Bool)
- [func (x \*Bool) CompareAndSwap(old, new bool) (swapped
    bool)](#Bool.CompareAndSwap)
- [func (x \*Bool) Load() bool](#Bool.Load)
- [func (x \*Bool) Store(val bool)](#Bool.Store)
- [func (x \*Bool) Swap(new bool) (old bool)](#Bool.Swap)
- [type Int32](#Int32)
- [func (x \*Int32) Add(delta int32) (new int32)](#Int32.Add)
- [func (x \*Int32) CompareAndSwap(old, new int32) (swapped
    bool)](#Int32.CompareAndSwap)
- [func (x \*Int32) Load() int32](#Int32.Load)
- [func (x \*Int32) Store(val int32)](#Int32.Store)
- [func (x \*Int32) Swap(new int32) (old int32)](#Int32.Swap)
- [type Int64](#Int64)
- [func (x \*Int64) Add(delta int64) (new int64)](#Int64.Add)
- [func (x \*Int64) CompareAndSwap(old, new int64) (swapped
    bool)](#Int64.CompareAndSwap)
- [func (x \*Int64) Load() int64](#Int64.Load)
- [func (x \*Int64) Store(val int64)](#Int64.Store)
- [func (x \*Int64) Swap(new int64) (old int64)](#Int64.Swap)
- [type Pointer](#Pointer)
- [func (x \*Pointer\[T\]) CompareAndSwap(old, new \*T) (swapped
    bool)](#Pointer.CompareAndSwap)
- [func (x \*Pointer\[T\]) Load() \*T](#Pointer.Load)
- [func (x \*Pointer\[T\]) Store(val \*T)](#Pointer.Store)
- [func (x \*Pointer\[T\]) Swap(new \*T) (old \*T)](#Pointer.Swap)
- [type Uint32](#Uint32)
- [func (x \*Uint32) Add(delta uint32) (new uint32)](#Uint32.Add)
- [func (x \*Uint32) CompareAndSwap(old, new uint32) (swapped
    bool)](#Uint32.CompareAndSwap)
- [func (x \*Uint32) Load() uint32](#Uint32.Load)
- [func (x \*Uint32) Store(val uint32)](#Uint32.Store)
- [func (x \*Uint32) Swap(new uint32) (old uint32)](#Uint32.Swap)
- [type Uint64](#Uint64)
- [func (x \*Uint64) Add(delta uint64) (new uint64)](#Uint64.Add)
- [func (x \*Uint64) CompareAndSwap(old, new uint64) (swapped
    bool)](#Uint64.CompareAndSwap)
- [func (x \*Uint64) Load() uint64](#Uint64.Load)
- [func (x \*Uint64) Store(val uint64)](#Uint64.Store)
- [func (x \*Uint64) Swap(new uint64) (old uint64)](#Uint64.Swap)
- [type Uintptr](#Uintptr)
- [func (x \*Uintptr) Add(delta uintptr) (new uintptr)](#Uintptr.Add)
- [func (x \*Uintptr) CompareAndSwap(old, new uintptr) (swapped
    bool)](#Uintptr.CompareAndSwap)
- [func (x \*Uintptr) Load() uintptr](#Uintptr.Load)
- [func (x \*Uintptr) Store(val uintptr)](#Uintptr.Store)
- [func (x \*Uintptr) Swap(new uintptr) (old uintptr)](#Uintptr.Swap)
- [type Value](#Value)
- [func (v \*Value) CompareAndSwap(old, new any) (swapped
    bool)](#Value.CompareAndSwap)
- [func (v \*Value) Load() (val any)](#Value.Load)
- [func (v \*Value) Store(val any)](#Value.Store)
- [func (v \*Value) Swap(new any) (old any)](#Value.Swap)
- [Bugs](#pkg-note-BUG)

### Examples

[Value (Config)](#example_Value_config)

[Value (ReadMostly)](#example_Value_readMostly)

### Package files

doc.go type.go value.go

func AddInt32
-------------

```go
func AddInt32(addr *int32, delta int32) (new int32)
```

AddInt32 atomically adds delta to \*addr and returns the new value.
Consider using the more ergonomic and less error-prone
[Int32.Add](#Int32.Add) instead.

func AddInt64
-------------

```go
func AddInt64(addr *int64, delta int64) (new int64)
```

AddInt64 atomically adds delta to \*addr and returns the new value.
Consider using the more ergonomic and less error-prone
[Int64.Add](#Int64.Add) instead (particularly if you target 32-bit
platforms; see the bugs section).

func AddUint32
--------------

```go
func AddUint32(addr *uint32, delta uint32) (new uint32)
```

AddUint32 atomically adds delta to \*addr and returns the new value. To
subtract a signed positive constant value c from x, do AddUint32(&x,
\^uint32(c-1)). In particular, to decrement x, do AddUint32(&x,
\^uint32(0)). Consider using the more ergonomic and less error-prone
[Uint32.Add](#Uint32.Add) instead.

func AddUint64
--------------

```go
func AddUint64(addr *uint64, delta uint64) (new uint64)
```

AddUint64 atomically adds delta to \*addr and returns the new value. To
subtract a signed positive constant value c from x, do AddUint64(&x,
\^uint64(c-1)). In particular, to decrement x, do AddUint64(&x,
\^uint64(0)). Consider using the more ergonomic and less error-prone
[Uint64.Add](#Uint64.Add) instead (particularly if you target 32-bit
platforms; see the bugs section).

func AddUintptr
---------------

```go
func AddUintptr(addr *uintptr, delta uintptr) (new uintptr)
```

AddUintptr atomically adds delta to \*addr and returns the new value.
Consider using the more ergonomic and less error-prone
[Uintptr.Add](#Uintptr.Add) instead.

func CompareAndSwapInt32
------------------------

```go
func CompareAndSwapInt32(addr *int32, old, new int32) (swapped bool)
```

CompareAndSwapInt32 executes the compare-and-swap operation for an int32
value. Consider using the more ergonomic and less error-prone
[Int32.CompareAndSwap](#Int32.CompareAndSwap) instead.

func CompareAndSwapInt64
------------------------

```go
func CompareAndSwapInt64(addr *int64, old, new int64) (swapped bool)
```

CompareAndSwapInt64 executes the compare-and-swap operation for an int64
value. Consider using the more ergonomic and less error-prone
[Int64.CompareAndSwap](#Int64.CompareAndSwap) instead (particularly if
you target 32-bit platforms; see the bugs section).

func CompareAndSwapPointer
--------------------------

```go
func CompareAndSwapPointer(addr *unsafe.Pointer, old, new unsafe.Pointer) (swapped bool)
```

CompareAndSwapPointer executes the compare-and-swap operation for a
unsafe.Pointer value. Consider using the more ergonomic and less
error-prone [Pointer.CompareAndSwap](#Pointer.CompareAndSwap) instead.

func CompareAndSwapUint32
-------------------------

```go
func CompareAndSwapUint32(addr *uint32, old, new uint32) (swapped bool)
```

CompareAndSwapUint32 executes the compare-and-swap operation for a
uint32 value. Consider using the more ergonomic and less error-prone
[Uint32.CompareAndSwap](#Uint32.CompareAndSwap) instead.

func CompareAndSwapUint64
-------------------------

```go
func CompareAndSwapUint64(addr *uint64, old, new uint64) (swapped bool)
```

CompareAndSwapUint64 executes the compare-and-swap operation for a
uint64 value. Consider using the more ergonomic and less error-prone
[Uint64.CompareAndSwap](#Uint64.CompareAndSwap) instead (particularly if
you target 32-bit platforms; see the bugs section).

func CompareAndSwapUintptr
--------------------------

```go
func CompareAndSwapUintptr(addr *uintptr, old, new uintptr) (swapped bool)
```

CompareAndSwapUintptr executes the compare-and-swap operation for a
uintptr value. Consider using the more ergonomic and less error-prone
[Uintptr.CompareAndSwap](#Uintptr.CompareAndSwap) instead.

func LoadInt32
--------------

```go
func LoadInt32(addr *int32) (val int32)
```

LoadInt32 atomically loads \*addr. Consider using the more ergonomic and
less error-prone [Int32.Load](#Int32.Load) instead.

func LoadInt64
--------------

```go
func LoadInt64(addr *int64) (val int64)
```

LoadInt64 atomically loads \*addr. Consider using the more ergonomic and
less error-prone [Int64.Load](#Int64.Load) instead (particularly if you
target 32-bit platforms; see the bugs section).

func LoadPointer
----------------

```go
func LoadPointer(addr *unsafe.Pointer) (val unsafe.Pointer)
```

LoadPointer atomically loads \*addr. Consider using the more ergonomic
and less error-prone [Pointer.Load](#Pointer.Load) instead.

func LoadUint32
---------------

```go
func LoadUint32(addr *uint32) (val uint32)
```

LoadUint32 atomically loads \*addr. Consider using the more ergonomic
and less error-prone [Uint32.Load](#Uint32.Load) instead.

func LoadUint64
---------------

```go
func LoadUint64(addr *uint64) (val uint64)
```

LoadUint64 atomically loads \*addr. Consider using the more ergonomic
and less error-prone [Uint64.Load](#Uint64.Load) instead (particularly
if you target 32-bit platforms; see the bugs section).

func LoadUintptr
----------------

```go
func LoadUintptr(addr *uintptr) (val uintptr)
```

LoadUintptr atomically loads \*addr. Consider using the more ergonomic
and less error-prone [Uintptr.Load](#Uintptr.Load) instead.

func StoreInt32
---------------

```go
func StoreInt32(addr *int32, val int32)
```

StoreInt32 atomically stores val into \*addr. Consider using the more
ergonomic and less error-prone [Int32.Store](#Int32.Store) instead.

func StoreInt64
---------------

```go
func StoreInt64(addr *int64, val int64)
```

StoreInt64 atomically stores val into \*addr. Consider using the more
ergonomic and less error-prone [Int64.Store](#Int64.Store) instead
(particularly if you target 32-bit platforms; see the bugs section).

func StorePointer
-----------------

```go
func StorePointer(addr *unsafe.Pointer, val unsafe.Pointer)
```

StorePointer atomically stores val into \*addr. Consider using the more
ergonomic and less error-prone [Pointer.Store](#Pointer.Store) instead.

func StoreUint32
----------------

```go
func StoreUint32(addr *uint32, val uint32)
```

StoreUint32 atomically stores val into \*addr. Consider using the more
ergonomic and less error-prone [Uint32.Store](#Uint32.Store) instead.

func StoreUint64
----------------

```go
func StoreUint64(addr *uint64, val uint64)
```

StoreUint64 atomically stores val into \*addr. Consider using the more
ergonomic and less error-prone [Uint64.Store](#Uint64.Store) instead
(particularly if you target 32-bit platforms; see the bugs section).

func StoreUintptr
-----------------

```go
func StoreUintptr(addr *uintptr, val uintptr)
```

StoreUintptr atomically stores val into \*addr. Consider using the more
ergonomic and less error-prone [Uintptr.Store](#Uintptr.Store) instead.

func SwapInt32
---------------------------------------------

```go
func SwapInt32(addr *int32, new int32) (old int32)
```

SwapInt32 atomically stores new into \*addr and returns the previous
\*addr value. Consider using the more ergonomic and less error-prone
[Int32.Swap](#Int32.Swap) instead.

func SwapInt64
---------------------------------------------

```go
func SwapInt64(addr *int64, new int64) (old int64)
```

SwapInt64 atomically stores new into \*addr and returns the previous
\*addr value. Consider using the more ergonomic and less error-prone
[Int64.Swap](#Int64.Swap) instead (particularly if you target 32-bit
platforms; see the bugs section).

func SwapPointer
-----------------------------------------------

```go
func SwapPointer(addr *unsafe.Pointer, new unsafe.Pointer) (old unsafe.Pointer)
```

SwapPointer atomically stores new into \*addr and returns the previous
\*addr value. Consider using the more ergonomic and less error-prone
[Pointer.Swap](#Pointer.Swap) instead.

func SwapUint32
----------------------------------------------

```go
func SwapUint32(addr *uint32, new uint32) (old uint32)
```

SwapUint32 atomically stores new into \*addr and returns the previous
\*addr value. Consider using the more ergonomic and less error-prone
[Uint32.Swap](#Uint32.Swap) instead.

func SwapUint64
----------------------------------------------

```go
func SwapUint64(addr *uint64, new uint64) (old uint64)
```

SwapUint64 atomically stores new into \*addr and returns the previous
\*addr value. Consider using the more ergonomic and less error-prone
[Uint64.Swap](#Uint64.Swap) instead (particularly if you target 32-bit
platforms; see the bugs section).

func SwapUintptr
-----------------------------------------------

```go
func SwapUintptr(addr *uintptr, new uintptr) (old uintptr)
```

SwapUintptr atomically stores new into \*addr and returns the previous
\*addr value. Consider using the more ergonomic and less error-prone
[Uintptr.Swap](#Uintptr.Swap) instead.

type Bool
------------------------------------------

A Bool is an atomic boolean value. The zero value is false.

```go
type Bool struct {
    // contains filtered or unexported fields
}
```

### func (\*Bool) CompareAndSwap

```go
func (x *Bool) CompareAndSwap(old, new bool) (swapped bool)
```

CompareAndSwap executes the compare-and-swap operation for the boolean
value x.

### func (\*Bool) Load

```go
func (x *Bool) Load() bool
```

Load atomically loads and returns the value stored in x.

### func (\*Bool) Store

```go
func (x *Bool) Store(val bool)
```

Store atomically stores val into x.

### func (\*Bool) Swap

```go
func (x *Bool) Swap(new bool) (old bool)
```

Swap atomically stores new into x and returns the previous value.

type Int32
-------------------------------------------

An Int32 is an atomic int32. The zero value is zero.

```go
type Int32 struct {
    // contains filtered or unexported fields
}
```

### func (\*Int32) Add

```go
func (x *Int32) Add(delta int32) (new int32)
```

Add atomically adds delta to x and returns the new value.

### func (\*Int32) CompareAndSwap

```go
func (x *Int32) CompareAndSwap(old, new int32) (swapped bool)
```

CompareAndSwap executes the compare-and-swap operation for x.

### func (\*Int32) Load

```go
func (x *Int32) Load() int32
```

Load atomically loads and returns the value stored in x.

### func (\*Int32) Store

```go
func (x *Int32) Store(val int32)
```

Store atomically stores val into x.

### func (\*Int32) Swap

```go
func (x *Int32) Swap(new int32) (old int32)
```

Swap atomically stores new into x and returns the previous value.

type Int64
-------------------------------------------

An Int64 is an atomic int64. The zero value is zero.

```go
type Int64 struct {
    // contains filtered or unexported fields
}
```

### func (\*Int64) Add

```go
func (x *Int64) Add(delta int64) (new int64)
```

Add atomically adds delta to x and returns the new value.

### func (\*Int64) CompareAndSwap

```go
func (x *Int64) CompareAndSwap(old, new int64) (swapped bool)
```

CompareAndSwap executes the compare-and-swap operation for x.

### func (\*Int64) Load

```go
func (x *Int64) Load() int64
```

Load atomically loads and returns the value stored in x.

### func (\*Int64) Store

```go
func (x *Int64) Store(val int64)
```

Store atomically stores val into x.

### func (\*Int64) Swap

```go
func (x *Int64) Swap(new int64) (old int64)
```

Swap atomically stores new into x and returns the previous value.

type Pointer
------------

A Pointer is an atomic pointer of type \*T. The zero value is a nil \*T.

```go
type Pointer[T any] struct {
    // contains filtered or unexported fields
}
```

### func (\*Pointer\[T\]) CompareAndSwap

```go
func (x *Pointer[T]) CompareAndSwap(old, new *T) (swapped bool)
```

CompareAndSwap executes the compare-and-swap operation for x.

### func (\*Pointer\[T\]) Load

```go
func (x *Pointer[T]) Load() *T
```

Load atomically loads and returns the value stored in x.

### func (\*Pointer\[T\]) Store

```go
func (x *Pointer[T]) Store(val *T)
```

Store atomically stores val into x.

### func (\*Pointer\[T\]) Swap

```go
func (x *Pointer[T]) Swap(new *T) (old *T)
```

Swap atomically stores new into x and returns the previous value.

type Uint32
--------------------------------------------

A Uint32 is an atomic uint32. The zero value is zero.

```go
type Uint32 struct {
    // contains filtered or unexported fields
}
```

### func (\*Uint32) Add

```go
func (x *Uint32) Add(delta uint32) (new uint32)
```

Add atomically adds delta to x and returns the new value.

### func (\*Uint32) CompareAndSwap

```go
func (x *Uint32) CompareAndSwap(old, new uint32) (swapped bool)
```

CompareAndSwap executes the compare-and-swap operation for x.

### func (\*Uint32) Load

```go
func (x *Uint32) Load() uint32
```

Load atomically loads and returns the value stored in x.

### func (\*Uint32) Store

```go
func (x *Uint32) Store(val uint32)
```

Store atomically stores val into x.

### func (\*Uint32) Swap

```go
func (x *Uint32) Swap(new uint32) (old uint32)
```

Swap atomically stores new into x and returns the previous value.

type Uint64
--------------------------------------------

A Uint64 is an atomic uint64. The zero value is zero.

```go
type Uint64 struct {
    // contains filtered or unexported fields
}
```

### func (\*Uint64) Add

```go
func (x *Uint64) Add(delta uint64) (new uint64)
```

Add atomically adds delta to x and returns the new value.

### func (\*Uint64) CompareAndSwap

```go
func (x *Uint64) CompareAndSwap(old, new uint64) (swapped bool)
```

CompareAndSwap executes the compare-and-swap operation for x.

### func (\*Uint64) Load

```go
func (x *Uint64) Load() uint64
```

Load atomically loads and returns the value stored in x.

### func (\*Uint64) Store

```go
func (x *Uint64) Store(val uint64)
```

Store atomically stores val into x.

### func (\*Uint64) Swap

```go
func (x *Uint64) Swap(new uint64) (old uint64)
```

Swap atomically stores new into x and returns the previous value.

type Uintptr
---------------------------------------------

A Uintptr is an atomic uintptr. The zero value is zero.

```go
type Uintptr struct {
    // contains filtered or unexported fields
}
```

### func (\*Uintptr) Add

```go
func (x *Uintptr) Add(delta uintptr) (new uintptr)
```

Add atomically adds delta to x and returns the new value.

### func (\*Uintptr) CompareAndSwap

```go
func (x *Uintptr) CompareAndSwap(old, new uintptr) (swapped bool)
```

CompareAndSwap executes the compare-and-swap operation for x.

### func (\*Uintptr) Load

```go
func (x *Uintptr) Load() uintptr
```

Load atomically loads and returns the value stored in x.

### func (\*Uintptr) Store

```go
func (x *Uintptr) Store(val uintptr)
```

Store atomically stores val into x.

### func (\*Uintptr) Swap

```go
func (x *Uintptr) Swap(new uintptr) (old uintptr)
```

Swap atomically stores new into x and returns the previous value.

type Value
-----------------------------------------

A Value provides an atomic load and store of a consistently typed value.
The zero value for a Value returns nil from Load. Once Store has been
called, a Value must not be copied.

A Value must not be copied after first use.

```go
type Value struct {
    // contains filtered or unexported fields
}
```

#### [Example (Config)]

The following example shows how to use Value for periodic program config
updates and propagation of the changes to worker goroutines.

Code:

```go
var config atomic.Value // holds current server configuration
// Create initial config value and store into config.
config.Store(loadConfig())
go func() {
    // Reload config every 10 seconds
    // and update config value with the new version.
    for {
        time.Sleep(10 * time.Second)
        config.Store(loadConfig())
    }
}()
// Create worker goroutines that handle incoming requests
// using the latest config value.
for i := 0; i < 10; i++ {
    go func() {
        for r := range requests() {
            c := config.Load()
            // Handle request r using config c.
            _, _ = r, c
        }
    }()
}
```

#### [Example (ReadMostly)]

The following example shows how to maintain a scalable frequently read,
but infrequently updated data structure using copy-on-write idiom.

Code:

```go
type Map map[string]string
var m atomic.Value
m.Store(make(Map))
var mu sync.Mutex // used only by writers
// read function can be used to read the data without further synchronization
read := func(key string) (val string) {
    m1 := m.Load().(Map)
    return m1[key]
}
// insert function can be used to update the data without further synchronization
insert := func(key, val string) {
    mu.Lock() // synchronize with other potential writers
    defer mu.Unlock()
    m1 := m.Load().(Map) // load current value of the data structure
    m2 := make(Map)      // create a new value
    for k, v := range m1 {
        m2[k] = v // copy all data from the current object to the new one
    }
    m2[key] = val // do the update that we need
    m.Store(m2)   // atomically replace the current object with the new one
    // At this point all new readers start working with the new version.
    // The old version will be garbage collected once the existing readers
    // (if any) are done with it.
}
_, _ = read, insert
```

### func (\*Value) CompareAndSwap

```go
func (v *Value) CompareAndSwap(old, new any) (swapped bool)
```

CompareAndSwap executes the compare-and-swap operation for the Value.

All calls to CompareAndSwap for a given Value must use values of the
same concrete type. CompareAndSwap of an inconsistent type panics, as
does CompareAndSwap(old, nil).

### func (\*Value) Load

```go
func (v *Value) Load() (val any)
```

Load returns the value set by the most recent Store. It returns nil if
there has been no call to Store for this Value.

### func (\*Value) Store

```go
func (v *Value) Store(val any)
```

Store sets the value of the Value v to val. All calls to Store for a
given Value must use values of the same concrete type. Store of an
inconsistent type panics, as does Store(nil).

### func (\*Value) Swap

```go
func (v *Value) Swap(new any) (old any)
```

Swap stores new into Value and returns the previous value. It returns
nil if the Value is empty.

All calls to Swap for a given Value must use values of the same concrete
type. Swap of an inconsistent type panics, as does Swap(nil).

Bugs
----

-

    On 386, the 64-bit functions use instructions unavailable before the
    Pentium MMX.

    On non-Linux ARM, the 64-bit functions use instructions unavailable
    before the ARMv6k core.

    On ARM, 386, and 32-bit MIPS, it is the caller\'s responsibility to
    arrange for 64-bit alignment of 64-bit words accessed atomically via
    the primitive atomic functions (types [Int64](#Int64) and
    [Uint64](#Uint64) are automatically aligned). The first word in an
    allocated struct, array, or slice; in a global variable; or in a
    local variable (because the subject of all atomic operations will
    escape to the heap) can be relied upon to be 64-bit aligned.

© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/sync/atomic/>
