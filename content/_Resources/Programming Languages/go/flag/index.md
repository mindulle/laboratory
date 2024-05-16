Package flag
============

-   `import "flag"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package flag implements command-line flag parsing.

### Usage 

Define flags using flag.String(), Bool(), Int(), etc.

This declares an integer flag, -n, stored in the pointer nFlag, with
type \*int:

```go
import "flag"
var nFlag = flag.Int("n", 1234, "help message for flag n")
```

If you like, you can bind the flag to a variable using the Var()
functions.

```go
var flagvar int
func init() {
    flag.IntVar(&flagvar, "flagname", 1234, "help message for flagname")
}
```

Or you can create custom flags that satisfy the Value interface (with
pointer receivers) and couple them to flag parsing by

```go
flag.Var(&flagVal, "name", "help message for flagname")
```

For such flags, the default value is just the initial value of the
variable.

After all flags are defined, call

```go
flag.Parse()
```

to parse the command line into the defined flags.

Flags may then be used directly. If you\'re using the flags themselves,
they are all pointers; if you bind to variables, they\'re values.

```go
fmt.Println("ip has value ", *ip)
fmt.Println("flagvar has value ", flagvar)
```

After parsing, the arguments following the flags are available as the
slice flag.Args() or individually as flag.Arg(i). The arguments are
indexed from 0 through flag.NArg()-1.

### Command line flag syntax 

The following forms are permitted:

```go
-flag
--flag   // double dashes are also permitted
-flag=x
-flag x  // non-boolean flags only
```

One or two dashes may be used; they are equivalent. The last form is not
permitted for boolean flags because the meaning of the command

```go
cmd -x *
```

where \* is a Unix shell wildcard, will change if there is a file called
0, false, etc. You must use the -flag=false form to turn off a boolean
flag.

Flag parsing stops just before the first non-flag argument (\"-\" is a
non-flag argument) or after the terminator \"\--\".

Integer flags accept 1234, 0664, 0x1234 and may be negative. Boolean
flags may be:

```go
1, 0, t, f, T, F, true, false, TRUE, FALSE, True, False
```

Duration flags accept any input valid for time.ParseDuration.

The default set of command-line flags is controlled by top-level
functions. The FlagSet type allows one to define independent sets of
flags, such as to implement subcommands in a command-line interface. The
methods of FlagSet are analogous to the top-level functions for the
command-line flag set.

#### [Example]

Code:

```go
// These examples demonstrate more intricate uses of the flag package.
package flag_test

import (
    "errors"
    "flag"
    "fmt"
    "strings"
    "time"
)

// Example 1: A single string flag called "species" with default value "gopher".
var species = flag.String("species", "gopher", "the species we are studying")

// Example 2: Two flags sharing a variable, so we can have a shorthand.
// The order of initialization is undefined, so make sure both use the
// same default value. They must be set up with an init function.
var gopherType string

func init() {
    const (
        defaultGopher = "pocket"
        usage         = "the variety of gopher"
    )
    flag.StringVar(&gopherType, "gopher_type", defaultGopher, usage)
    flag.StringVar(&gopherType, "g", defaultGopher, usage+" (shorthand)")
}

// Example 3: A user-defined flag type, a slice of durations.
type interval []time.Duration

// String is the method to format the flag's value, part of the flag.Value interface.
// The String method's output will be used in diagnostics.
func (i *interval) String() string {
    return fmt.Sprint(*i)
}

// Set is the method to set the flag value, part of the flag.Value interface.
// Set's argument is a string to be parsed to set the flag.
// It's a comma-separated list, so we split it.
func (i *interval) Set(value string) error {
    // If we wanted to allow the flag to be set multiple times,
    // accumulating values, we would delete this if statement.
    // That would permit usages such as
    //  -deltaT 10s -deltaT 15s
    // and other combinations.
    if len(*i) > 0 {
        return errors.New("interval flag already set")
    }
    for _, dt := range strings.Split(value, ",") {
        duration, err := time.ParseDuration(dt)
        if err != nil {
            return err
        }
        *i = append(*i, duration)
    }
    return nil
}

// Define a flag to accumulate durations. Because it has a special type,
// we need to use the Var function and therefore create the flag during
// init.

var intervalFlag interval

func init() {
    // Tie the command-line flag to the intervalFlag variable and
    // set a usage message.
    flag.Var(&intervalFlag, "deltaT", "comma-separated list of intervals to use between events")
}

