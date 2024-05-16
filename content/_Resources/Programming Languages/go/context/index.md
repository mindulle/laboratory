Package context
===============

-   `import "context"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package context defines the Context type, which carries deadlines,
cancellation signals, and other request-scoped values across API
boundaries and between processes.

Incoming requests to a server should create a [Context](#Context), and
outgoing calls to servers should accept a Context. The chain of function
calls between them must propagate the Context, optionally replacing it
with a derived Context created using [WithCancel](#WithCancel),
[WithDeadline](#WithDeadline), [WithTimeout](#WithTimeout), or
[WithValue](#WithValue). When a Context is canceled, all Contexts
derived from it are also canceled.

The [WithCancel](#WithCancel), [WithDeadline](#WithDeadline), and
[WithTimeout](#WithTimeout) functions take a Context (the parent) and
return a derived Context (the child) and a [CancelFunc](#CancelFunc).
Calling the CancelFunc cancels the child and its children, removes the
parent\'s reference to the child, and stops any associated timers.
Failing to call the CancelFunc leaks the child and its children until
the parent is canceled or the timer fires. The go vet tool checks that
CancelFuncs are used on all control-flow paths.

The [WithCancelCause](#WithCancelCause) function returns a
[CancelCauseFunc](#CancelCauseFunc), which takes an error and records it
as the cancellation cause. Calling [Cause](#Cause) on the canceled
context or any of its children retrieves the cause. If no cause is
specified, Cause(ctx) returns the same value as ctx.Err().

Programs that use Contexts should follow these rules to keep interfaces
consistent across packages and enable static analysis tools to check
context propagation:

Do not store Contexts inside a struct type; instead, pass a Context
explicitly to each function that needs it. The Context should be the
first parameter, typically named ctx:

```go
func DoSomething(ctx context.Context, arg Arg) error {
    // ... use ctx ...
}
```

Do not pass a nil [Context](#Context), even if a function permits it.
Pass [context.TODO](#TODO) if you are unsure about which Context to use.

Use context Values only for request-scoped data that transits processes
and APIs, not for passing optional parameters to functions.

The same Context may be passed to functions running in different
goroutines; Contexts are safe for simultaneous use by multiple
goroutines.

See https://blog.golang.org/context> for example code for a server that
uses Contexts.

Index 
-----

-   [Variables](#pkg-variables)
-   [func AfterFunc(ctx Context, f func()) (stop func()
    bool)](#AfterFunc)
-   [func Cause(c Context) error](#Cause)
-   [func WithCancel(parent Context) (ctx Context, cancel
    CancelFunc)](#WithCancel)
-   [func WithCancelCause(parent Context) (ctx Context, cancel
    CancelCauseFunc)](#WithCancelCause)
-   [func WithDeadline(parent Context, d time.Time) (Context,
    CancelFunc)](#WithDeadline)
-   [func WithDeadlineCause(parent Context, d time.Time, cause error)
    (Context, CancelFunc)](#WithDeadlineCause)
-   [func WithTimeout(parent Context, timeout time.Duration) (Context,
    CancelFunc)](#WithTimeout)
-   [func WithTimeoutCause(parent Context, timeout time.Duration, cause
    error) (Context, CancelFunc)](#WithTimeoutCause)
-   [type CancelCauseFunc](#CancelCauseFunc)
-   [type CancelFunc](#CancelFunc)
-   [type Context](#Context)
-   [func Background() Context](#Background)
-   [func TODO() Context](#TODO)
-   [func WithValue(parent Context, key, val any) Context](#WithValue)
-   [func WithoutCancel(parent Context) Context](#WithoutCancel)

 
### Examples

[AfterFunc (Cond)](#example_AfterFunc_cond)

[AfterFunc (Connection)](#example_AfterFunc_connection)

[AfterFunc (Merge)](#example_AfterFunc_merge)

[WithCancel](#example_WithCancel)

[WithDeadline](#example_WithDeadline)

[WithTimeout](#example_WithTimeout)

[WithValue](#example_WithValue)


### Package files

context.go

Variables 
---------

Canceled is the error returned by \[Context.Err\] when the context is
canceled.

```go
var Canceled = errors.New("context canceled")
```

DeadlineExceeded is the error returned by \[Context.Err\] when the
context\'s deadline passes.

```go
var DeadlineExceeded error = deadlineExceededError{}
```

func AfterFunc 
-----------------------------------------------

```go
func AfterFunc(ctx Context, f func()) (stop func() bool)
```

AfterFunc arranges to call f in its own goroutine after ctx is done
(cancelled or timed out). If ctx is already done, AfterFunc calls f
immediately in its own goroutine.

Multiple calls to AfterFunc on a context operate independently; one does
not replace another.

Calling the returned stop function stops the association of ctx with f.
It returns true if the call stopped f from being run. If stop returns
false, either the context is done and f has been started in its own
goroutine; or f was already stopped. The stop function does not wait for
f to complete before returning. If the caller needs to know whether f is
completed, it must coordinate with f explicitly.

If ctx has a \"AfterFunc(func()) func() bool\" method, AfterFunc will
use it to schedule the call.

#### [Example (Cond)]

This example uses AfterFunc to define a function which waits on a
sync.Cond, stopping the wait when a context is canceled.

Code:

```go
waitOnCond := func(ctx context.Context, cond *sync.Cond, conditionMet func() bool) error {
    stopf := context.AfterFunc(ctx, func() {
        // We need to acquire cond.L here to be sure that the Broadcast
        // below won't occur before the call to Wait, which would result
        // in a missed signal (and deadlock).
        cond.L.Lock()
        defer cond.L.Unlock()

        // If multiple goroutines are waiting on cond simultaneously,
        // we need to make sure we wake up exactly this one.
        // That means that we need to Broadcast to all of the goroutines,
        // which will wake them all up.
        //
        // If there are N concurrent calls to waitOnCond, each of the goroutines
        // will spuriously wake up O(N) other goroutines that aren't ready yet,
        // so this will cause the overall CPU cost to be O(N²).
        cond.Broadcast()
    })
    defer stopf()

    // Since the wakeups are using Broadcast instead of Signal, this call to
    // Wait may unblock due to some other goroutine's context becoming done,
    // so to be sure that ctx is actually done we need to check it in a loop.
    for !conditionMet() {
        cond.Wait()
        if ctx.Err() != nil {
            return ctx.Err()
        }
    }

    return nil
}

