Package constraint
==================

-   `import "go/build/constraint"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package constraint implements parsing and evaluation of build constraint
lines. See https://golang.org/cmd/go/#hdr-Build_constraints> for
documentation about build constraints themselves.

This package parses both the original "// +build" syntax and the
"//go:build" syntax that was added in Go 1.17. See
https://golang.org/design/draft-gobuild> for details about the
"//go:build" syntax.

Index 
-----

-   [func GoVersion(x Expr) string](#GoVersion)
-   [func IsGoBuild(line string) bool](#IsGoBuild)
-   [func IsPlusBuild(line string) bool](#IsPlusBuild)
-   [func PlusBuildLines(x Expr) (\[\]string, error)](#PlusBuildLines)
-   [type AndExpr](#AndExpr)
-   [func (x \*AndExpr) Eval(ok func(tag string) bool)
    bool](#AndExpr.Eval)
-   [func (x \*AndExpr) String() string](#AndExpr.String)
-   [type Expr](#Expr)
-   [func Parse(line string) (Expr, error)](#Parse)
-   [type NotExpr](#NotExpr)
-   [func (x \*NotExpr) Eval(ok func(tag string) bool)
    bool](#NotExpr.Eval)
-   [func (x \*NotExpr) String() string](#NotExpr.String)
-   [type OrExpr](#OrExpr)
-   [func (x \*OrExpr) Eval(ok func(tag string) bool)
    bool](#OrExpr.Eval)
-   [func (x \*OrExpr) String() string](#OrExpr.String)
-   [type SyntaxError](#SyntaxError)
-   [func (e \*SyntaxError) Error() string](#SyntaxError.Error)
-   [type TagExpr](#TagExpr)
-   [func (x \*TagExpr) Eval(ok func(tag string) bool)
    bool](#TagExpr.Eval)
-   [func (x \*TagExpr) String() string](#TagExpr.String)

### Package files

expr.go vers.go

func GoVersion 
-----------------------------------------------

```go
func GoVersion(x Expr) string
```

GoVersion returns the minimum Go version implied by a given build
expression. If the expression can be satisfied without any Go version
tags, GoVersion returns an empty string.

For example:

```go
GoVersion(linux && go1.22) = "go1.22"
GoVersion((linux && go1.22) || (windows && go1.20)) = "go1.20" => go1.20
GoVersion(linux) = ""
GoVersion(linux || (windows && go1.22)) = ""
GoVersion(!go1.22) = ""
```

GoVersion assumes that any tag or negated tag may independently be true,
so that its analysis can be purely structural, without SAT solving.
"Impossible" subexpressions may therefore affect the result.

For example:

```go
GoVersion((linux && !linux && go1.20) || go1.21) = "go1.20"
```

func IsGoBuild 
-----------------------------------------------

```go
func IsGoBuild(line string) bool
```

IsGoBuild reports whether the line of text is a "//go:build" constraint.
It only checks the prefix of the text, not that the expression itself
parses.

func IsPlusBuild 
-------------------------------------------------

```go
func IsPlusBuild(line string) bool
```

IsPlusBuild reports whether the line of text is a "// +build"
constraint. It only checks the prefix of the text, not that the
expression itself parses.

func PlusBuildLines 
----------------------------------------------------

```go
func PlusBuildLines(x Expr) ([]string, error)
```

PlusBuildLines returns a sequence of "// +build" lines that evaluate to
the build expression x. If the expression is too complex to convert
directly to "// +build" lines, PlusBuildLines returns an error.

type AndExpr 
---------------------------------------------

An AndExpr represents the expression X && Y.

```go
type AndExpr struct {
    X, Y Expr
}
```

### func (\*AndExpr) Eval 

```go
func (x *AndExpr) Eval(ok func(tag string) bool) bool
```

### func (\*AndExpr) String 

```go
func (x *AndExpr) String() string
```

type Expr 
------------------------------------------

An Expr is a build tag constraint expression. The underlying concrete
type is \*AndExpr, \*OrExpr, \*NotExpr, or \*TagExpr.

```go
type Expr interface {
    // String returns the string form of the expression,
    // using the boolean syntax used in //go:build lines.
    String() string

    // Eval reports whether the expression evaluates to true.
    // It calls ok(tag) as needed to find out whether a given build tag
    // is satisfied by the current build configuration.
    Eval(ok func(tag string) bool) bool
    // contains filtered or unexported methods
}
```

### func Parse 

```go
func Parse(line string) (Expr, error)
```

Parse parses a single build constraint line of the form "//go:build
\..." or "// +build \..." and returns the corresponding boolean
expression.

type NotExpr 
---------------------------------------------

A NotExpr represents the expression !X (the negation of X).

```go
type NotExpr struct {
    X Expr
}
```

### func (\*NotExpr) Eval 

```go
func (x *NotExpr) Eval(ok func(tag string) bool) bool
```

### func (\*NotExpr) String 

```go
func (x *NotExpr) String() string
```

type OrExpr 
--------------------------------------------

An OrExpr represents the expression X \|\| Y.

```go
type OrExpr struct {
    X, Y Expr
}
```

### func (\*OrExpr) Eval 

```go
func (x *OrExpr) Eval(ok func(tag string) bool) bool
```

### func (\*OrExpr) String 

```go
func (x *OrExpr) String() string
```

type SyntaxError 
-------------------------------------------------

A SyntaxError reports a syntax error in a parsed build expression.

```go
type SyntaxError struct {
    Offset int    // byte offset in input where error was detected
    Err    string // description of error
}
```

### func (\*SyntaxError) Error 

```go
func (e *SyntaxError) Error() string
```

type TagExpr 
---------------------------------------------

A TagExpr is an Expr for the single tag Tag.

```go
type TagExpr struct {
    Tag string // for example, “linux” or “cgo”
}
```

### func (\*TagExpr) Eval 

```go
func (x *TagExpr) Eval(ok func(tag string) bool) bool
```

### func (\*TagExpr) String 

```go
func (x *TagExpr) String() string
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/go/build/constraint/>