func Example() {
    // All the interesting pieces are with the variables declared above, but
    // to enable the flag package to see the flags defined there, one must
    // execute, typically at the start of main (not init!):
    //  flag.Parse()
    // We don't call it here because this code is a function called "Example"
    // that is part of the testing suite for the package, which has already
    // parsed the flags. When viewed at pkg.go.dev, however, the function is
    // renamed to "main" and it could be run as a standalone example.
}
```

Index 
-----

-   [Variables](#pkg-variables)
-   [func Arg(i int) string](#Arg)
-   [func Args() \[\]string](#Args)
-   [func Bool(name string, value bool, usage string) \*bool](#Bool)
-   [func BoolFunc(name, usage string, fn func(string)
    error)](#BoolFunc)
-   [func BoolVar(p \*bool, name string, value bool, usage
    string)](#BoolVar)
-   [func Duration(name string, value time.Duration, usage string)
    \*time.Duration](#Duration)
-   [func DurationVar(p \*time.Duration, name string, value
    time.Duration, usage string)](#DurationVar)
-   [func Float64(name string, value float64, usage string)
    \*float64](#Float64)
-   [func Float64Var(p \*float64, name string, value float64, usage
    string)](#Float64Var)
-   [func Func(name, usage string, fn func(string) error)](#Func)
-   [func Int(name string, value int, usage string) \*int](#Int)
-   [func Int64(name string, value int64, usage string) \*int64](#Int64)
-   [func Int64Var(p \*int64, name string, value int64, usage
    string)](#Int64Var)
-   [func IntVar(p \*int, name string, value int, usage
    string)](#IntVar)
-   [func NArg() int](#NArg)
-   [func NFlag() int](#NFlag)
-   [func Parse()](#Parse)
-   [func Parsed() bool](#Parsed)
-   [func PrintDefaults()](#PrintDefaults)
-   [func Set(name, value string) error](#Set)
-   [func String(name string, value string, usage string)
    \*string](#String)
-   [func StringVar(p \*string, name string, value string, usage
    string)](#StringVar)
-   [func TextVar(p encoding.TextUnmarshaler, name string, value
    encoding.TextMarshaler, usage string)](#TextVar)
-   [func Uint(name string, value uint, usage string) \*uint](#Uint)
-   [func Uint64(name string, value uint64, usage string)
    \*uint64](#Uint64)
-   [func Uint64Var(p \*uint64, name string, value uint64, usage
    string)](#Uint64Var)
-   [func UintVar(p \*uint, name string, value uint, usage
    string)](#UintVar)
-   [func UnquoteUsage(flag \*Flag) (name string, usage
    string)](#UnquoteUsage)
-   [func Var(value Value, name string, usage string)](#Var)
-   [func Visit(fn func(\*Flag))](#Visit)
-   [func VisitAll(fn func(\*Flag))](#VisitAll)
-   [type ErrorHandling](#ErrorHandling)
-   [type Flag](#Flag)
-   [func Lookup(name string) \*Flag](#Lookup)
-   [type FlagSet](#FlagSet)
-   [func NewFlagSet(name string, errorHandling ErrorHandling)
    \*FlagSet](#NewFlagSet)
-   [func (f \*FlagSet) Arg(i int) string](#FlagSet.Arg)
-   [func (f \*FlagSet) Args() \[\]string](#FlagSet.Args)
-   [func (f \*FlagSet) Bool(name string, value bool, usage string)
    \*bool](#FlagSet.Bool)
-   [func (f \*FlagSet) BoolFunc(name, usage string, fn func(string)
    error)](#FlagSet.BoolFunc)
-   [func (f \*FlagSet) BoolVar(p \*bool, name string, value bool, usage
    string)](#FlagSet.BoolVar)
-   [func (f \*FlagSet) Duration(name string, value time.Duration, usage
    string) \*time.Duration](#FlagSet.Duration)
-   [func (f \*FlagSet) DurationVar(p \*time.Duration, name string,
    value time.Duration, usage string)](#FlagSet.DurationVar)
-   [func (f \*FlagSet) ErrorHandling()
    ErrorHandling](#FlagSet.ErrorHandling)
-   [func (f \*FlagSet) Float64(name string, value float64, usage
    string) \*float64](#FlagSet.Float64)
-   [func (f \*FlagSet) Float64Var(p \*float64, name string, value
    float64, usage string)](#FlagSet.Float64Var)
-   [func (f \*FlagSet) Func(name, usage string, fn func(string)
    error)](#FlagSet.Func)
-   [func (f \*FlagSet) Init(name string, errorHandling
    ErrorHandling)](#FlagSet.Init)
-   [func (f \*FlagSet) Int(name string, value int, usage string)
    \*int](#FlagSet.Int)
-   [func (f \*FlagSet) Int64(name string, value int64, usage string)
    \*int64](#FlagSet.Int64)
-   [func (f \*FlagSet) Int64Var(p \*int64, name string, value int64,
    usage string)](#FlagSet.Int64Var)
-   [func (f \*FlagSet) IntVar(p \*int, name string, value int, usage
    string)](#FlagSet.IntVar)
-   [func (f \*FlagSet) Lookup(name string) \*Flag](#FlagSet.Lookup)
-   [func (f \*FlagSet) NArg() int](#FlagSet.NArg)
-   [func (f \*FlagSet) NFlag() int](#FlagSet.NFlag)
-   [func (f \*FlagSet) Name() string](#FlagSet.Name)
-   [func (f \*FlagSet) Output() io.Writer](#FlagSet.Output)
-   [func (f \*FlagSet) Parse(arguments \[\]string)
    error](#FlagSet.Parse)
-   [func (f \*FlagSet) Parsed() bool](#FlagSet.Parsed)
-   [func (f \*FlagSet) PrintDefaults()](#FlagSet.PrintDefaults)
-   [func (f \*FlagSet) Set(name, value string) error](#FlagSet.Set)
-   [func (f \*FlagSet) SetOutput(output io.Writer)](#FlagSet.SetOutput)
-   [func (f \*FlagSet) String(name string, value string, usage string)
    \*string](#FlagSet.String)
-   [func (f \*FlagSet) StringVar(p \*string, name string, value string,
    usage string)](#FlagSet.StringVar)
-   [func (f \*FlagSet) TextVar(p encoding.TextUnmarshaler, name string,
    value encoding.TextMarshaler, usage string)](#FlagSet.TextVar)
-   [func (f \*FlagSet) Uint(name string, value uint, usage string)
    \*uint](#FlagSet.Uint)
-   [func (f \*FlagSet) Uint64(name string, value uint64, usage string)
    \*uint64](#FlagSet.Uint64)
-   [func (f \*FlagSet) Uint64Var(p \*uint64, name string, value uint64,
    usage string)](#FlagSet.Uint64Var)
-   [func (f \*FlagSet) UintVar(p \*uint, name string, value uint, usage
    string)](#FlagSet.UintVar)
-   [func (f \*FlagSet) Var(value Value, name string, usage
    string)](#FlagSet.Var)
-   [func (f \*FlagSet) Visit(fn func(\*Flag))](#FlagSet.Visit)
-   [func (f \*FlagSet) VisitAll(fn func(\*Flag))](#FlagSet.VisitAll)
-   [type Getter](#Getter)
-   [type Value](#Value)

 
### Examples

[Package](#example_)

[BoolFunc](#example_BoolFunc)

[Func](#example_Func)

[TextVar](#example_TextVar)

[Value](#example_Value)


### Package files

flag.go

Variables 
---------

CommandLine is the default set of command-line flags, parsed from
os.Args. The top-level functions such as BoolVar, Arg, and so on are
wrappers for the methods of CommandLine.

```go
var CommandLine = NewFlagSet(os.Args[0], ExitOnError)
```

ErrHelp is the error returned if the -help or -h flag is invoked but no
such flag is defined.

```go
var ErrHelp = errors.New("flag: help requested")
```

Usage prints a usage message documenting all defined command-line flags
to CommandLine\'s output, which by default is os.Stderr. It is called
when an error occurs while parsing flags. The function is a variable
that may be changed to point to a custom function. By default it prints
a simple header and calls PrintDefaults; for details about the format of
the output and how to control it, see the documentation for
PrintDefaults. Custom usage functions may choose to exit the program; by
default exiting happens anyway as the command line\'s error handling
strategy is set to ExitOnError.

```go
var Usage = func() {
    fmt.Fprintf(CommandLine.Output(), "Usage of %s:\n", os.Args[0])
    PrintDefaults()
}
```

func Arg 
--------

```go
func Arg(i int) string
```

Arg returns the i\'th command-line argument. Arg(0) is the first
remaining argument after flags have been processed. Arg returns an empty
string if the requested element does not exist.

func Args 
---------

```go
func Args() []string
```

Args returns the non-flag command-line arguments.

func Bool 
---------

```go
func Bool(name string, value bool, usage string) *bool
```

Bool defines a bool flag with specified name, default value, and usage
string. The return value is the address of a bool variable that stores
the value of the flag.

func BoolFunc 
----------------------------------------------

```go
func BoolFunc(name, usage string, fn func(string) error)
```

BoolFunc defines a flag with the specified name and usage string without
requiring values. Each time the flag is seen, fn is called with the
value of the flag. If fn returns a non-nil error, it will be treated as
a flag value parsing error.

#### [Example]

Code:

```go
fs := flag.NewFlagSet("ExampleBoolFunc", flag.ContinueOnError)
fs.SetOutput(os.Stdout)