cond := sync.NewCond(new(sync.Mutex))

var wg sync.WaitGroup
for i := 0; i < 4; i++ {
    wg.Add(1)
    go func() {
        defer wg.Done()

        ctx, cancel := context.WithTimeout(context.Background(), 1*time.Millisecond)
        defer cancel()

        cond.L.Lock()
        defer cond.L.Unlock()

        err := waitOnCond(ctx, cond, func() bool { return false })
        fmt.Println(err)
    }()
}
wg.Wait()
```

Output:

```go
context deadline exceeded
context deadline exceeded
context deadline exceeded
context deadline exceeded
```

#### [Example (Connection)]

This example uses AfterFunc to define a function which reads from a
net.Conn, stopping the read when a context is canceled.

Code:

```go
readFromConn := func(ctx context.Context, conn net.Conn, b []byte) (n int, err error) {
    stopc := make(chan struct{})
    stop := context.AfterFunc(ctx, func() {
        conn.SetReadDeadline(time.Now())
        close(stopc)
    })
    n, err = conn.Read(b)
    if !stop() {
        // The AfterFunc was started.
        // Wait for it to complete, and reset the Conn's deadline.
        <-stopc
        conn.SetReadDeadline(time.Time{})
        return n, ctx.Err()
    }
    return n, err
}

listener, err := net.Listen("tcp", ":0")
if err != nil {
    fmt.Println(err)
    return
}
defer listener.Close()

conn, err := net.Dial(listener.Addr().Network(), listener.Addr().String())
if err != nil {
    fmt.Println(err)
    return
}
defer conn.Close()

ctx, cancel := context.WithTimeout(context.Background(), 1*time.Millisecond)
defer cancel()

