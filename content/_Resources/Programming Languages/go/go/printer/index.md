Package printer
===============

-   `import "go/printer"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package printer implements printing of AST nodes.

Index 
-----

-   [func Fprint(output io.Writer, fset \*token.FileSet, node any)
    error](#Fprint)
-   [type CommentedNode](#CommentedNode)
-   [type Config](#Config)
-   [func (cfg \*Config) Fprint(output io.Writer, fset \*token.FileSet,
    node any) error](#Config.Fprint)
-   [type Mode](#Mode)

 
### Examples

[Fprint](#example_Fprint)


### Package files

comment.go gobuild.go nodes.go printer.go

func Fprint 
-----------

```go
func Fprint(output io.Writer, fset *token.FileSet, node any) error
```

Fprint \"pretty-prints\" an AST node to output. It calls Config.Fprint
with default settings. Note that gofmt uses tabs for indentation but
spaces for alignment; use format.Node (package go/format) for output
that matches gofmt.

#### [Example]

Code:

```go
package printer_test

import (
    "bytes"
    "fmt"
    "go/ast"
    "go/parser"
    "go/printer"
    "go/token"
    "strings"
)

func parseFunc(filename, functionname string) (fun *ast.FuncDecl, fset *token.FileSet) {
    fset = token.NewFileSet()
    if file, err := parser.ParseFile(fset, filename, nil, 0); err == nil {
        for _, d := range file.Decls {
            if f, ok := d.(*ast.FuncDecl); ok && f.Name.Name == functionname {
                fun = f
                return
            }
        }
    }
    panic("function not found")
}

func printSelf() {
    // Parse source file and extract the AST without comments for
    // this function, with position information referring to the
    // file set fset.
    funcAST, fset := parseFunc("example_test.go", "printSelf")

    // Print the function body into buffer buf.
    // The file set is provided to the printer so that it knows
    // about the original source formatting and can add additional
    // line breaks where they were present in the source.
    var buf bytes.Buffer
    printer.Fprint(&buf, fset, funcAST.Body)

    // Remove braces {} enclosing the function body, unindent,
    // and trim leading and trailing white space.
    s := buf.String()
    s = s[1 : len(s)-1]
    s = strings.TrimSpace(strings.ReplaceAll(s, "\n\t", "\n"))

    // Print the cleaned-up body text to stdout.
    fmt.Println(s)
}

func ExampleFprint() {
    printSelf()

    // Output:
    // funcAST, fset := parseFunc("example_test.go", "printSelf")
    //
    // var buf bytes.Buffer
    // printer.Fprint(&buf, fset, funcAST.Body)
    //
    // s := buf.String()
    // s = s[1 : len(s)-1]
    // s = strings.TrimSpace(strings.ReplaceAll(s, "\n\t", "\n"))
    //
    // fmt.Println(s)
}
```

type CommentedNode 
------------------

A CommentedNode bundles an AST node and corresponding comments. It may
be provided as argument to any of the Fprint functions.

```go
type CommentedNode struct {
    Node     any // *ast.File, or ast.Expr, ast.Decl, ast.Spec, or ast.Stmt
    Comments []*ast.CommentGroup
}
```

type Config 
-----------

A Config node controls the output of Fprint.

```go
type Config struct {
    Mode     Mode // default: 0
    Tabwidth int  // default: 8
    Indent   int  // default: 0 (all code is indented at least by this much); added in Go 1.1
}
```

### func (\*Config) Fprint 

```go
func (cfg *Config) Fprint(output io.Writer, fset *token.FileSet, node any) error
```

Fprint \"pretty-prints\" an AST node to output for a given configuration
cfg. Position information is interpreted relative to the file set fset.
The node type must be \*ast.File, \*CommentedNode, \[\]ast.Decl,
\[\]ast.Stmt, or assignment-compatible to ast.Expr, ast.Decl, ast.Spec,
or ast.Stmt.

type Mode 
---------

A Mode value is a set of flags (or 0). They control printing.

```go
type Mode uint
```

```go
const (
    RawFormat Mode = 1 << iota // do not use a tabwriter; if set, UseSpaces is ignored
    TabIndent                  // use tabs for indentation independent of UseSpaces
    UseSpaces                  // use spaces instead of tabs for alignment
    SourcePos                  // emit //line directives to preserve original source positions
)
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/go/printer/>