fs.BoolFunc("log", "logs a dummy message", func(s string) error {
    fmt.Println("dummy message:", s)
    return nil
})
fs.Parse([]string{"-log"})
fs.Parse([]string{"-log=0"})
```

Output:

```go
dummy message: true
dummy message: 0
```

func BoolVar 
------------

```go
func BoolVar(p *bool, name string, value bool, usage string)
```

BoolVar defines a bool flag with specified name, default value, and
usage string. The argument p points to a bool variable in which to store
the value of the flag.

func Duration 
-------------

```go
func Duration(name string, value time.Duration, usage string) *time.Duration
```

Duration defines a time.Duration flag with specified name, default
value, and usage string. The return value is the address of a
time.Duration variable that stores the value of the flag. The flag
accepts a value acceptable to time.ParseDuration.

func DurationVar 
----------------

```go
func DurationVar(p *time.Duration, name string, value time.Duration, usage string)
```

DurationVar defines a time.Duration flag with specified name, default
value, and usage string. The argument p points to a time.Duration
variable in which to store the value of the flag. The flag accepts a
value acceptable to time.ParseDuration.

func Float64 
------------

```go
func Float64(name string, value float64, usage string) *float64
```

Float64 defines a float64 flag with specified name, default value, and
usage string. The return value is the address of a float64 variable that
stores the value of the flag.

func Float64Var 
---------------

```go
func Float64Var(p *float64, name string, value float64, usage string)
```

Float64Var defines a float64 flag with specified name, default value,
and usage string. The argument p points to a float64 variable in which
to store the value of the flag.

func Func 
------------------------------------------

```go
func Func(name, usage string, fn func(string) error)
```

Func defines a flag with the specified name and usage string. Each time
the flag is seen, fn is called with the value of the flag. If fn returns
a non-nil error, it will be treated as a flag value parsing error.

#### [Example]

Code:

```go
fs := flag.NewFlagSet("ExampleFunc", flag.ContinueOnError)
fs.SetOutput(os.Stdout)
var ip net.IP
fs.Func("ip", "`IP address` to parse", func(s string) error {
    ip = net.ParseIP(s)
    if ip == nil {
        return errors.New("could not parse IP")
    }
    return nil
})
fs.Parse([]string{"-ip", "127.0.0.1"})
fmt.Printf("{ip: %v, loopback: %t}\n\n", ip, ip.IsLoopback())