b := make([]byte, 1024)
_, err = readFromConn(ctx, conn, b)
fmt.Println(err)
```

Output:

```go
context deadline exceeded
```

#### [Example (Merge)]

This example uses AfterFunc to define a function which combines the
cancellation signals of two Contexts.

Code:

```go
// mergeCancel returns a context that contains the values of ctx,
// and which is canceled when either ctx or cancelCtx is canceled.
mergeCancel := func(ctx, cancelCtx context.Context) (context.Context, context.CancelFunc) {
    ctx, cancel := context.WithCancelCause(ctx)
    stop := context.AfterFunc(cancelCtx, func() {
        cancel(context.Cause(cancelCtx))
    })
    return ctx, func() {
        stop()
        cancel(context.Canceled)
    }
}

ctx1, cancel1 := context.WithCancelCause(context.Background())
defer cancel1(errors.New("ctx1 canceled"))

ctx2, cancel2 := context.WithCancelCause(context.Background())

mergedCtx, mergedCancel := mergeCancel(ctx1, ctx2)
defer mergedCancel()

cancel2(errors.New("ctx2 canceled"))
<-mergedCtx.Done()
fmt.Println(context.Cause(mergedCtx))
```

Output:

```go
ctx2 canceled
```

func Cause 
-------------------------------------------

```go
func Cause(c Context) error
```

Cause returns a non-nil error explaining why c was canceled. The first
cancellation of c or one of its parents sets the cause. If that
cancellation happened via a call to CancelCauseFunc(err), then
[Cause](#Cause) returns err. Otherwise Cause(c) returns the same value
as c.Err(). Cause returns nil if c has not been canceled yet.

func WithCancel 
----------------------------------------------

```go
func WithCancel(parent Context) (ctx Context, cancel CancelFunc)
```

WithCancel returns a copy of parent with a new Done channel. The
returned context\'s Done channel is closed when the returned cancel
function is called or when the parent context\'s Done channel is closed,
whichever happens first.

Canceling this context releases resources associated with it, so code
should call cancel as soon as the operations running in this Context
complete.

#### [Example]

This example demonstrates the use of a cancelable context to prevent a
goroutine leak. By the end of the example function, the goroutine
started by gen will return without leaking.

Code:

```go
// gen generates integers in a separate goroutine and
// sends them to the returned channel.
// The callers of gen need to cancel the context once
// they are done consuming generated integers not to leak
// the internal goroutine started by gen.
gen := func(ctx context.Context) <-chan int {
    dst := make(chan int)
    n := 1
    go func() {
        for {
            select {
            case <-ctx.Done():
                return // returning not to leak the goroutine
            case dst <- n:
                n++
            }
        }
    }()
    return dst
}

ctx, cancel := context.WithCancel(context.Background())
defer cancel() // cancel when we are finished consuming integers

for n := range gen(ctx) {
    fmt.Println(n)
    if n == 5 {
        break
    }
}
```

Output:

```go
1
2
3
4
5
```

func WithCancelCause 
-----------------------------------------------------

```go
func WithCancelCause(parent Context) (ctx Context, cancel CancelCauseFunc)
```

WithCancelCause behaves like [WithCancel](#WithCancel) but returns a
[CancelCauseFunc](#CancelCauseFunc) instead of a
[CancelFunc](#CancelFunc). Calling cancel with a non-nil error (the
\"cause\") records that error in ctx; it can then be retrieved using
Cause(ctx). Calling cancel with nil sets the cause to Canceled.

Example use:

```go
ctx, cancel := context.WithCancelCause(parent)
cancel(myError)
ctx.Err() // returns context.Canceled
context.Cause(ctx) // returns myError
```

func WithDeadline 
------------------------------------------------

```go
func WithDeadline(parent Context, d time.Time) (Context, CancelFunc)
```

WithDeadline returns a copy of the parent context with the deadline
adjusted to be no later than d. If the parent\'s deadline is already
earlier than d, WithDeadline(parent, d) is semantically equivalent to
parent. The returned \[Context.Done\] channel is closed when the
deadline expires, when the returned cancel function is called, or when
the parent context\'s Done channel is closed, whichever happens first.

Canceling this context releases resources associated with it, so code
should call cancel as soon as the operations running in this
[Context](#Context) complete.

#### [Example]

This example passes a context with an arbitrary deadline to tell a
blocking function that it should abandon its work as soon as it gets to
it.

Code:

```go
d := time.Now().Add(shortDuration)
ctx, cancel := context.WithDeadline(context.Background(), d)

// Even though ctx will be expired, it is good practice to call its
// cancellation function in any case. Failure to do so may keep the
// context and its parent alive longer than necessary.
defer cancel()

