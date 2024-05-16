Package expvar
==============

-   `import "expvar"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package expvar provides a standardized interface to public variables,
such as operation counters in servers. It exposes these variables via
HTTP at /debug/vars in JSON format.

Operations to set or modify these public variables are atomic.

In addition to adding the HTTP handler, this package registers the
following variables:

```go
cmdline   os.Args
memstats  runtime.Memstats
```

The package is sometimes only imported for the side effect of
registering its HTTP handler and the above variables. To use it this
way, link this package into your program:

```go
import _ "expvar"
```

Index 
-----

-   [func Do(f func(KeyValue))](#Do)
-   [func Handler() http.Handler](#Handler)
-   [func Publish(name string, v Var)](#Publish)
-   [type Float](#Float)
-   [func NewFloat(name string) \*Float](#NewFloat)
-   [func (v \*Float) Add(delta float64)](#Float.Add)
-   [func (v \*Float) Set(value float64)](#Float.Set)
-   [func (v \*Float) String() string](#Float.String)
-   [func (v \*Float) Value() float64](#Float.Value)
-   [type Func](#Func)
-   [func (f Func) String() string](#Func.String)
-   [func (f Func) Value() any](#Func.Value)
-   [type Int](#Int)
-   [func NewInt(name string) \*Int](#NewInt)
-   [func (v \*Int) Add(delta int64)](#Int.Add)
-   [func (v \*Int) Set(value int64)](#Int.Set)
-   [func (v \*Int) String() string](#Int.String)
-   [func (v \*Int) Value() int64](#Int.Value)
-   [type KeyValue](#KeyValue)
-   [type Map](#Map)
-   [func NewMap(name string) \*Map](#NewMap)
-   [func (v \*Map) Add(key string, delta int64)](#Map.Add)
-   [func (v \*Map) AddFloat(key string, delta float64)](#Map.AddFloat)
-   [func (v \*Map) Delete(key string)](#Map.Delete)
-   [func (v \*Map) Do(f func(KeyValue))](#Map.Do)
-   [func (v \*Map) Get(key string) Var](#Map.Get)
-   [func (v \*Map) Init() \*Map](#Map.Init)
-   [func (v \*Map) Set(key string, av Var)](#Map.Set)
-   [func (v \*Map) String() string](#Map.String)
-   [type String](#String)
-   [func NewString(name string) \*String](#NewString)
-   [func (v \*String) Set(value string)](#String.Set)
-   [func (v \*String) String() string](#String.String)
-   [func (v \*String) Value() string](#String.Value)
-   [type Var](#Var)
-   [func Get(name string) Var](#Get)

### Package files

expvar.go

func Do 
-------

```go
func Do(f func(KeyValue))
```

Do calls f for each exported variable. The global variable map is locked
during the iteration, but existing entries may be concurrently updated.

func Handler 
-------------------------------------------

```go
func Handler() http.Handler
```

Handler returns the expvar HTTP Handler.

This is only needed to install the handler in a non-standard location.

func Publish 
------------

```go
func Publish(name string, v Var)
```

Publish declares a named exported variable. This should be called from a
package\'s init function when it creates its Vars. If the name is
already registered then this will log.Panic.

type Float 
----------

Float is a 64-bit float variable that satisfies the Var interface.

```go
type Float struct {
    // contains filtered or unexported fields
}
```

### func NewFloat 

```go
func NewFloat(name string) *Float
```

### func (\*Float) Add 

```go
func (v *Float) Add(delta float64)
```

Add adds delta to v.

### func (\*Float) Set 

```go
func (v *Float) Set(value float64)
```

Set sets v to value.

### func (\*Float) String 

```go
func (v *Float) String() string
```

### func (\*Float) Value 

```go
func (v *Float) Value() float64
```

type Func 
---------

Func implements Var by calling the function and formatting the returned
value using JSON.

```go
type Func func() any
```

### func (Func) String 

```go
func (f Func) String() string
```

### func (Func) Value 

```go
func (f Func) Value() any
```

type Int 
--------

Int is a 64-bit integer variable that satisfies the Var interface.

```go
type Int struct {
    // contains filtered or unexported fields
}
```

### func NewInt 

```go
func NewInt(name string) *Int
```

### func (\*Int) Add 

```go
func (v *Int) Add(delta int64)
```

### func (\*Int) Set 

```go
func (v *Int) Set(value int64)
```

### func (\*Int) String 

```go
func (v *Int) String() string
```

### func (\*Int) Value 

```go
func (v *Int) Value() int64
```

type KeyValue 
-------------

KeyValue represents a single entry in a Map.

```go
type KeyValue struct {
    Key   string
    Value Var
}
```

type Map 
--------

Map is a string-to-Var map variable that satisfies the Var interface.

```go
type Map struct {
    // contains filtered or unexported fields
}
```

### func NewMap 

```go
func NewMap(name string) *Map
```

### func (\*Map) Add 

```go
func (v *Map) Add(key string, delta int64)
```

Add adds delta to the \*Int value stored under the given map key.

### func (\*Map) AddFloat 

```go
func (v *Map) AddFloat(key string, delta float64)
```

AddFloat adds delta to the \*Float value stored under the given map key.

### func (\*Map) Delete 

```go
func (v *Map) Delete(key string)
```

Delete deletes the given key from the map.

### func (\*Map) Do 

```go
func (v *Map) Do(f func(KeyValue))
```

Do calls f for each entry in the map. The map is locked during the
iteration, but existing entries may be concurrently updated.

### func (\*Map) Get 

```go
func (v *Map) Get(key string) Var
```

### func (\*Map) Init 

```go
func (v *Map) Init() *Map
```

Init removes all keys from the map.

### func (\*Map) Set 

```go
func (v *Map) Set(key string, av Var)
```

### func (\*Map) String 

```go
func (v *Map) String() string
```

type String 
-----------

String is a string variable, and satisfies the Var interface.

```go
type String struct {
    // contains filtered or unexported fields
}
```

### func NewString 

```go
func NewString(name string) *String
```

### func (\*String) Set 

```go
func (v *String) Set(value string)
```

### func (\*String) String 

```go
func (v *String) String() string
```

String implements the Var interface. To get the unquoted string use
Value.

### func (\*String) Value 

```go
func (v *String) Value() string
```

type Var 
--------

Var is an abstract type for all exported variables.

```go
type Var interface {
    // String returns a valid JSON value for the variable.
    // Types with String methods that do not return valid JSON
    // (such as time.Time) must not be used as a Var.
    String() string
}
```

### func Get 

```go
func Get(name string) Var
```

Get retrieves a named exported variable. It returns nil if the name has
not been registered.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/expvar/>