// 256 is not a valid IPv4 component
fs.Parse([]string{"-ip", "256.0.0.1"})
fmt.Printf("{ip: %v, loopback: %t}\n\n", ip, ip.IsLoopback())
```

Output:

```go
{ip: 127.0.0.1, loopback: true}

invalid value "256.0.0.1" for flag -ip: could not parse IP
Usage of ExampleFunc:
  -ip IP address
        IP address to parse
{ip: <nil>, loopback: false}
```

func Int 
--------

```go
func Int(name string, value int, usage string) *int
```

Int defines an int flag with specified name, default value, and usage
string. The return value is the address of an int variable that stores
the value of the flag.

func Int64 
----------

```go
func Int64(name string, value int64, usage string) *int64
```

Int64 defines an int64 flag with specified name, default value, and
usage string. The return value is the address of an int64 variable that
stores the value of the flag.

func Int64Var 
-------------

```go
func Int64Var(p *int64, name string, value int64, usage string)
```

Int64Var defines an int64 flag with specified name, default value, and
usage string. The argument p points to an int64 variable in which to
store the value of the flag.

func IntVar 
-----------

```go
func IntVar(p *int, name string, value int, usage string)
```

IntVar defines an int flag with specified name, default value, and usage
string. The argument p points to an int variable in which to store the
value of the flag.

func NArg 
---------

```go
func NArg() int
```

NArg is the number of arguments remaining after flags have been
processed.

func NFlag 
----------

```go
func NFlag() int
```

NFlag returns the number of command-line flags that have been set.

func Parse 
----------

```go
func Parse()
```

Parse parses the command-line flags from os.Args\[1:\]. Must be called
after all flags are defined and before flags are accessed by the
program.

func Parsed 
-----------

```go
func Parsed() bool
```

Parsed reports whether the command-line flags have been parsed.

func PrintDefaults 
------------------

```go
func PrintDefaults()
```

PrintDefaults prints, to standard error unless configured otherwise, a
usage message showing the default settings of all defined command-line
flags. For an integer valued flag x, the default output has the form

```go
-x int
    usage-message-for-x (default 7)
