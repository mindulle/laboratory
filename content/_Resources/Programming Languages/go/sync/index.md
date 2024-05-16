Package sync
============

-   `import "sync"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)
-   [Subdirectories](#pkg-subdirectories)

Overview 
--------

Package sync provides basic synchronization primitives such as mutual
exclusion locks. Other than the Once and WaitGroup types, most are
intended for use by low-level library routines. Higher-level
synchronization is better done via channels and communication.

Values containing the types defined in this package should not be
copied.

Index 
-----

-   [func OnceFunc(f func()) func()](#OnceFunc)
-   [func OnceValue\[T any\](f func() T) func() T](#OnceValue)
-   [func OnceValues\[T1, T2 any\](f func() (T1, T2)) func() (T1,
    T2)](#OnceValues)
-   [type Cond](#Cond)
-   [func NewCond(l Locker) \*Cond](#NewCond)
-   [func (c \*Cond) Broadcast()](#Cond.Broadcast)
-   [func (c \*Cond) Signal()](#Cond.Signal)
-   [func (c \*Cond) Wait()](#Cond.Wait)
-   [type Locker](#Locker)
-   [type Map](#Map)
-   [func (m \*Map) CompareAndDelete(key, old any) (deleted
    bool)](#Map.CompareAndDelete)
-   [func (m \*Map) CompareAndSwap(key, old, new any)
    bool](#Map.CompareAndSwap)
-   [func (m \*Map) Delete(key any)](#Map.Delete)
-   [func (m \*Map) Load(key any) (value any, ok bool)](#Map.Load)
-   [func (m \*Map) LoadAndDelete(key any) (value any, loaded
    bool)](#Map.LoadAndDelete)
-   [func (m \*Map) LoadOrStore(key, value any) (actual any, loaded
    bool)](#Map.LoadOrStore)
-   [func (m \*Map) Range(f func(key, value any) bool)](#Map.Range)
-   [func (m \*Map) Store(key, value any)](#Map.Store)
-   [func (m \*Map) Swap(key, value any) (previous any, loaded
    bool)](#Map.Swap)
-   [type Mutex](#Mutex)
-   [func (m \*Mutex) Lock()](#Mutex.Lock)
-   [func (m \*Mutex) TryLock() bool](#Mutex.TryLock)
-   [func (m \*Mutex) Unlock()](#Mutex.Unlock)
-   [type Once](#Once)
-   [func (o \*Once) Do(f func())](#Once.Do)
-   [type Pool](#Pool)
-   [func (p \*Pool) Get() any](#Pool.Get)
-   [func (p \*Pool) Put(x any)](#Pool.Put)
-   [type RWMutex](#RWMutex)
-   [func (rw \*RWMutex) Lock()](#RWMutex.Lock)
-   [func (rw \*RWMutex) RLock()](#RWMutex.RLock)
-   [func (rw \*RWMutex) RLocker() Locker](#RWMutex.RLocker)
-   [func (rw \*RWMutex) RUnlock()](#RWMutex.RUnlock)
-   [func (rw \*RWMutex) TryLock() bool](#RWMutex.TryLock)
-   [func (rw \*RWMutex) TryRLock() bool](#RWMutex.TryRLock)
-   [func (rw \*RWMutex) Unlock()](#RWMutex.Unlock)
-   [type WaitGroup](#WaitGroup)
-   [func (wg \*WaitGroup) Add(delta int)](#WaitGroup.Add)
-   [func (wg \*WaitGroup) Done()](#WaitGroup.Done)
-   [func (wg \*WaitGroup) Wait()](#WaitGroup.Wait)

 
### Examples

[Once](#example_Once)

[Pool](#example_Pool)

[WaitGroup](#example_WaitGroup)


### Package files

cond.go map.go mutex.go once.go oncefunc.go pool.go poolqueue.go
runtime.go runtime2.go rwmutex.go waitgroup.go

func OnceFunc 
----------------------------------------------

```go
func OnceFunc(f func()) func()
```

OnceFunc returns a function that invokes f only once. The returned
function may be called concurrently.

If f panics, the returned function will panic with the same value on
every call.

func OnceValue 
--------------

```go
func OnceValue[T any](f func() T) func() T
```

OnceValue returns a function that invokes f only once and returns the
value returned by f. The returned function may be called concurrently.

If f panics, the returned function will panic with the same value on
every call.

func OnceValues 
---------------

```go
func OnceValues[T1, T2 any](f func() (T1, T2)) func() (T1, T2)
```

OnceValues returns a function that invokes f only once and returns the
values returned by f. The returned function may be called concurrently.

If f panics, the returned function will panic with the same value on
every call.

type Cond 
---------

Cond implements a condition variable, a rendezvous point for goroutines
waiting for or announcing the occurrence of an event.

Each Cond has an associated Locker L (often a \*Mutex or \*RWMutex),
which must be held when changing the condition and when calling the Wait
method.

A Cond must not be copied after first use.

In the terminology of the Go memory model, Cond arranges that a call to
Broadcast or Signal "synchronizes before" any Wait call that it
unblocks.

For many simple use cases, users will be better off using channels than
a Cond (Broadcast corresponds to closing a channel, and Signal
corresponds to sending on a channel).

For more on replacements for sync.Cond, see [Roberto Clapis\'s series on
advanced concurrency
patterns](https://blogtitle.github.io/categories/concurrency/), as well
as [Bryan Mills\'s talk on concurrency
patterns](https://drive.google.com/file/d/1nPdvhB0PutEJzdCq5ms6UI58dp50fcAN/view).

```go
type Cond struct {

    // L is held while observing or changing the condition
    L Locker
    // contains filtered or unexported fields
}
```

### func NewCond 

```go
func NewCond(l Locker) *Cond
```

NewCond returns a new Cond with Locker l.

### func (\*Cond) Broadcast 

```go
func (c *Cond) Broadcast()
```

Broadcast wakes all goroutines waiting on c.

It is allowed but not required for the caller to hold c.L during the
call.

### func (\*Cond) Signal 

```go
func (c *Cond) Signal()
```

Signal wakes one goroutine waiting on c, if there is any.

It is allowed but not required for the caller to hold c.L during the
call.

Signal() does not affect goroutine scheduling priority; if other
goroutines are attempting to lock c.L, they may be awoken before a
\"waiting\" goroutine.

### func (\*Cond) Wait 

```go
func (c *Cond) Wait()
```

Wait atomically unlocks c.L and suspends execution of the calling
goroutine. After later resuming execution, Wait locks c.L before
returning. Unlike in other systems, Wait cannot return unless awoken by
Broadcast or Signal.

Because c.L is not locked while Wait is waiting, the caller typically
cannot assume that the condition is true when Wait returns. Instead, the
caller should Wait in a loop:

```go
c.L.Lock()
for !condition() {
    c.Wait()
}
... make use of condition ...
c.L.Unlock()
```

type Locker 
-----------

A Locker represents an object that can be locked and unlocked.

```go
type Locker interface {
    Lock()
    Unlock()
}
```

type Map 
---------------------------------------

Map is like a Go map\[interface{}\]interface{} but is safe for
concurrent use by multiple goroutines without additional locking or
coordination. Loads, stores, and deletes run in amortized constant time.

The Map type is specialized. Most code should use a plain Go map
instead, with separate locking or coordination, for better type safety
and to make it easier to maintain other invariants along with the map
content.

The Map type is optimized for two common use cases: (1) when the entry
for a given key is only ever written once but read many times, as in
caches that only grow, or (2) when multiple goroutines read, write, and
overwrite entries for disjoint sets of keys. In these two cases, use of
a Map may significantly reduce lock contention compared to a Go map
paired with a separate Mutex or RWMutex.

The zero Map is empty and ready for use. A Map must not be copied after
first use.

In the terminology of the Go memory model, Map arranges that a write
operation "synchronizes before" any read operation that observes the
effect of the write, where read and write operations are defined as
follows. Load, LoadAndDelete, LoadOrStore, Swap, CompareAndSwap, and
CompareAndDelete are read operations; Delete, LoadAndDelete, Store, and
Swap are write operations; LoadOrStore is a write operation when it
returns loaded set to false; CompareAndSwap is a write operation when it
returns swapped set to true; and CompareAndDelete is a write operation
when it returns deleted set to true.

```go
type Map struct {
    // contains filtered or unexported fields
}
```

### func (\*Map) CompareAndDelete 

```go
func (m *Map) CompareAndDelete(key, old any) (deleted bool)
```

CompareAndDelete deletes the entry for key if its value is equal to old.
The old value must be of a comparable type.

If there is no current value for key in the map, CompareAndDelete
returns false (even if the old value is the nil interface value).

### func (\*Map) CompareAndSwap 

```go
func (m *Map) CompareAndSwap(key, old, new any) bool
```

CompareAndSwap swaps the old and new values for key if the value stored
in the map is equal to old. The old value must be of a comparable type.

### func (\*Map) Delete 

```go
func (m *Map) Delete(key any)
```

Delete deletes the value for a key.

### func (\*Map) Load 

```go
func (m *Map) Load(key any) (value any, ok bool)
```

Load returns the value stored in the map for a key, or nil if no value
is present. The ok result indicates whether value was found in the map.

### func (\*Map) LoadAndDelete 

```go
func (m *Map) LoadAndDelete(key any) (value any, loaded bool)
```

LoadAndDelete deletes the value for a key, returning the previous value
if any. The loaded result reports whether the key was present.

### func (\*Map) LoadOrStore 

```go
func (m *Map) LoadOrStore(key, value any) (actual any, loaded bool)
```

LoadOrStore returns the existing value for the key if present.
Otherwise, it stores and returns the given value. The loaded result is
true if the value was loaded, false if stored.

### func (\*Map) Range 

```go
func (m *Map) Range(f func(key, value any) bool)
```

Range calls f sequentially for each key and value present in the map. If
f returns false, range stops the iteration.

Range does not necessarily correspond to any consistent snapshot of the
Map\'s contents: no key will be visited more than once, but if the value
for any key is stored or deleted concurrently (including by f), Range
may reflect any mapping for that key from any point during the Range
call. Range does not block other methods on the receiver; even f itself
may call any method on m.

Range may be O(N) with the number of elements in the map even if f
returns false after a constant number of calls.

### func (\*Map) Store 

```go
func (m *Map) Store(key, value any)
```

Store sets the value for a key.

### func (\*Map) Swap 

```go
func (m *Map) Swap(key, value any) (previous any, loaded bool)
```

Swap swaps the value for a key and returns the previous value if any.
The loaded result reports whether the key was present.

type Mutex 
----------

A Mutex is a mutual exclusion lock. The zero value for a Mutex is an
unlocked mutex.

A Mutex must not be copied after first use.

In the terminology of the Go memory model, the n\'th call to Unlock
"synchronizes before" the m\'th call to Lock for any n \< m. A
successful call to TryLock is equivalent to a call to Lock. A failed
call to TryLock does not establish any "synchronizes before" relation at
all.

```go
type Mutex struct {
    // contains filtered or unexported fields
}
```

### func (\*Mutex) Lock 

```go
func (m *Mutex) Lock()
```

Lock locks m. If the lock is already in use, the calling goroutine
blocks until the mutex is available.

### func (\*Mutex) TryLock 

```go
func (m *Mutex) TryLock() bool
```

TryLock tries to lock m and reports whether it succeeded.

Note that while correct uses of TryLock do exist, they are rare, and use
of TryLock is often a sign of a deeper problem in a particular use of
mutexes.

### func (\*Mutex) Unlock 

```go
func (m *Mutex) Unlock()
```

Unlock unlocks m. It is a run-time error if m is not locked on entry to
Unlock.

A locked Mutex is not associated with a particular goroutine. It is
allowed for one goroutine to lock a Mutex and then arrange for another
goroutine to unlock it.

type Once 
---------

Once is an object that will perform exactly one action.

A Once must not be copied after first use.

In the terminology of the Go memory model, the return from f
"synchronizes before" the return from any call of once.Do(f).

```go
type Once struct {
    // contains filtered or unexported fields
}
```

#### [Example]

Code:

```go
var once sync.Once
onceBody := func() {
    fmt.Println("Only once")
}
done := make(chan bool)
for i := 0; i < 10; i++ {
    go func() {
        once.Do(onceBody)
        done <- true
    }()
}
for i := 0; i < 10; i++ {
    <-done
}
```

Output:

```go
Only once
```

### func (\*Once) Do 

```go
func (o *Once) Do(f func())
```

Do calls the function f if and only if Do is being called for the first
time for this instance of Once. In other words, given

```go
var once Once
```

if once.Do(f) is called multiple times, only the first call will invoke
f, even if f has a different value in each invocation. A new instance of
Once is required for each function to execute.

Do is intended for initialization that must be run exactly once. Since f
is niladic, it may be necessary to use a function literal to capture the
arguments to a function to be invoked by Do:

```go
config.once.Do(func() { config.init(filename) })
```

Because no call to Do returns until the one call to f returns, if f
causes Do to be called, it will deadlock.

If f panics, Do considers it to have returned; future calls of Do return
without calling f.

type Pool 
----------------------------------------

A Pool is a set of temporary objects that may be individually saved and
retrieved.

Any item stored in the Pool may be removed automatically at any time
without notification. If the Pool holds the only reference when this
happens, the item might be deallocated.

A Pool is safe for use by multiple goroutines simultaneously.

Pool\'s purpose is to cache allocated but unused items for later reuse,
relieving pressure on the garbage collector. That is, it makes it easy
to build efficient, thread-safe free lists. However, it is not suitable
for all free lists.

An appropriate use of a Pool is to manage a group of temporary items
silently shared among and potentially reused by concurrent independent
clients of a package. Pool provides a way to amortize allocation
overhead across many clients.

An example of good use of a Pool is in the fmt package, which maintains
a dynamically-sized store of temporary output buffers. The store scales
under load (when many goroutines are actively printing) and shrinks when
quiescent.

On the other hand, a free list maintained as part of a short-lived
object is not a suitable use for a Pool, since the overhead does not
amortize well in that scenario. It is more efficient to have such
objects implement their own free list.

A Pool must not be copied after first use.

In the terminology of the Go memory model, a call to Put(x)
"synchronizes before" a call to Get returning that same value x.
Similarly, a call to New returning x "synchronizes before" a call to Get
returning that same value x.

```go
type Pool struct {

    // New optionally specifies a function to generate
    // a value when Get would otherwise return nil.
    // It may not be changed concurrently with calls to Get.
    New func() any
    // contains filtered or unexported fields
}
```

#### [Example]

Code:

```go
package sync_test

