Package parser
==============

-   `import "go/parser"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package parser implements a parser for Go source files. Input may be
provided in a variety of forms (see the various Parse\* functions); the
output is an abstract syntax tree (AST) representing the Go source. The
parser is invoked through one of the Parse\* functions.

The parser accepts a larger language than is syntactically permitted by
the Go spec, for simplicity, and for improved robustness in the presence
of syntax errors. For instance, in method declarations, the receiver is
treated like an ordinary parameter list and thus may contain multiple
entries where the spec permits exactly one. Consequently, the
corresponding field in the AST (ast.FuncDecl.Recv) field is not
restricted to one entry.

Index 
-----

-   [func ParseDir(fset \*token.FileSet, path string, filter
    func(fs.FileInfo) bool, mode Mode) (pkgs map\[string\]\*ast.Package,
    first error)](#ParseDir)
-   [func ParseExpr(x string) (ast.Expr, error)](#ParseExpr)
-   [func ParseExprFrom(fset \*token.FileSet, filename string, src any,
    mode Mode) (expr ast.Expr, err error)](#ParseExprFrom)
-   [func ParseFile(fset \*token.FileSet, filename string, src any, mode
    Mode) (f \*ast.File, err error)](#ParseFile)
-   [type Mode](#Mode)

 
### Examples

[ParseFile](#example_ParseFile)


### Package files

interface.go parser.go resolver.go

func ParseDir 
-------------

```go
func ParseDir(fset *token.FileSet, path string, filter func(fs.FileInfo) bool, mode Mode) (pkgs map[string]*ast.Package, first error)
```

ParseDir calls ParseFile for all files with names ending in \".go\" in
the directory specified by path and returns a map of package name -\>
package AST with all the packages found.

If filter != nil, only the files with fs.FileInfo entries passing
through the filter (and ending in \".go\") are considered. The mode bits
are passed to ParseFile unchanged. Position information is recorded in
fset, which must not be nil.

If the directory couldn\'t be read, a nil map and the respective error
are returned. If a parse error occurred, a non-nil but incomplete map
and the first error encountered are returned.

func ParseExpr 
--------------

```go
func ParseExpr(x string) (ast.Expr, error)
```

ParseExpr is a convenience function for obtaining the AST of an
expression x. The position information recorded in the AST is undefined.
The filename used in error messages is the empty string.

If syntax errors were found, the result is a partial AST (with ast.Bad\*
nodes representing the fragments of erroneous source code). Multiple
errors are returned via a scanner.ErrorList which is sorted by source
position.


-------------------------------------------------

```go
func ParseExprFrom(fset *token.FileSet, filename string, src any, mode Mode) (expr ast.Expr, err error)
```

ParseExprFrom is a convenience function for parsing an expression. The
arguments have the same meaning as for ParseFile, but the source must be
a valid Go (type or value) expression. Specifically, fset must not be
nil.

If the source couldn\'t be read, the returned AST is nil and the error
indicates the specific failure. If the source was read but syntax errors
were found, the result is a partial AST (with ast.Bad\* nodes
representing the fragments of erroneous source code). Multiple errors
are returned via a scanner.ErrorList which is sorted by source position.

func ParseFile 
--------------

```go
func ParseFile(fset *token.FileSet, filename string, src any, mode Mode) (f *ast.File, err error)
```

ParseFile parses the source code of a single Go source file and returns
the corresponding ast.File node. The source code may be provided via the
filename of the source file, or via the src parameter.

If src != nil, ParseFile parses the source from src and the filename is
only used when recording position information. The type of the argument
for the src parameter must be string, \[\]byte, or io.Reader. If src ==
nil, ParseFile parses the file specified by filename.

The mode parameter controls the amount of source text parsed and other
optional parser functionality. If the SkipObjectResolution mode bit is
set, the object resolution phase of parsing will be skipped, causing
File.Scope, File.Unresolved, and all Ident.Obj fields to be nil.

Position information is recorded in the file set fset, which must not be
nil.

If the source couldn\'t be read, the returned AST is nil and the error
indicates the specific failure. If the source was read but syntax errors
were found, the result is a partial AST (with ast.Bad\* nodes
representing the fragments of erroneous source code). Multiple errors
are returned via a scanner.ErrorList which is sorted by source position.

#### [Example]

Code:

```go
fset := token.NewFileSet() // positions are relative to fset

src := `package foo

import (
    "fmt"
    "time"
)

func bar() {
    fmt.Println(time.Now())
}`

// Parse src but stop after processing the imports.
f, err := parser.ParseFile(fset, "", src, parser.ImportsOnly)
if err != nil {
    fmt.Println(err)
    return
}

// Print the imports from the file's AST.
for _, s := range f.Imports {
    fmt.Println(s.Path.Value)
}
```

Output:

```go
"fmt"
"time"
```

type Mode 
---------

A Mode value is a set of flags (or 0). They control the amount of source
code parsed and other optional parser functionality.

```go
type Mode uint
```

```go
const (
    PackageClauseOnly    Mode             = 1 << iota // stop parsing after package clause
    ImportsOnly                                       // stop parsing after import declarations
    ParseComments                                     // parse comments and add them to AST
    Trace                                             // print a trace of parsed productions
    DeclarationErrors                                 // report declaration errors
    SpuriousErrors                                    // same as AllErrors, for backward-compatibility
    SkipObjectResolution                              // don't resolve identifiers to objects - see ParseFile
    AllErrors            = SpuriousErrors             // report all errors (not just the first 10 on different lines)
)
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/go/parser/>