```

The usage message will appear on a separate line for anything but a bool
flag with a one-byte name. For bool flags, the type is omitted and if
the flag name is one byte the usage message appears on the same line.
The parenthetical default is omitted if the default is the zero value
for the type. The listed type, here int, can be changed by placing a
back-quoted name in the flag\'s usage string; the first such item in the
message is taken to be a parameter name to show in the message and the
back quotes are stripped from the message when displayed. For instance,
given

```go
flag.String("I", "", "search `directory` for include files")
```

the output will be

```go
-I directory
    search directory for include files.
```

To change the destination for flag messages, call CommandLine.SetOutput.

func Set 
--------

```go
func Set(name, value string) error
```

Set sets the value of the named command-line flag.

func String 
-----------

```go
func String(name string, value string, usage string) *string
```

String defines a string flag with specified name, default value, and
usage string. The return value is the address of a string variable that
stores the value of the flag.

func StringVar 
--------------

```go
func StringVar(p *string, name string, value string, usage string)
```

StringVar defines a string flag with specified name, default value, and
usage string. The argument p points to a string variable in which to
store the value of the flag.

func TextVar 
---------------------------------------------

```go
func TextVar(p encoding.TextUnmarshaler, name string, value encoding.TextMarshaler, usage string)
```

TextVar defines a flag with a specified name, default value, and usage
string. The argument p must be a pointer to a variable that will hold
the value of the flag, and p must implement encoding.TextUnmarshaler. If
the flag is used, the flag value will be passed to p\'s UnmarshalText
method. The type of the default value must be the same as the type of p.

#### [Example]

Code:

```go
fs := flag.NewFlagSet("ExampleTextVar", flag.ContinueOnError)
fs.SetOutput(os.Stdout)
var ip net.IP
fs.TextVar(&ip, "ip", net.IPv4(192, 168, 0, 100), "`IP address` to parse")
fs.Parse([]string{"-ip", "127.0.0.1"})
fmt.Printf("{ip: %v}\n\n", ip)

// 256 is not a valid IPv4 component
ip = nil
fs.Parse([]string{"-ip", "256.0.0.1"})
fmt.Printf("{ip: %v}\n\n", ip)
```

Output:

```go
{ip: 127.0.0.1}