select {
case <-neverReady:
    fmt.Println("ready")
case <-ctx.Done():
    fmt.Println(ctx.Err())
}
```

Output:

```go
context deadline exceeded
```

func WithDeadlineCause 
-------------------------------------------------------

```go
func WithDeadlineCause(parent Context, d time.Time, cause error) (Context, CancelFunc)
```

WithDeadlineCause behaves like [WithDeadline](#WithDeadline) but also
sets the cause of the returned Context when the deadline is exceeded.
The returned [CancelFunc](#CancelFunc) does not set the cause.

func WithTimeout 
-----------------------------------------------

```go
func WithTimeout(parent Context, timeout time.Duration) (Context, CancelFunc)
```

WithTimeout returns WithDeadline(parent, time.Now().Add(timeout)).

Canceling this context releases resources associated with it, so code
should call cancel as soon as the operations running in this
[Context](#Context) complete:

```go
func slowOperationWithTimeout(ctx context.Context) (Result, error) {
    ctx, cancel := context.WithTimeout(ctx, 100*time.Millisecond)
    defer cancel()  // releases resources if slowOperation completes before timeout elapses
    return slowOperation(ctx)
}
```

#### [Example]

This example passes a context with a timeout to tell a blocking function
that it should abandon its work after the timeout elapses.

Code:

```go
// Pass a context with a timeout to tell a blocking function that it
// should abandon its work after the timeout elapses.
ctx, cancel := context.WithTimeout(context.Background(), shortDuration)
defer cancel()

