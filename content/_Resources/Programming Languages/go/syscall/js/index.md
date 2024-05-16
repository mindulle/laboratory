Package js
==========

-   `import "syscall/js"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package js gives access to the WebAssembly host environment when using
the js/wasm architecture. Its API is based on JavaScript semantics.

This package is EXPERIMENTAL. Its current scope is only to allow tests
to run, but not yet to provide a comprehensive API for users. It is
exempt from the Go compatibility promise.

Index 
-----

-   [func CopyBytesToGo(dst \[\]byte, src Value) int](#CopyBytesToGo)
-   [func CopyBytesToJS(dst Value, src \[\]byte) int](#CopyBytesToJS)
-   [type Error](#Error)
-   [func (e Error) Error() string](#Error.Error)
-   [type Func](#Func)
-   [func FuncOf(fn func(this Value, args \[\]Value) any) Func](#FuncOf)
-   [func (c Func) Release()](#Func.Release)
-   [type Type](#Type)
-   [func (t Type) String() string](#Type.String)
-   [type Value](#Value)
-   [func Global() Value](#Global)
-   [func Null() Value](#Null)
-   [func Undefined() Value](#Undefined)
-   [func ValueOf(x any) Value](#ValueOf)
-   [func (v Value) Bool() bool](#Value.Bool)
-   [func (v Value) Call(m string, args \...any) Value](#Value.Call)
-   [func (v Value) Delete(p string)](#Value.Delete)
-   [func (v Value) Equal(w Value) bool](#Value.Equal)
-   [func (v Value) Float() float64](#Value.Float)
-   [func (v Value) Get(p string) Value](#Value.Get)
-   [func (v Value) Index(i int) Value](#Value.Index)
-   [func (v Value) InstanceOf(t Value) bool](#Value.InstanceOf)
-   [func (v Value) Int() int](#Value.Int)
-   [func (v Value) Invoke(args \...any) Value](#Value.Invoke)
-   [func (v Value) IsNaN() bool](#Value.IsNaN)
-   [func (v Value) IsNull() bool](#Value.IsNull)
-   [func (v Value) IsUndefined() bool](#Value.IsUndefined)
-   [func (v Value) Length() int](#Value.Length)
-   [func (v Value) New(args \...any) Value](#Value.New)
-   [func (v Value) Set(p string, x any)](#Value.Set)
-   [func (v Value) SetIndex(i int, x any)](#Value.SetIndex)
-   [func (v Value) String() string](#Value.String)
-   [func (v Value) Truthy() bool](#Value.Truthy)
-   [func (v Value) Type() Type](#Value.Type)
-   [type ValueError](#ValueError)
-   [func (e \*ValueError) Error() string](#ValueError.Error)

 
### Examples

[FuncOf](#example_FuncOf)


### Package files

func.go js.go

func CopyBytesToGo 
------------------

```go
func CopyBytesToGo(dst []byte, src Value) int
```

CopyBytesToGo copies bytes from src to dst. It panics if src is not a
Uint8Array or Uint8ClampedArray. It returns the number of bytes copied,
which will be the minimum of the lengths of src and dst.

func CopyBytesToJS 
------------------

```go
func CopyBytesToJS(dst Value, src []byte) int
```

CopyBytesToJS copies bytes from src to dst. It panics if dst is not a
Uint8Array or Uint8ClampedArray. It returns the number of bytes copied,
which will be the minimum of the lengths of src and dst.

type Error 
----------

Error wraps a JavaScript error.

```go
type Error struct {
    // Value is the underlying JavaScript error value.
    Value
}
```

### func (Error) Error 

```go
func (e Error) Error() string
```

Error implements the error interface.

type Func 
---------

Func is a wrapped Go function to be called by JavaScript.

```go
type Func struct {
    Value // the JavaScript function that invokes the Go function
    // contains filtered or unexported fields
}
```

### func FuncOf 

```go
func FuncOf(fn func(this Value, args []Value) any) Func
```

FuncOf returns a function to be used by JavaScript.

The Go function fn is called with the value of JavaScript\'s \"this\"
keyword and the arguments of the invocation. The return value of the
invocation is the result of the Go function mapped back to JavaScript
according to ValueOf.

Invoking the wrapped Go function from JavaScript will pause the event
loop and spawn a new goroutine. Other wrapped functions which are
triggered during a call from Go to JavaScript get executed on the same
goroutine.

As a consequence, if one wrapped function blocks, JavaScript\'s event
loop is blocked until that function returns. Hence, calling any async
JavaScript API, which requires the event loop, like fetch (http.Client),
will cause an immediate deadlock. Therefore a blocking function should
explicitly start a new goroutine.

Func.Release must be called to free up resources when the function will
not be invoked any more.

#### [Example]

Code:

```go
var cb js.Func
cb = js.FuncOf(func(this js.Value, args []js.Value) any {
    fmt.Println("button clicked")
    cb.Release() // release the function if the button will not be clicked again
    return nil
})
js.Global().Get("document").Call("getElementById", "myButton").Call("addEventListener", "click", cb)
```

### func (Func) Release 

```go
func (c Func) Release()
```

Release frees up resources allocated for the function. The function must
not be invoked after calling Release. It is allowed to call Release
while the function is still running.

type Type 
---------

Type represents the JavaScript type of a Value.

```go
type Type int
```

```go
const (
    TypeUndefined Type = iota
    TypeNull
    TypeBoolean
    TypeNumber
    TypeString
    TypeSymbol
    TypeObject
    TypeFunction
)
```

### func (Type) String 

```go
func (t Type) String() string
```

type Value 
----------

Value represents a JavaScript value. The zero value is the JavaScript
value \"undefined\". Values can be checked for equality with the Equal
method.

```go
type Value struct {
    // contains filtered or unexported fields
}
```

### func Global 

```go
func Global() Value
```

Global returns the JavaScript global object, usually \"window\" or
\"global\".

### func Null 

```go
func Null() Value
```

Null returns the JavaScript value \"null\".

### func Undefined 

```go
func Undefined() Value
```

Undefined returns the JavaScript value \"undefined\".

### func ValueOf 

```go
func ValueOf(x any) Value
```

ValueOf returns x as a JavaScript value:

```go
| Go                     | JavaScript             |
| ---------------------- | ---------------------- |
| js.Value               | [its value]            |
| js.Func                | function               |
| nil                    | null                   |
| bool                   | boolean                |
| integers and floats    | number                 |
| string                 | string                 |
| []interface{}          | new array              |
| map[string]interface{} | new object             |
```

Panics if x is not one of the expected types.

### func (Value) Bool 

```go
func (v Value) Bool() bool
```

Bool returns the value v as a bool. It panics if v is not a JavaScript
boolean.

### func (Value) Call 

```go
func (v Value) Call(m string, args ...any) Value
```

Call does a JavaScript call to the method m of value v with the given
arguments. It panics if v has no method m. The arguments get mapped to
JavaScript values according to the ValueOf function.

### func (Value) Delete 

```go
func (v Value) Delete(p string)
```

Delete deletes the JavaScript property p of value v. It panics if v is
not a JavaScript object.

### func (Value) Equal 

```go
func (v Value) Equal(w Value) bool
```

Equal reports whether v and w are equal according to JavaScript\'s ===
operator.

### func (Value) Float 

```go
func (v Value) Float() float64
```

Float returns the value v as a float64. It panics if v is not a
JavaScript number.

### func (Value) Get 

```go
func (v Value) Get(p string) Value
```

Get returns the JavaScript property p of value v. It panics if v is not
a JavaScript object.

### func (Value) Index 

```go
func (v Value) Index(i int) Value
```

Index returns JavaScript index i of value v. It panics if v is not a
JavaScript object.

### func (Value) InstanceOf 

```go
func (v Value) InstanceOf(t Value) bool
```

InstanceOf reports whether v is an instance of type t according to
JavaScript\'s instanceof operator.

### func (Value) Int 

```go
func (v Value) Int() int
```

Int returns the value v truncated to an int. It panics if v is not a
JavaScript number.

### func (Value) Invoke 

```go
func (v Value) Invoke(args ...any) Value
```

Invoke does a JavaScript call of the value v with the given arguments.
It panics if v is not a JavaScript function. The arguments get mapped to
JavaScript values according to the ValueOf function.

### func (Value) IsNaN 

```go
func (v Value) IsNaN() bool
```

IsNaN reports whether v is the JavaScript value \"NaN\".

### func (Value) IsNull 

```go
func (v Value) IsNull() bool
```

IsNull reports whether v is the JavaScript value \"null\".

### func (Value) IsUndefined 

```go
func (v Value) IsUndefined() bool
```

IsUndefined reports whether v is the JavaScript value \"undefined\".

### func (Value) Length 

```go
func (v Value) Length() int
```

Length returns the JavaScript property \"length\" of v. It panics if v
is not a JavaScript object.

### func (Value) New 

```go
func (v Value) New(args ...any) Value
```

New uses JavaScript\'s \"new\" operator with value v as constructor and
the given arguments. It panics if v is not a JavaScript function. The
arguments get mapped to JavaScript values according to the ValueOf
function.

### func (Value) Set 

```go
func (v Value) Set(p string, x any)
```

Set sets the JavaScript property p of value v to ValueOf(x). It panics
if v is not a JavaScript object.

### func (Value) SetIndex 

```go
func (v Value) SetIndex(i int, x any)
```

SetIndex sets the JavaScript index i of value v to ValueOf(x). It panics
if v is not a JavaScript object.

### func (Value) String 

```go
func (v Value) String() string
```

String returns the value v as a string. String is a special case because
of Go\'s String method convention. Unlike the other getters, it does not
panic if v\'s Type is not TypeString. Instead, it returns a string of
the form \"\<T\>\" or \"\<T: V\>\" where T is v\'s type and V is a
string representation of v\'s value.

### func (Value) Truthy 

```go
func (v Value) Truthy() bool
```

Truthy returns the JavaScript \"truthiness\" of the value v. In
JavaScript, false, 0, \"\", null, undefined, and NaN are \"falsy\", and
everything else is \"truthy\". See
https://developer.mozilla.org/en-US/docs/Glossary/Truthy>.

### func (Value) Type 

```go
func (v Value) Type() Type
```

Type returns the JavaScript type of the value v. It is similar to
JavaScript\'s typeof operator, except that it returns TypeNull instead
of TypeObject for null.

type ValueError 
---------------

A ValueError occurs when a Value method is invoked on a Value that does
not support it. Such cases are documented in the description of each
method.

```go
type ValueError struct {
    Method string
    Type   Type
}
```

### func (\*ValueError) Error 

```go
func (e *ValueError) Error() string
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/syscall/js/>