invalid value "256.0.0.1" for flag -ip: invalid IP address: 256.0.0.1
Usage of ExampleTextVar:
  -ip IP address
        IP address to parse (default 192.168.0.100)
{ip: <nil>}
```

func Uint 
---------

```go
func Uint(name string, value uint, usage string) *uint
```

Uint defines a uint flag with specified name, default value, and usage
string. The return value is the address of a uint variable that stores
the value of the flag.

func Uint64 
-----------

```go
func Uint64(name string, value uint64, usage string) *uint64
```

Uint64 defines a uint64 flag with specified name, default value, and
usage string. The return value is the address of a uint64 variable that
stores the value of the flag.

func Uint64Var 
--------------

```go
func Uint64Var(p *uint64, name string, value uint64, usage string)
```

Uint64Var defines a uint64 flag with specified name, default value, and
usage string. The argument p points to a uint64 variable in which to
store the value of the flag.

func UintVar 
------------

```go
func UintVar(p *uint, name string, value uint, usage string)
```

UintVar defines a uint flag with specified name, default value, and
usage string. The argument p points to a uint variable in which to store
the value of the flag.

func UnquoteUsage 
------------------------------------------------

```go
func UnquoteUsage(flag *Flag) (name string, usage string)
```

UnquoteUsage extracts a back-quoted name from the usage string for a
flag and returns it and the un-quoted usage. Given \"a \`name\` to
show\" it returns (\"name\", \"a name to show\"). If there are no back
quotes, the name is an educated guess of the type of the flag\'s value,
or the empty string if the flag is boolean.

func Var 
--------

```go
func Var(value Value, name string, usage string)
```

Var defines a flag with the specified name and usage string. The type
and value of the flag are represented by the first argument, of type
Value, which typically holds a user-defined implementation of Value. For
instance, the caller could create a flag that turns a comma-separated
string into a slice of strings by giving the slice the methods of Value;
in particular, Set would decompose the comma-separated string into the
slice.

func Visit 
----------

```go
func Visit(fn func(*Flag))
```

Visit visits the command-line flags in lexicographical order, calling fn
for each. It visits only those flags that have been set.

func VisitAll 
-------------

```go
func VisitAll(fn func(*Flag))
```

VisitAll visits the command-line flags in lexicographical order, calling
fn for each. It visits all flags, even those not set.

type ErrorHandling 
------------------

ErrorHandling defines how FlagSet.Parse behaves if the parse fails.

```go
type ErrorHandling int
```

These constants cause FlagSet.Parse to behave as described if the parse
fails.

```go
const (
    ContinueOnError ErrorHandling = iota // Return a descriptive error.
    ExitOnError                          // Call os.Exit(2) or for -h/-help Exit(0).
    PanicOnError                         // Call panic with a descriptive error.
)
```

type Flag 
---------

A Flag represents the state of a flag.

```go
type Flag struct {
    Name     string // name as it appears on command line
    Usage    string // help message
    Value    Value  // value as set
    DefValue string // default value (as text); for usage message
}
```

### func Lookup 

```go
func Lookup(name string) *Flag
```

Lookup returns the Flag structure of the named command-line flag,
returning nil if none exists.

type FlagSet 
------------

A FlagSet represents a set of defined flags. The zero value of a FlagSet
has no name and has ContinueOnError error handling.

Flag names must be unique within a FlagSet. An attempt to define a flag
whose name is already in use will cause a panic.

```go
type FlagSet struct {
    // Usage is the function called when an error occurs while parsing flags.
    // The field is a function (not a method) that may be changed to point to
    // a custom error handler. What happens after Usage is called depends
    // on the ErrorHandling setting; for the command line, this defaults
    // to ExitOnError, which exits the program after calling Usage.
    Usage func()
    // contains filtered or unexported fields
}
```

### func NewFlagSet 

```go
func NewFlagSet(name string, errorHandling ErrorHandling) *FlagSet
```

NewFlagSet returns a new, empty flag set with the specified name and
error handling property. If the name is not empty, it will be printed in
the default usage message and in error messages.

### func (\*FlagSet) Arg 

```go
func (f *FlagSet) Arg(i int) string
```

Arg returns the i\'th argument. Arg(0) is the first remaining argument
after flags have been processed. Arg returns an empty string if the
requested element does not exist.

### func (\*FlagSet) Args 

```go
func (f *FlagSet) Args() []string
```

Args returns the non-flag arguments.

### func (\*FlagSet) Bool 

```go
func (f *FlagSet) Bool(name string, value bool, usage string) *bool
```

Bool defines a bool flag with specified name, default value, and usage
string. The return value is the address of a bool variable that stores
the value of the flag.

### func (\*FlagSet) BoolFunc 

```go
func (f *FlagSet) BoolFunc(name, usage string, fn func(string) error)
```

BoolFunc defines a flag with the specified name and usage string without
requiring values. Each time the flag is seen, fn is called with the
value of the flag. If fn returns a non-nil error, it will be treated as
a flag value parsing error.

### func (\*FlagSet) BoolVar 

```go
func (f *FlagSet) BoolVar(p *bool, name string, value bool, usage string)
```

BoolVar defines a bool flag with specified name, default value, and
usage string. The argument p points to a bool variable in which to store
the value of the flag.

### func (\*FlagSet) Duration 

```go
func (f *FlagSet) Duration(name string, value time.Duration, usage string) *time.Duration
```

Duration defines a time.Duration flag with specified name, default
value, and usage string. The return value is the address of a
time.Duration variable that stores the value of the flag. The flag
accepts a value acceptable to time.ParseDuration.

### func (\*FlagSet) DurationVar 

```go
func (f *FlagSet) DurationVar(p *time.Duration, name string, value time.Duration, usage string)
```

DurationVar defines a time.Duration flag with specified name, default
value, and usage string. The argument p points to a time.Duration
variable in which to store the value of the flag. The flag accepts a
value acceptable to time.ParseDuration.

### func (\*FlagSet) ErrorHandling 

```go
func (f *FlagSet) ErrorHandling() ErrorHandling
```

ErrorHandling returns the error handling behavior of the flag set.

### func (\*FlagSet) Float64 

```go
func (f *FlagSet) Float64(name string, value float64, usage string) *float64
```

Float64 defines a float64 flag with specified name, default value, and
usage string. The return value is the address of a float64 variable that
stores the value of the flag.

### func (\*FlagSet) Float64Var 

```go
func (f *FlagSet) Float64Var(p *float64, name string, value float64, usage string)
```

Float64Var defines a float64 flag with specified name, default value,
and usage string. The argument p points to a float64 variable in which
to store the value of the flag.

### func (\*FlagSet) Func 

```go
func (f *FlagSet) Func(name, usage string, fn func(string) error)
```

Func defines a flag with the specified name and usage string. Each time
the flag is seen, fn is called with the value of the flag. If fn returns
a non-nil error, it will be treated as a flag value parsing error.

### func (\*FlagSet) Init 

```go
func (f *FlagSet) Init(name string, errorHandling ErrorHandling)
```

Init sets the name and error handling property for a flag set. By
default, the zero FlagSet uses an empty name and the ContinueOnError
error handling policy.

### func (\*FlagSet) Int 

```go
func (f *FlagSet) Int(name string, value int, usage string) *int
```

Int defines an int flag with specified name, default value, and usage
string. The return value is the address of an int variable that stores
the value of the flag.

### func (\*FlagSet) Int64 

```go
func (f *FlagSet) Int64(name string, value int64, usage string) *int64
```

Int64 defines an int64 flag with specified name, default value, and
usage string. The return value is the address of an int64 variable that
stores the value of the flag.

### func (\*FlagSet) Int64Var 

```go
func (f *FlagSet) Int64Var(p *int64, name string, value int64, usage string)
```

Int64Var defines an int64 flag with specified name, default value, and
usage string. The argument p points to an int64 variable in which to
store the value of the flag.

### func (\*FlagSet) IntVar 

```go
func (f *FlagSet) IntVar(p *int, name string, value int, usage string)
```

IntVar defines an int flag with specified name, default value, and usage
string. The argument p points to an int variable in which to store the
value of the flag.

### func (\*FlagSet) Lookup 

```go
func (f *FlagSet) Lookup(name string) *Flag
```

Lookup returns the Flag structure of the named flag, returning nil if
none exists.

### func (\*FlagSet) NArg 

```go
func (f *FlagSet) NArg() int
```

NArg is the number of arguments remaining after flags have been
processed.

### func (\*FlagSet) NFlag 

```go
func (f *FlagSet) NFlag() int
```

NFlag returns the number of flags that have been set.

### func (\*FlagSet) Name 

```go
func (f *FlagSet) Name() string
```

Name returns the name of the flag set.

### func (\*FlagSet) Output 

```go
func (f *FlagSet) Output() io.Writer
```

Output returns the destination for usage and error messages. os.Stderr
is returned if output was not set or was set to nil.

### func (\*FlagSet) Parse 

```go
func (f *FlagSet) Parse(arguments []string) error
```

Parse parses flag definitions from the argument list, which should not
include the command name. Must be called after all flags in the FlagSet
are defined and before flags are accessed by the program. The return
value will be ErrHelp if -help or -h were set but not defined.

### func (\*FlagSet) Parsed 

```go
func (f *FlagSet) Parsed() bool
```

Parsed reports whether f.Parse has been called.

### func (\*FlagSet) PrintDefaults 

```go
func (f *FlagSet) PrintDefaults()
```

PrintDefaults prints, to standard error unless configured otherwise, the
default values of all defined command-line flags in the set. See the
documentation for the global function PrintDefaults for more
information.

### func (\*FlagSet) Set 

```go
func (f *FlagSet) Set(name, value string) error
```

Set sets the value of the named flag.

### func (\*FlagSet) SetOutput 

```go
func (f *FlagSet) SetOutput(output io.Writer)
```

SetOutput sets the destination for usage and error messages. If output
is nil, os.Stderr is used.

### func (\*FlagSet) String 

```go
func (f *FlagSet) String(name string, value string, usage string) *string
```

String defines a string flag with specified name, default value, and
usage string. The return value is the address of a string variable that
stores the value of the flag.

### func (\*FlagSet) StringVar 

```go
func (f *FlagSet) StringVar(p *string, name string, value string, usage string)
```

StringVar defines a string flag with specified name, default value, and
usage string. The argument p points to a string variable in which to
store the value of the flag.

### func (\*FlagSet) TextVar 

```go
func (f *FlagSet) TextVar(p encoding.TextUnmarshaler, name string, value encoding.TextMarshaler, usage string)
```

TextVar defines a flag with a specified name, default value, and usage
string. The argument p must be a pointer to a variable that will hold
the value of the flag, and p must implement encoding.TextUnmarshaler. If
the flag is used, the flag value will be passed to p\'s UnmarshalText
method. The type of the default value must be the same as the type of p.

### func (\*FlagSet) Uint 

```go
func (f *FlagSet) Uint(name string, value uint, usage string) *uint
```

Uint defines a uint flag with specified name, default value, and usage
string. The return value is the address of a uint variable that stores
the value of the flag.

### func (\*FlagSet) Uint64 

```go
func (f *FlagSet) Uint64(name string, value uint64, usage string) *uint64
```

Uint64 defines a uint64 flag with specified name, default value, and
usage string. The return value is the address of a uint64 variable that
stores the value of the flag.

### func (\*FlagSet) Uint64Var 

```go
func (f *FlagSet) Uint64Var(p *uint64, name string, value uint64, usage string)
```

Uint64Var defines a uint64 flag with specified name, default value, and
usage string. The argument p points to a uint64 variable in which to
store the value of the flag.

### func (\*FlagSet) UintVar 

```go
func (f *FlagSet) UintVar(p *uint, name string, value uint, usage string)
```

UintVar defines a uint flag with specified name, default value, and
usage string. The argument p points to a uint variable in which to store
the value of the flag.

### func (\*FlagSet) Var 

```go
func (f *FlagSet) Var(value Value, name string, usage string)
```

Var defines a flag with the specified name and usage string. The type
and value of the flag are represented by the first argument, of type
Value, which typically holds a user-defined implementation of Value. For
instance, the caller could create a flag that turns a comma-separated
string into a slice of strings by giving the slice the methods of Value;
in particular, Set would decompose the comma-separated string into the
slice.

### func (\*FlagSet) Visit 

```go
func (f *FlagSet) Visit(fn func(*Flag))
```

Visit visits the flags in lexicographical order, calling fn for each. It
visits only those flags that have been set.

### func (\*FlagSet) VisitAll 

```go
func (f *FlagSet) VisitAll(fn func(*Flag))
```

VisitAll visits the flags in lexicographical order, calling fn for each.
It visits all flags, even those not set.

type Getter 
------------------------------------------

Getter is an interface that allows the contents of a Value to be
retrieved. It wraps the Value interface, rather than being part of it,
because it appeared after Go 1 and its compatibility rules. All Value
types provided by this package satisfy the Getter interface, except the
type used by Func.

```go
type Getter interface {
    Value
    Get() any
}
```

type Value 
----------

Value is the interface to the dynamic value stored in a flag. (The
default value is represented as a string.)

If a Value has an IsBoolFlag() bool method returning true, the
command-line parser makes -name equivalent to -name=true rather than
using the next command-line argument.

Set is called once, in command line order, for each flag present. The
flag package may call the String method with a zero-valued receiver,
such as a nil pointer.

```go
type Value interface {
    String() string
    Set(string) error
}
```

#### [Example]

Code:

```go
package flag_test

import (
    "flag"
    "fmt"
    "net/url"
)

type URLValue struct {
    URL *url.URL
}

func (v URLValue) String() string {
    if v.URL != nil {
        return v.URL.String()
    }
    return ""
}

func (v URLValue) Set(s string) error {
    if u, err := url.Parse(s); err != nil {
        return err
    } else {
        *v.URL = *u
    }
    return nil
}

var u = &url.URL{}

func ExampleValue() {
    fs := flag.NewFlagSet("ExampleValue", flag.ExitOnError)
    fs.Var(&URLValue{u}, "url", "URL to parse")

    fs.Parse([]string{"-url", "https://golang.org/pkg/flag/"})
    fmt.Printf(`{scheme: %q, host: %q, path: %q}`, u.Scheme, u.Host, u.Path)

    // Output:
    // {scheme: "https", host: "golang.org", path: "/pkg/flag/"}
}
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/flag/>