select {
case <-neverReady:
    fmt.Println("ready")
case <-ctx.Done():
    fmt.Println(ctx.Err()) // prints "context deadline exceeded"
}
```

Output:

```go
context deadline exceeded
```

func WithTimeoutCause 
------------------------------------------------------

```go
func WithTimeoutCause(parent Context, timeout time.Duration, cause error) (Context, CancelFunc)
```

WithTimeoutCause behaves like [WithTimeout](#WithTimeout) but also sets
the cause of the returned Context when the timeout expires. The returned
[CancelFunc](#CancelFunc) does not set the cause.

type CancelCauseFunc 
-----------------------------------------------------

A CancelCauseFunc behaves like a [CancelFunc](#CancelFunc) but
additionally sets the cancellation cause. This cause can be retrieved by
calling [Cause](#Cause) on the canceled Context or on any of its derived
Contexts.

If the context has already been canceled, CancelCauseFunc does not set
the cause. For example, if childContext is derived from parentContext:

-   if parentContext is canceled with cause1 before childContext is
    canceled with cause2, then Cause(parentContext) ==
    Cause(childContext) == cause1
-   if childContext is canceled with cause2 before parentContext is
    canceled with cause1, then Cause(parentContext) == cause1 and
    Cause(childContext) == cause2

```go
type CancelCauseFunc func(cause error)
```

type CancelFunc 
----------------------------------------------

A CancelFunc tells an operation to abandon its work. A CancelFunc does
not wait for the work to stop. A CancelFunc may be called by multiple
goroutines simultaneously. After the first call, subsequent calls to a
CancelFunc do nothing.

```go
type CancelFunc func()
```

type Context 
-------------------------------------------

A Context carries a deadline, a cancellation signal, and other values
across API boundaries.

Context\'s methods may be called by multiple goroutines simultaneously.

```go
type Context interface {
    // Deadline returns the time when work done on behalf of this context
    // should be canceled. Deadline returns ok==false when no deadline is
    // set. Successive calls to Deadline return the same results.
    Deadline() (deadline time.Time, ok bool)

    // Done returns a channel that's closed when work done on behalf of this
    // context should be canceled. Done may return nil if this context can
    // never be canceled. Successive calls to Done return the same value.
    // The close of the Done channel may happen asynchronously,
    // after the cancel function returns.
    //
    // WithCancel arranges for Done to be closed when cancel is called;
    // WithDeadline arranges for Done to be closed when the deadline
    // expires; WithTimeout arranges for Done to be closed when the timeout
    // elapses.
    //
    // Done is provided for use in select statements:
    //
    //  // Stream generates values with DoSomething and sends them to out
    //  // until DoSomething returns an error or ctx.Done is closed.
    //  func Stream(ctx context.Context, out chan<- Value) error {
    //      for {
    //          v, err := DoSomething(ctx)
    //          if err != nil {
    //              return err
    //          }
    //          select {
    //          case <-ctx.Done():
    //              return ctx.Err()
    //          case out <- v:
    //          }
    //      }
    //  }
    //
    // See https://blog.golang.org/pipelines for more examples of how to use
    // a Done channel for cancellation.
    Done() <-chan struct{}

    // If Done is not yet closed, Err returns nil.
    // If Done is closed, Err returns a non-nil error explaining why:
    // Canceled if the context was canceled
    // or DeadlineExceeded if the context's deadline passed.
    // After Err returns a non-nil error, successive calls to Err return the same error.
    Err() error

    // Value returns the value associated with this context for key, or nil
    // if no value is associated with key. Successive calls to Value with
    // the same key returns the same result.
    //
    // Use context values only for request-scoped data that transits
    // processes and API boundaries, not for passing optional parameters to
    // functions.
    //
    // A key identifies a specific value in a Context. Functions that wish
    // to store values in Context typically allocate a key in a global
    // variable then use that key as the argument to context.WithValue and
    // Context.Value. A key can be any type that supports equality;
    // packages should define keys as an unexported type to avoid
    // collisions.
    //
    // Packages that define a Context key should provide type-safe accessors
    // for the values stored using that key:
    //
    //  // Package user defines a User type that's stored in Contexts.
    //  package user
    //
    //  import "context"
    //
    //  // User is the type of value stored in the Contexts.
    //  type User struct 
    //
    //  // key is an unexported type for keys defined in this package.
    //  // This prevents collisions with keys defined in other packages.
    //  type key int
    //
    //  // userKey is the key for user.User values in Contexts. It is
    //  // unexported; clients use user.NewContext and user.FromContext
    //  // instead of using this key directly.
    //  var userKey key
    //
    //  // NewContext returns a new Context that carries value u.
    //  func NewContext(ctx context.Context, u *User) context.Context {
    //      return context.WithValue(ctx, userKey, u)
    //  }
    //
    //  // FromContext returns the User value stored in ctx, if any.
    //  func FromContext(ctx context.Context) (*User, bool) {
    //      u, ok := ctx.Value(userKey).(*User)
    //      return u, ok
    //  }
    Value(key any) any
}
```

### func Background 

```go
func Background() Context
```

Background returns a non-nil, empty [Context](#Context). It is never
canceled, has no values, and has no deadline. It is typically used by
the main function, initialization, and tests, and as the top-level
Context for incoming requests.

### func TODO 

```go
func TODO() Context
```

TODO returns a non-nil, empty [Context](#Context). Code should use
context.TODO when it\'s unclear which Context to use or it is not yet
available (because the surrounding function has not yet been extended to
accept a Context parameter).

### func WithValue 

```go
func WithValue(parent Context, key, val any) Context
```

WithValue returns a copy of parent in which the value associated with
key is val.

Use context Values only for request-scoped data that transits processes
and APIs, not for passing optional parameters to functions.

The provided key must be comparable and should not be of type string or
any other built-in type to avoid collisions between packages using
context. Users of WithValue should define their own types for keys. To
avoid allocating when assigning to an interface{}, context keys often
have concrete type struct{}. Alternatively, exported context key
variables\' static type should be a pointer or interface.

#### [Example]

This example demonstrates how a value can be passed to the context and
also how to retrieve it if it exists.

Code:

```go
type favContextKey string

f := func(ctx context.Context, k favContextKey) {
    if v := ctx.Value(k); v != nil {
        fmt.Println("found value:", v)
        return
    }
    fmt.Println("key not found:", k)
}

k := favContextKey("language")
ctx := context.WithValue(context.Background(), k, "Go")

f(ctx, k)
f(ctx, favContextKey("color"))
```

Output:

```go
found value: Go
key not found: color
```

### func WithoutCancel 

```go
func WithoutCancel(parent Context) Context
```

WithoutCancel returns a copy of parent that is not canceled when parent
is canceled. The returned context returns no Deadline or Err, and its
Done channel is nil. Calling [Cause](#Cause) on the returned context
returns nil.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/context/>