import (
    "bytes"
    "io"
    "os"
    "sync"
    "time"
)

var bufPool = sync.Pool{
    New: func() any {
        // The Pool's New function should generally only return pointer
        // types, since a pointer can be put into the return interface
        // value without an allocation:
        return new(bytes.Buffer)
    },
}

// timeNow is a fake version of time.Now for tests.
func timeNow() time.Time {
    return time.Unix(1136214245, 0)
}

func Log(w io.Writer, key, val string) {
    b := bufPool.Get().(*bytes.Buffer)
    b.Reset()
    // Replace this with time.Now() in a real logger.
    b.WriteString(timeNow().UTC().Format(time.RFC3339))
    b.WriteByte(' ')
    b.WriteString(key)
    b.WriteByte('=')
    b.WriteString(val)
    w.Write(b.Bytes())
    bufPool.Put(b)
}

func ExamplePool() {
    Log(os.Stdout, "path", "/search?q=flowers")
    // Output: 2006-01-02T15:04:05Z path=/search?q=flowers
}
```

### func (\*Pool) Get 

```go
func (p *Pool) Get() any
```

Get selects an arbitrary item from the Pool, removes it from the Pool,
and returns it to the caller. Get may choose to ignore the pool and
treat it as empty. Callers should not assume any relation between values
passed to Put and the values returned by Get.

If Get would otherwise return nil and p.New is non-nil, Get returns the
result of calling p.New.

### func (\*Pool) Put 

```go
func (p *Pool) Put(x any)
```

Put adds x to the pool.

type RWMutex 
------------

A RWMutex is a reader/writer mutual exclusion lock. The lock can be held
by an arbitrary number of readers or a single writer. The zero value for
a RWMutex is an unlocked mutex.

A RWMutex must not be copied after first use.

If a goroutine holds a RWMutex for reading and another goroutine might
call Lock, no goroutine should expect to be able to acquire a read lock
until the initial read lock is released. In particular, this prohibits
recursive read locking. This is to ensure that the lock eventually
becomes available; a blocked Lock call excludes new readers from
acquiring the lock.

In the terminology of the Go memory model, the n\'th call to Unlock
"synchronizes before" the m\'th call to Lock for any n \< m, just as for
Mutex. For any call to RLock, there exists an n such that the n\'th call
to Unlock "synchronizes before" that call to RLock, and the
corresponding call to RUnlock "synchronizes before" the n+1\'th call to
Lock.

```go
type RWMutex struct {
    // contains filtered or unexported fields
}
```

### func (\*RWMutex) Lock 

```go
func (rw *RWMutex) Lock()
```

Lock locks rw for writing. If the lock is already locked for reading or
writing, Lock blocks until the lock is available.

### func (\*RWMutex) RLock 

```go
func (rw *RWMutex) RLock()
```

RLock locks rw for reading.

It should not be used for recursive read locking; a blocked Lock call
excludes new readers from acquiring the lock. See the documentation on
the RWMutex type.

### func (\*RWMutex) RLocker 

```go
func (rw *RWMutex) RLocker() Locker
```

RLocker returns a Locker interface that implements the Lock and Unlock
methods by calling rw.RLock and rw.RUnlock.

### func (\*RWMutex) RUnlock 

```go
func (rw *RWMutex) RUnlock()
```

RUnlock undoes a single RLock call; it does not affect other
simultaneous readers. It is a run-time error if rw is not locked for
reading on entry to RUnlock.

### func (\*RWMutex) TryLock 

```go
func (rw *RWMutex) TryLock() bool
```

TryLock tries to lock rw for writing and reports whether it succeeded.

Note that while correct uses of TryLock do exist, they are rare, and use
of TryLock is often a sign of a deeper problem in a particular use of
mutexes.

### func (\*RWMutex) TryRLock 

```go
func (rw *RWMutex) TryRLock() bool
```

TryRLock tries to lock rw for reading and reports whether it succeeded.

Note that while correct uses of TryRLock do exist, they are rare, and
use of TryRLock is often a sign of a deeper problem in a particular use
of mutexes.

### func (\*RWMutex) Unlock 

```go
func (rw *RWMutex) Unlock()
```

Unlock unlocks rw for writing. It is a run-time error if rw is not
locked for writing on entry to Unlock.

As with Mutexes, a locked RWMutex is not associated with a particular
goroutine. One goroutine may RLock (Lock) a RWMutex and then arrange for
another goroutine to RUnlock (Unlock) it.

type WaitGroup 
--------------

A WaitGroup waits for a collection of goroutines to finish. The main
goroutine calls Add to set the number of goroutines to wait for. Then
each of the goroutines runs and calls Done when finished. At the same
time, Wait can be used to block until all goroutines have finished.

A WaitGroup must not be copied after first use.

In the terminology of the Go memory model, a call to Done "synchronizes
before" the return of any Wait call that it unblocks.

```go
type WaitGroup struct {
    // contains filtered or unexported fields
}
```

#### [Example]

This example fetches several URLs concurrently, using a WaitGroup to
block until all the fetches are complete.

Code:

```go
var wg sync.WaitGroup
var urls = []string{
    "http://www.golang.org/",
    "http://www.google.com/",
    "http://www.example.com/",
}
for _, url := range urls {
    // Increment the WaitGroup counter.
    wg.Add(1)
    // Launch a goroutine to fetch the URL.
    go func(url string) {
        // Decrement the counter when the goroutine completes.
        defer wg.Done()
        // Fetch the URL.
        http.Get(url)
    }(url)
}
// Wait for all HTTP fetches to complete.
wg.Wait()
```

### func (\*WaitGroup) Add 

```go
func (wg *WaitGroup) Add(delta int)
```

Add adds delta, which may be negative, to the WaitGroup counter. If the
counter becomes zero, all goroutines blocked on Wait are released. If
the counter goes negative, Add panics.

Note that calls with a positive delta that occur when the counter is
zero must happen before a Wait. Calls with a negative delta, or calls
with a positive delta that start when the counter is greater than zero,
may happen at any time. Typically this means the calls to Add should
execute before the statement creating the goroutine or other event to be
waited for. If a WaitGroup is reused to wait for several independent
sets of events, new Add calls must happen after all previous Wait calls
have returned. See the WaitGroup example.

### func (\*WaitGroup) Done 

```go
func (wg *WaitGroup) Done()
```

Done decrements the WaitGroup counter by one.

### func (\*WaitGroup) Wait 

```go
func (wg *WaitGroup) Wait()
```

Wait blocks until the WaitGroup counter is zero.

Subdirectories 
--------------

 
Name


Synopsis

[..](../index)

[atomic](atomic/index)

Package atomic provides low-level atomic memory primitives useful for
implementing synchronization algorithms.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/sync/>

