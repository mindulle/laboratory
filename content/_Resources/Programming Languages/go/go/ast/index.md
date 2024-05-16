Package ast
===========

-   `import "go/ast"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package ast declares the types used to represent syntax trees for Go
packages.

Index 
-----

-   [func FileExports(src \*File) bool](#FileExports)
-   [func FilterDecl(decl Decl, f Filter) bool](#FilterDecl)
-   [func FilterFile(src \*File, f Filter) bool](#FilterFile)
-   [func FilterPackage(pkg \*Package, f Filter) bool](#FilterPackage)
-   [func Fprint(w io.Writer, fset \*token.FileSet, x any, f
    FieldFilter) error](#Fprint)
-   [func Inspect(node Node, f func(Node) bool)](#Inspect)
-   [func IsExported(name string) bool](#IsExported)
-   [func IsGenerated(file \*File) bool](#IsGenerated)
-   [func NotNilFilter(\_ string, v reflect.Value) bool](#NotNilFilter)
-   [func PackageExports(pkg \*Package) bool](#PackageExports)
-   [func Print(fset \*token.FileSet, x any) error](#Print)
-   [func SortImports(fset \*token.FileSet, f \*File)](#SortImports)
-   [func Walk(v Visitor, node Node)](#Walk)
-   [type ArrayType](#ArrayType)
-   [func (x \*ArrayType) End() token.Pos](#ArrayType.End)
-   [func (x \*ArrayType) Pos() token.Pos](#ArrayType.Pos)
-   [type AssignStmt](#AssignStmt)
-   [func (s \*AssignStmt) End() token.Pos](#AssignStmt.End)
-   [func (s \*AssignStmt) Pos() token.Pos](#AssignStmt.Pos)
-   [type BadDecl](#BadDecl)
-   [func (d \*BadDecl) End() token.Pos](#BadDecl.End)
-   [func (d \*BadDecl) Pos() token.Pos](#BadDecl.Pos)
-   [type BadExpr](#BadExpr)
-   [func (x \*BadExpr) End() token.Pos](#BadExpr.End)
-   [func (x \*BadExpr) Pos() token.Pos](#BadExpr.Pos)
-   [type BadStmt](#BadStmt)
-   [func (s \*BadStmt) End() token.Pos](#BadStmt.End)
-   [func (s \*BadStmt) Pos() token.Pos](#BadStmt.Pos)
-   [type BasicLit](#BasicLit)
-   [func (x \*BasicLit) End() token.Pos](#BasicLit.End)
-   [func (x \*BasicLit) Pos() token.Pos](#BasicLit.Pos)
-   [type BinaryExpr](#BinaryExpr)
-   [func (x \*BinaryExpr) End() token.Pos](#BinaryExpr.End)
-   [func (x \*BinaryExpr) Pos() token.Pos](#BinaryExpr.Pos)
-   [type BlockStmt](#BlockStmt)
-   [func (s \*BlockStmt) End() token.Pos](#BlockStmt.End)
-   [func (s \*BlockStmt) Pos() token.Pos](#BlockStmt.Pos)
-   [type BranchStmt](#BranchStmt)
-   [func (s \*BranchStmt) End() token.Pos](#BranchStmt.End)
-   [func (s \*BranchStmt) Pos() token.Pos](#BranchStmt.Pos)
-   [type CallExpr](#CallExpr)
-   [func (x \*CallExpr) End() token.Pos](#CallExpr.End)
-   [func (x \*CallExpr) Pos() token.Pos](#CallExpr.Pos)
-   [type CaseClause](#CaseClause)
-   [func (s \*CaseClause) End() token.Pos](#CaseClause.End)
-   [func (s \*CaseClause) Pos() token.Pos](#CaseClause.Pos)
-   [type ChanDir](#ChanDir)
-   [type ChanType](#ChanType)
-   [func (x \*ChanType) End() token.Pos](#ChanType.End)
-   [func (x \*ChanType) Pos() token.Pos](#ChanType.Pos)
-   [type CommClause](#CommClause)
-   [func (s \*CommClause) End() token.Pos](#CommClause.End)
-   [func (s \*CommClause) Pos() token.Pos](#CommClause.Pos)
-   [type Comment](#Comment)
-   [func (c \*Comment) End() token.Pos](#Comment.End)
-   [func (c \*Comment) Pos() token.Pos](#Comment.Pos)
-   [type CommentGroup](#CommentGroup)
-   [func (g \*CommentGroup) End() token.Pos](#CommentGroup.End)
-   [func (g \*CommentGroup) Pos() token.Pos](#CommentGroup.Pos)
-   [func (g \*CommentGroup) Text() string](#CommentGroup.Text)
-   [type CommentMap](#CommentMap)
-   [func NewCommentMap(fset \*token.FileSet, node Node, comments
    \[\]\*CommentGroup) CommentMap](#NewCommentMap)
-   [func (cmap CommentMap) Comments()
    \[\]\*CommentGroup](#CommentMap.Comments)
-   [func (cmap CommentMap) Filter(node Node)
    CommentMap](#CommentMap.Filter)
-   [func (cmap CommentMap) String() string](#CommentMap.String)
-   [func (cmap CommentMap) Update(old, new Node)
    Node](#CommentMap.Update)
-   [type CompositeLit](#CompositeLit)
-   [func (x \*CompositeLit) End() token.Pos](#CompositeLit.End)
-   [func (x \*CompositeLit) Pos() token.Pos](#CompositeLit.Pos)
-   [type Decl](#Decl)
-   [type DeclStmt](#DeclStmt)
-   [func (s \*DeclStmt) End() token.Pos](#DeclStmt.End)
-   [func (s \*DeclStmt) Pos() token.Pos](#DeclStmt.Pos)
-   [type DeferStmt](#DeferStmt)
-   [func (s \*DeferStmt) End() token.Pos](#DeferStmt.End)
-   [func (s \*DeferStmt) Pos() token.Pos](#DeferStmt.Pos)
-   [type Ellipsis](#Ellipsis)
-   [func (x \*Ellipsis) End() token.Pos](#Ellipsis.End)
-   [func (x \*Ellipsis) Pos() token.Pos](#Ellipsis.Pos)
-   [type EmptyStmt](#EmptyStmt)
-   [func (s \*EmptyStmt) End() token.Pos](#EmptyStmt.End)
-   [func (s \*EmptyStmt) Pos() token.Pos](#EmptyStmt.Pos)
-   [type Expr](#Expr)
-   [type ExprStmt](#ExprStmt)
-   [func (s \*ExprStmt) End() token.Pos](#ExprStmt.End)
-   [func (s \*ExprStmt) Pos() token.Pos](#ExprStmt.Pos)
-   [type Field](#Field)
-   [func (f \*Field) End() token.Pos](#Field.End)
-   [func (f \*Field) Pos() token.Pos](#Field.Pos)
-   [type FieldFilter](#FieldFilter)
-   [type FieldList](#FieldList)
-   [func (f \*FieldList) End() token.Pos](#FieldList.End)
-   [func (f \*FieldList) NumFields() int](#FieldList.NumFields)
-   [func (f \*FieldList) Pos() token.Pos](#FieldList.Pos)
-   [type File](#File)
-   [func MergePackageFiles(pkg \*Package, mode MergeMode)
    \*File](#MergePackageFiles)
-   [func (f \*File) End() token.Pos](#File.End)
-   [func (f \*File) Pos() token.Pos](#File.Pos)
-   [type Filter](#Filter)
-   [type ForStmt](#ForStmt)
-   [func (s \*ForStmt) End() token.Pos](#ForStmt.End)
-   [func (s \*ForStmt) Pos() token.Pos](#ForStmt.Pos)
-   [type FuncDecl](#FuncDecl)
-   [func (d \*FuncDecl) End() token.Pos](#FuncDecl.End)
-   [func (d \*FuncDecl) Pos() token.Pos](#FuncDecl.Pos)
-   [type FuncLit](#FuncLit)
-   [func (x \*FuncLit) End() token.Pos](#FuncLit.End)
-   [func (x \*FuncLit) Pos() token.Pos](#FuncLit.Pos)
-   [type FuncType](#FuncType)
-   [func (x \*FuncType) End() token.Pos](#FuncType.End)
-   [func (x \*FuncType) Pos() token.Pos](#FuncType.Pos)
-   [type GenDecl](#GenDecl)
-   [func (d \*GenDecl) End() token.Pos](#GenDecl.End)
-   [func (d \*GenDecl) Pos() token.Pos](#GenDecl.Pos)
-   [type GoStmt](#GoStmt)
-   [func (s \*GoStmt) End() token.Pos](#GoStmt.End)
-   [func (s \*GoStmt) Pos() token.Pos](#GoStmt.Pos)
-   [type Ident](#Ident)
-   [func NewIdent(name string) \*Ident](#NewIdent)
-   [func (x \*Ident) End() token.Pos](#Ident.End)
-   [func (id \*Ident) IsExported() bool](#Ident.IsExported)
-   [func (x \*Ident) Pos() token.Pos](#Ident.Pos)
-   [func (id \*Ident) String() string](#Ident.String)
-   [type IfStmt](#IfStmt)
-   [func (s \*IfStmt) End() token.Pos](#IfStmt.End)
-   [func (s \*IfStmt) Pos() token.Pos](#IfStmt.Pos)
-   [type ImportSpec](#ImportSpec)
-   [func (s \*ImportSpec) End() token.Pos](#ImportSpec.End)
-   [func (s \*ImportSpec) Pos() token.Pos](#ImportSpec.Pos)
-   [type Importer](#Importer)
-   [type IncDecStmt](#IncDecStmt)
-   [func (s \*IncDecStmt) End() token.Pos](#IncDecStmt.End)
-   [func (s \*IncDecStmt) Pos() token.Pos](#IncDecStmt.Pos)
-   [type IndexExpr](#IndexExpr)
-   [func (x \*IndexExpr) End() token.Pos](#IndexExpr.End)
-   [func (x \*IndexExpr) Pos() token.Pos](#IndexExpr.Pos)
-   [type IndexListExpr](#IndexListExpr)
-   [func (x \*IndexListExpr) End() token.Pos](#IndexListExpr.End)
-   [func (x \*IndexListExpr) Pos() token.Pos](#IndexListExpr.Pos)
-   [type InterfaceType](#InterfaceType)
-   [func (x \*InterfaceType) End() token.Pos](#InterfaceType.End)
-   [func (x \*InterfaceType) Pos() token.Pos](#InterfaceType.Pos)
-   [type KeyValueExpr](#KeyValueExpr)
-   [func (x \*KeyValueExpr) End() token.Pos](#KeyValueExpr.End)
-   [func (x \*KeyValueExpr) Pos() token.Pos](#KeyValueExpr.Pos)
-   [type LabeledStmt](#LabeledStmt)
-   [func (s \*LabeledStmt) End() token.Pos](#LabeledStmt.End)
-   [func (s \*LabeledStmt) Pos() token.Pos](#LabeledStmt.Pos)
-   [type MapType](#MapType)
-   [func (x \*MapType) End() token.Pos](#MapType.End)
-   [func (x \*MapType) Pos() token.Pos](#MapType.Pos)
-   [type MergeMode](#MergeMode)
-   [type Node](#Node)
-   [type ObjKind](#ObjKind)
-   [func (kind ObjKind) String() string](#ObjKind.String)
-   [type Object](#Object)
-   [func NewObj(kind ObjKind, name string) \*Object](#NewObj)
-   [func (obj \*Object) Pos() token.Pos](#Object.Pos)
-   [type Package](#Package)
-   [func NewPackage(fset \*token.FileSet, files map\[string\]\*File,
    importer Importer, universe \*Scope) (\*Package,
    error)](#NewPackage)
-   [func (p \*Package) End() token.Pos](#Package.End)
-   [func (p \*Package) Pos() token.Pos](#Package.Pos)
-   [type ParenExpr](#ParenExpr)
-   [func (x \*ParenExpr) End() token.Pos](#ParenExpr.End)
-   [func (x \*ParenExpr) Pos() token.Pos](#ParenExpr.Pos)
-   [type RangeStmt](#RangeStmt)
-   [func (s \*RangeStmt) End() token.Pos](#RangeStmt.End)
-   [func (s \*RangeStmt) Pos() token.Pos](#RangeStmt.Pos)
-   [type ReturnStmt](#ReturnStmt)
-   [func (s \*ReturnStmt) End() token.Pos](#ReturnStmt.End)
-   [func (s \*ReturnStmt) Pos() token.Pos](#ReturnStmt.Pos)
-   [type Scope](#Scope)
-   [func NewScope(outer \*Scope) \*Scope](#NewScope)
-   [func (s \*Scope) Insert(obj \*Object) (alt
    \*Object)](#Scope.Insert)
-   [func (s \*Scope) Lookup(name string) \*Object](#Scope.Lookup)
-   [func (s \*Scope) String() string](#Scope.String)
-   [type SelectStmt](#SelectStmt)
-   [func (s \*SelectStmt) End() token.Pos](#SelectStmt.End)
-   [func (s \*SelectStmt) Pos() token.Pos](#SelectStmt.Pos)
-   [type SelectorExpr](#SelectorExpr)
-   [func (x \*SelectorExpr) End() token.Pos](#SelectorExpr.End)
-   [func (x \*SelectorExpr) Pos() token.Pos](#SelectorExpr.Pos)
-   [type SendStmt](#SendStmt)
-   [func (s \*SendStmt) End() token.Pos](#SendStmt.End)
-   [func (s \*SendStmt) Pos() token.Pos](#SendStmt.Pos)
-   [type SliceExpr](#SliceExpr)
-   [func (x \*SliceExpr) End() token.Pos](#SliceExpr.End)
-   [func (x \*SliceExpr) Pos() token.Pos](#SliceExpr.Pos)
-   [type Spec](#Spec)
-   [type StarExpr](#StarExpr)
-   [func (x \*StarExpr) End() token.Pos](#StarExpr.End)
-   [func (x \*StarExpr) Pos() token.Pos](#StarExpr.Pos)
-   [type Stmt](#Stmt)
-   [type StructType](#StructType)
-   [func (x \*StructType) End() token.Pos](#StructType.End)
-   [func (x \*StructType) Pos() token.Pos](#StructType.Pos)
-   [type SwitchStmt](#SwitchStmt)
-   [func (s \*SwitchStmt) End() token.Pos](#SwitchStmt.End)
-   [func (s \*SwitchStmt) Pos() token.Pos](#SwitchStmt.Pos)
-   [type TypeAssertExpr](#TypeAssertExpr)
-   [func (x \*TypeAssertExpr) End() token.Pos](#TypeAssertExpr.End)
-   [func (x \*TypeAssertExpr) Pos() token.Pos](#TypeAssertExpr.Pos)
-   [type TypeSpec](#TypeSpec)
-   [func (s \*TypeSpec) End() token.Pos](#TypeSpec.End)
-   [func (s \*TypeSpec) Pos() token.Pos](#TypeSpec.Pos)
-   [type TypeSwitchStmt](#TypeSwitchStmt)
-   [func (s \*TypeSwitchStmt) End() token.Pos](#TypeSwitchStmt.End)
-   [func (s \*TypeSwitchStmt) Pos() token.Pos](#TypeSwitchStmt.Pos)
-   [type UnaryExpr](#UnaryExpr)
-   [func (x \*UnaryExpr) End() token.Pos](#UnaryExpr.End)
-   [func (x \*UnaryExpr) Pos() token.Pos](#UnaryExpr.Pos)
-   [type ValueSpec](#ValueSpec)
-   [func (s \*ValueSpec) End() token.Pos](#ValueSpec.End)
-   [func (s \*ValueSpec) Pos() token.Pos](#ValueSpec.Pos)
-   [type Visitor](#Visitor)

 
### Examples

[CommentMap](#example_CommentMap)

[Inspect](#example_Inspect)

[Print](#example_Print)


### Package files

ast.go commentmap.go filter.go import.go print.go resolve.go scope.go
walk.go

func FileExports 
----------------

```go
func FileExports(src *File) bool
```

FileExports trims the AST for a Go source file in place such that only
exported nodes remain: all top-level identifiers which are not exported
and their associated information (such as type, initial value, or
function body) are removed. Non-exported fields and methods of exported
types are stripped. The File.Comments list is not changed.

FileExports reports whether there are exported declarations.

func FilterDecl 
---------------

```go
func FilterDecl(decl Decl, f Filter) bool
```

FilterDecl trims the AST for a Go declaration in place by removing all
names (including struct field and interface method names, but not from
parameter lists) that don\'t pass through the filter f.

FilterDecl reports whether there are any declared names left after
filtering.

func FilterFile 
---------------

```go
func FilterFile(src *File, f Filter) bool
```

FilterFile trims the AST for a Go file in place by removing all names
from top-level declarations (including struct field and interface method
names, but not from parameter lists) that don\'t pass through the filter
f. If the declaration is empty afterwards, the declaration is removed
from the AST. Import declarations are always removed. The File.Comments
list is not changed.

FilterFile reports whether there are any top-level declarations left
after filtering.

func FilterPackage 
------------------

```go
func FilterPackage(pkg *Package, f Filter) bool
```

FilterPackage trims the AST for a Go package in place by removing all
names from top-level declarations (including struct field and interface
method names, but not from parameter lists) that don\'t pass through the
filter f. If the declaration is empty afterwards, the declaration is
removed from the AST. The pkg.Files list is not changed, so that file
names and top-level package comments don\'t get lost.

FilterPackage reports whether there are any top-level declarations left
after filtering.

func Fprint 
-----------

```go
func Fprint(w io.Writer, fset *token.FileSet, x any, f FieldFilter) error
```

Fprint prints the (sub-)tree starting at AST node x to w. If fset !=
nil, position information is interpreted relative to that file set.
Otherwise positions are printed as integer values (file set specific
offsets).

A non-nil FieldFilter f may be provided to control the output: struct
fields for which f(fieldname, fieldvalue) is true are printed; all
others are filtered from the output. Unexported struct fields are never
printed.

func Inspect 
------------

```go
func Inspect(node Node, f func(Node) bool)
```

Inspect traverses an AST in depth-first order: It starts by calling
f(node); node must not be nil. If f returns true, Inspect invokes f
recursively for each of the non-nil children of node, followed by a call
of f(nil).

#### [Example]

This example demonstrates how to inspect the AST of a Go program.

Code:

```go
// src is the input for which we want to inspect the AST.
src := `
package p
const c = 1.0
var X = f(3.14)*2 + c
`

// Create the AST by parsing src.
fset := token.NewFileSet() // positions are relative to fset
f, err := parser.ParseFile(fset, "src.go", src, 0)
if err != nil {
    panic(err)
}

// Inspect the AST and print all identifiers and literals.
ast.Inspect(f, func(n ast.Node) bool {
    var s string
    switch x := n.(type) {
    case *ast.BasicLit:
        s = x.Value
    case *ast.Ident:
        s = x.Name
    }
    if s != "" {
        fmt.Printf("%s:\t%s\n", fset.Position(n.Pos()), s)
    }
    return true
})
```

Output:

```go
src.go:2:9:    p
src.go:3:7: c
src.go:3:11:    1.0
src.go:4:5: X
src.go:4:9: f
src.go:4:11:    3.14
src.go:4:17:    2
src.go:4:21:    c
```

func IsExported 
---------------

```go
func IsExported(name string) bool
```

IsExported reports whether name starts with an upper-case letter.

func IsGenerated 
-------------------------------------------------

```go
func IsGenerated(file *File) bool
```

IsGenerated reports whether the file was generated by a program, not
handwritten, by detecting the special comment described at
https://go.dev/s/generatedcode>.

The syntax tree must have been parsed with the ParseComments flag.
Example:

```go
f, err := parser.ParseFile(fset, filename, src, parser.ParseComments|parser.PackageClauseOnly)
if err != nil { ... }
gen := ast.IsGenerated(f)
```

func NotNilFilter 
-----------------

```go
func NotNilFilter(_ string, v reflect.Value) bool
```

NotNilFilter returns true for field values that are not nil; it returns
false otherwise.

func PackageExports 
-------------------

```go
func PackageExports(pkg *Package) bool
```

PackageExports trims the AST for a Go package in place such that only
exported nodes remain. The pkg.Files list is not changed, so that file
names and top-level package comments don\'t get lost.

PackageExports reports whether there are exported declarations; it
returns false otherwise.

func Print 
----------

```go
func Print(fset *token.FileSet, x any) error
```

Print prints x to standard output, skipping nil fields. Print(fset, x)
is the same as Fprint(os.Stdout, fset, x, NotNilFilter).

#### [Example]

This example shows what an AST looks like when printed for debugging.

Code:

```go
// src is the input for which we want to print the AST.
src := `
package main
func main() {
    println("Hello, World!")
}
`

// Create the AST by parsing src.
fset := token.NewFileSet() // positions are relative to fset
f, err := parser.ParseFile(fset, "", src, 0)
if err != nil {
    panic(err)
}

// Print the AST.
ast.Print(fset, f)
```

Output:

```go
     0  *ast.File {
     1  .  Package: 2:1
     2  .  Name: *ast.Ident {
     3  .  .  NamePos: 2:9
     4  .  .  Name: "main"
     5  .  }
     6  .  Decls: []ast.Decl (len = 1) {
     7  .  .  0: *ast.FuncDecl {
     8  .  .  .  Name: *ast.Ident {
     9  .  .  .  .  NamePos: 3:6
    10  .  .  .  .  Name: "main"
    11  .  .  .  .  Obj: *ast.Object {
    12  .  .  .  .  .  Kind: func
    13  .  .  .  .  .  Name: "main"
    14  .  .  .  .  .  Decl: *(obj @ 7)
    15  .  .  .  .  }
    16  .  .  .  }
    17  .  .  .  Type: *ast.FuncType {
    18  .  .  .  .  Func: 3:1
    19  .  .  .  .  Params: *ast.FieldList {
    20  .  .  .  .  .  Opening: 3:10
    21  .  .  .  .  .  Closing: 3:11
    22  .  .  .  .  }
    23  .  .  .  }
    24  .  .  .  Body: *ast.BlockStmt {
    25  .  .  .  .  Lbrace: 3:13
    26  .  .  .  .  List: []ast.Stmt (len = 1) {
    27  .  .  .  .  .  0: *ast.ExprStmt {
    28  .  .  .  .  .  .  X: *ast.CallExpr {
    29  .  .  .  .  .  .  .  Fun: *ast.Ident {
    30  .  .  .  .  .  .  .  .  NamePos: 4:2
    31  .  .  .  .  .  .  .  .  Name: "println"
    32  .  .  .  .  .  .  .  }
    33  .  .  .  .  .  .  .  Lparen: 4:9
    34  .  .  .  .  .  .  .  Args: []ast.Expr (len = 1) {
    35  .  .  .  .  .  .  .  .  0: *ast.BasicLit {
    36  .  .  .  .  .  .  .  .  .  ValuePos: 4:10
    37  .  .  .  .  .  .  .  .  .  Kind: STRING
    38  .  .  .  .  .  .  .  .  .  Value: "\"Hello, World!\""
    39  .  .  .  .  .  .  .  .  }
    40  .  .  .  .  .  .  .  }
    41  .  .  .  .  .  .  .  Ellipsis: -
    42  .  .  .  .  .  .  .  Rparen: 4:25
    43  .  .  .  .  .  .  }
    44  .  .  .  .  .  }
    45  .  .  .  .  }
    46  .  .  .  .  Rbrace: 5:1
    47  .  .  .  }
    48  .  .  }
    49  .  }
    50  .  FileStart: 1:1
    51  .  FileEnd: 5:3
    52  .  Scope: *ast.Scope {
    53  .  .  Objects: map[string]*ast.Object (len = 1) {
    54  .  .  .  "main": *(obj @ 11)
    55  .  .  }
    56  .  }
    57  .  Unresolved: []*ast.Ident (len = 1) {
    58  .  .  0: *(obj @ 29)
    59  .  }
    60  .  GoVersion: ""
    61  }
```

func SortImports 
----------------

```go
func SortImports(fset *token.FileSet, f *File)
```

SortImports sorts runs of consecutive import lines in import blocks in
f. It also removes duplicate imports when it is possible to do so
without data loss.

func Walk 
---------

```go
func Walk(v Visitor, node Node)
```

Walk traverses an AST in depth-first order: It starts by calling
v.Visit(node); node must not be nil. If the visitor w returned by
v.Visit(node) is not nil, Walk is invoked recursively with visitor w for
each of the non-nil children of node, followed by a call of
w.Visit(nil).

type ArrayType 
--------------

An ArrayType node represents an array or slice type.

```go
type ArrayType struct {
    Lbrack token.Pos // position of "["
    Len    Expr      // Ellipsis node for [...]T array types, nil for slice types
    Elt    Expr      // element type
}
```

### func (\*ArrayType) End 

```go
func (x *ArrayType) End() token.Pos
```

### func (\*ArrayType) Pos 

```go
func (x *ArrayType) Pos() token.Pos
```

type AssignStmt 
---------------

An AssignStmt node represents an assignment or a short variable
declaration.

```go
type AssignStmt struct {
    Lhs    []Expr
    TokPos token.Pos   // position of Tok
    Tok    token.Token // assignment token, DEFINE
    Rhs    []Expr
}
```

### func (\*AssignStmt) End 

```go
func (s *AssignStmt) End() token.Pos
```

### func (\*AssignStmt) Pos 

```go
func (s *AssignStmt) Pos() token.Pos
```

type BadDecl 
------------

A BadDecl node is a placeholder for a declaration containing syntax
errors for which a correct declaration node cannot be created.

```go
type BadDecl struct {
    From, To token.Pos // position range of bad declaration
}
```

### func (\*BadDecl) End 

```go
func (d *BadDecl) End() token.Pos
```

### func (\*BadDecl) Pos 

```go
func (d *BadDecl) Pos() token.Pos
```

type BadExpr 
------------

A BadExpr node is a placeholder for an expression containing syntax
errors for which a correct expression node cannot be created.

```go
type BadExpr struct {
    From, To token.Pos // position range of bad expression
}
```

### func (\*BadExpr) End 

```go
func (x *BadExpr) End() token.Pos
```

### func (\*BadExpr) Pos 

```go
func (x *BadExpr) Pos() token.Pos
```

type BadStmt 
------------

A BadStmt node is a placeholder for statements containing syntax errors
for which no correct statement nodes can be created.

```go
type BadStmt struct {
    From, To token.Pos // position range of bad statement
}
```

### func (\*BadStmt) End 

```go
func (s *BadStmt) End() token.Pos
```

### func (\*BadStmt) Pos 

```go
func (s *BadStmt) Pos() token.Pos
```

type BasicLit 
-------------

A BasicLit node represents a literal of basic type.

```go
type BasicLit struct {
    ValuePos token.Pos   // literal position
    Kind     token.Token // token.INT, token.FLOAT, token.IMAG, token.CHAR, or token.STRING
    Value    string      // literal string; e.g. 42, 0x7f, 3.14, 1e-9, 2.4i, 'a', '\x7f', "foo" or `\m\n\o`
}
```

### func (\*BasicLit) End 

```go
func (x *BasicLit) End() token.Pos
```

### func (\*BasicLit) Pos 

```go
func (x *BasicLit) Pos() token.Pos
```

type BinaryExpr 
---------------

A BinaryExpr node represents a binary expression.

```go
type BinaryExpr struct {
    X     Expr        // left operand
    OpPos token.Pos   // position of Op
    Op    token.Token // operator
    Y     Expr        // right operand
}
```

### func (\*BinaryExpr) End 

```go
func (x *BinaryExpr) End() token.Pos
```

### func (\*BinaryExpr) Pos 

```go
func (x *BinaryExpr) Pos() token.Pos
```

type BlockStmt 
--------------

A BlockStmt node represents a braced statement list.

```go
type BlockStmt struct {
    Lbrace token.Pos // position of "{"
    List   []Stmt
    Rbrace token.Pos // position of "}", if any (may be absent due to syntax error)
}
```

### func (\*BlockStmt) End 

```go
func (s *BlockStmt) End() token.Pos
```

### func (\*BlockStmt) Pos 

```go
func (s *BlockStmt) Pos() token.Pos
```

type BranchStmt 
---------------

A BranchStmt node represents a break, continue, goto, or fallthrough
statement.

```go
type BranchStmt struct {
    TokPos token.Pos   // position of Tok
    Tok    token.Token // keyword token (BREAK, CONTINUE, GOTO, FALLTHROUGH)
    Label  *Ident      // label name; or nil
}
```

### func (\*BranchStmt) End 

```go
func (s *BranchStmt) End() token.Pos
```

### func (\*BranchStmt) Pos 

```go
func (s *BranchStmt) Pos() token.Pos
```

type CallExpr 
-------------

A CallExpr node represents an expression followed by an argument list.

```go
type CallExpr struct {
    Fun      Expr      // function expression
    Lparen   token.Pos // position of "("
    Args     []Expr    // function arguments; or nil
    Ellipsis token.Pos // position of "..." (token.NoPos if there is no "...")
    Rparen   token.Pos // position of ")"
}
```

### func (\*CallExpr) End 

```go
func (x *CallExpr) End() token.Pos
```

### func (\*CallExpr) Pos 

```go
func (x *CallExpr) Pos() token.Pos
```

type CaseClause 
---------------

A CaseClause represents a case of an expression or type switch
statement.

```go
type CaseClause struct {
    Case  token.Pos // position of "case" or "default" keyword
    List  []Expr    // list of expressions or types; nil means default case
    Colon token.Pos // position of ":"
    Body  []Stmt    // statement list; or nil
}
```

### func (\*CaseClause) End 

```go
func (s *CaseClause) End() token.Pos
```

### func (\*CaseClause) Pos 

```go
func (s *CaseClause) Pos() token.Pos
```

type ChanDir 
------------

The direction of a channel type is indicated by a bit mask including one
or both of the following constants.

```go
type ChanDir int
```

```go
const (
    SEND ChanDir = 1 << iota
    RECV
)
```

type ChanType 
-------------

A ChanType node represents a channel type.

```go
type ChanType struct {
    Begin token.Pos // position of "chan" keyword or "<-" (whichever comes first)
    Arrow token.Pos // position of "<-" (token.NoPos if there is no "<-"); added in Go 1.1
    Dir   ChanDir   // channel direction
    Value Expr      // value type
}
```

### func (\*ChanType) End 

```go
func (x *ChanType) End() token.Pos
```

### func (\*ChanType) Pos 

```go
func (x *ChanType) Pos() token.Pos
```

type CommClause 
---------------

A CommClause node represents a case of a select statement.

```go
type CommClause struct {
    Case  token.Pos // position of "case" or "default" keyword
    Comm  Stmt      // send or receive statement; nil means default case
    Colon token.Pos // position of ":"
    Body  []Stmt    // statement list; or nil
}
```

### func (\*CommClause) End 

```go
func (s *CommClause) End() token.Pos
```

### func (\*CommClause) Pos 

```go
func (s *CommClause) Pos() token.Pos
```

type Comment 
------------

A Comment node represents a single //-style or /\*-style comment.

The Text field contains the comment text without carriage returns (\\r)
that may have been present in the source. Because a comment\'s end
position is computed using len(Text), the position reported by End()
does not match the true source end position for comments containing
carriage returns.

```go
type Comment struct {
    Slash token.Pos // position of "/" starting the comment
    Text  string    // comment text (excluding '\n' for //-style comments)
}
```

### func (\*Comment) End 

```go
func (c *Comment) End() token.Pos
```

### func (\*Comment) Pos 

```go
func (c *Comment) Pos() token.Pos
```

type CommentGroup 
-----------------

A CommentGroup represents a sequence of comments with no other tokens
and no empty lines between.

```go
type CommentGroup struct {
    List []*Comment // len(List) > 0
}
```

### func (\*CommentGroup) End 

```go
func (g *CommentGroup) End() token.Pos
```

### func (\*CommentGroup) Pos 

```go
func (g *CommentGroup) Pos() token.Pos
```

### func (\*CommentGroup) Text 

```go
func (g *CommentGroup) Text() string
```

Text returns the text of the comment. Comment markers (//, /\*, and
\*/), the first space of a line comment, and leading and trailing empty
lines are removed. Comment directives like \"//line\" and
\"//go:noinline\" are also removed. Multiple empty lines are reduced to
one, and trailing space on lines is trimmed. Unless the result is empty,
it is newline-terminated.

type CommentMap 
----------------------------------------------

A CommentMap maps an AST node to a list of comment groups associated
with it. See NewCommentMap for a description of the association.

```go
type CommentMap map[Node][]*CommentGroup
```

#### [Example]

This example illustrates how to remove a variable declaration in a Go
program while maintaining correct comment association using an
ast.CommentMap.

Code:

```go
// src is the input for which we create the AST that we
// are going to manipulate.
src := `
// This is the package comment.
package main

// This comment is associated with the hello constant.
const hello = "Hello, World!" // line comment 1

// This comment is associated with the foo variable.
var foo = hello // line comment 2

// This comment is associated with the main function.
func main() {
    fmt.Println(hello) // line comment 3
}
`

// Create the AST by parsing src.
fset := token.NewFileSet() // positions are relative to fset
f, err := parser.ParseFile(fset, "src.go", src, parser.ParseComments)
if err != nil {
    panic(err)
}

// Create an ast.CommentMap from the ast.File's comments.
// This helps keeping the association between comments
// and AST nodes.
cmap := ast.NewCommentMap(fset, f, f.Comments)

// Remove the first variable declaration from the list of declarations.
for i, decl := range f.Decls {
    if gen, ok := decl.(*ast.GenDecl); ok && gen.Tok == token.VAR {
        copy(f.Decls[i:], f.Decls[i+1:])
        f.Decls = f.Decls[:len(f.Decls)-1]
        break
    }
}

// Use the comment map to filter comments that don't belong anymore
// (the comments associated with the variable declaration), and create
// the new comments list.
f.Comments = cmap.Filter(f).Comments()

// Print the modified AST.
var buf strings.Builder
if err := format.Node(&buf, fset, f); err != nil {
    panic(err)
}
fmt.Printf("%s", buf.String())
```

Output:

```go
// This is the package comment.
package main

// This comment is associated with the hello constant.
const hello = "Hello, World!" // line comment 1

// This comment is associated with the main function.
func main() {
    fmt.Println(hello) // line comment 3
}
```

### func NewCommentMap 

```go
func NewCommentMap(fset *token.FileSet, node Node, comments []*CommentGroup) CommentMap
```

NewCommentMap creates a new comment map by associating comment groups of
the comments list with the nodes of the AST specified by node.

A comment group g is associated with a node n if:

-   g starts on the same line as n ends
-   g starts on the line immediately following n, and there is at least
    one empty line after g and before the next node
-   g starts before n and is not associated to the node before n via the
    previous rules

NewCommentMap tries to associate a comment group to the \"largest\" node
possible: For instance, if the comment is a line comment trailing an
assignment, the comment is associated with the entire assignment rather
than just the last operand in the assignment.

### func (CommentMap) Comments 

```go
func (cmap CommentMap) Comments() []*CommentGroup
```

Comments returns the list of comment groups in the comment map. The
result is sorted in source order.

### func (CommentMap) Filter 

```go
func (cmap CommentMap) Filter(node Node) CommentMap
```

Filter returns a new comment map consisting of only those entries of
cmap for which a corresponding node exists in the AST specified by node.

### func (CommentMap) String 

```go
func (cmap CommentMap) String() string
```

### func (CommentMap) Update 

```go
func (cmap CommentMap) Update(old, new Node) Node
```

Update replaces an old node in the comment map with the new node and
returns the new node. Comments that were associated with the old node
are associated with the new node.

type CompositeLit 
-----------------

A CompositeLit node represents a composite literal.

```go
type CompositeLit struct {
    Type       Expr      // literal type; or nil
    Lbrace     token.Pos // position of "{"
    Elts       []Expr    // list of composite elements; or nil
    Rbrace     token.Pos // position of "}"
    Incomplete bool      // true if (source) expressions are missing in the Elts list; added in Go 1.11
}
```

### func (\*CompositeLit) End 

```go
func (x *CompositeLit) End() token.Pos
```

### func (\*CompositeLit) Pos 

```go
func (x *CompositeLit) Pos() token.Pos
```

type Decl 
---------

All declaration nodes implement the Decl interface.

```go
type Decl interface {
    Node
    // contains filtered or unexported methods
}
```

type DeclStmt 
-------------

A DeclStmt node represents a declaration in a statement list.

```go
type DeclStmt struct {
    Decl Decl // *GenDecl with CONST, TYPE, or VAR token
}
```

### func (\*DeclStmt) End 

```go
func (s *DeclStmt) End() token.Pos
```

### func (\*DeclStmt) Pos 

```go
func (s *DeclStmt) Pos() token.Pos
```

type DeferStmt 
--------------

A DeferStmt node represents a defer statement.

```go
type DeferStmt struct {
    Defer token.Pos // position of "defer" keyword
    Call  *CallExpr
}
```

### func (\*DeferStmt) End 

```go
func (s *DeferStmt) End() token.Pos
```

### func (\*DeferStmt) Pos 

```go
func (s *DeferStmt) Pos() token.Pos
```

type Ellipsis 
-------------

An Ellipsis node stands for the \"\...\" type in a parameter list or the
\"\...\" length in an array type.

```go
type Ellipsis struct {
    Ellipsis token.Pos // position of "..."
    Elt      Expr      // ellipsis element type (parameter lists only); or nil
}
```

### func (\*Ellipsis) End 

```go
func (x *Ellipsis) End() token.Pos
```

### func (\*Ellipsis) Pos 

```go
func (x *Ellipsis) Pos() token.Pos
```

type EmptyStmt 
--------------

An EmptyStmt node represents an empty statement. The \"position\" of the
empty statement is the position of the immediately following (explicit
or implicit) semicolon.

```go
type EmptyStmt struct {
    Semicolon token.Pos // position of following ";"
    Implicit  bool      // if set, ";" was omitted in the source; added in Go 1.5
}
```

### func (\*EmptyStmt) End 

```go
func (s *EmptyStmt) End() token.Pos
```

### func (\*EmptyStmt) Pos 

```go
func (s *EmptyStmt) Pos() token.Pos
```

type Expr 
---------

All expression nodes implement the Expr interface.

```go
type Expr interface {
    Node
    // contains filtered or unexported methods
}
```

type ExprStmt 
-------------

An ExprStmt node represents a (stand-alone) expression in a statement
list.

```go
type ExprStmt struct {
    X Expr // expression
}
```

### func (\*ExprStmt) End 

```go
func (s *ExprStmt) End() token.Pos
```

### func (\*ExprStmt) Pos 

```go
func (s *ExprStmt) Pos() token.Pos
```

type Field 
----------

A Field represents a Field declaration list in a struct type, a method
list in an interface type, or a parameter/result declaration in a
signature. Field.Names is nil for unnamed parameters (parameter lists
which only contain types) and embedded struct fields. In the latter
case, the field name is the type name.

```go
type Field struct {
    Doc     *CommentGroup // associated documentation; or nil
    Names   []*Ident      // field/method/(type) parameter names; or nil
    Type    Expr          // field/method/parameter type; or nil
    Tag     *BasicLit     // field tag; or nil
    Comment *CommentGroup // line comments; or nil
}
```

### func (\*Field) End 

```go
func (f *Field) End() token.Pos
```

### func (\*Field) Pos 

```go
func (f *Field) Pos() token.Pos
```

type FieldFilter 
----------------

A FieldFilter may be provided to Fprint to control the output.

```go
type FieldFilter func(name string, value reflect.Value) bool
```

type FieldList 
--------------

A FieldList represents a list of Fields, enclosed by parentheses, curly
braces, or square brackets.

```go
type FieldList struct {
    Opening token.Pos // position of opening parenthesis/brace/bracket, if any
    List    []*Field  // field list; or nil
    Closing token.Pos // position of closing parenthesis/brace/bracket, if any
}
```

### func (\*FieldList) End 

```go
func (f *FieldList) End() token.Pos
```

### func (\*FieldList) NumFields 

```go
func (f *FieldList) NumFields() int
```

NumFields returns the number of parameters or struct fields represented
by a FieldList.

### func (\*FieldList) Pos 

```go
func (f *FieldList) Pos() token.Pos
```

type File 
---------

A File node represents a Go source file.

The Comments list contains all comments in the source file in order of
appearance, including the comments that are pointed to from other nodes
via Doc and Comment fields.

For correct printing of source code containing comments (using packages
go/format and go/printer), special care must be taken to update comments
when a File\'s syntax tree is modified: For printing, comments are
interspersed between tokens based on their position. If syntax tree
nodes are removed or moved, relevant comments in their vicinity must
also be removed (from the File.Comments list) or moved accordingly (by
updating their positions). A CommentMap may be used to facilitate some
of these operations.

Whether and how a comment is associated with a node depends on the
interpretation of the syntax tree by the manipulating program: Except
for Doc and Comment comments directly associated with nodes, the
remaining comments are \"free-floating\" (see also issues \#18593,
\#20744).

```go
type File struct {
    Doc     *CommentGroup // associated documentation; or nil
    Package token.Pos     // position of "package" keyword
    Name    *Ident        // package name
    Decls   []Decl        // top-level declarations; or nil

    FileStart, FileEnd token.Pos       // start and end of entire file; added in Go 1.20
    Scope              *Scope          // package scope (this file only)
    Imports            []*ImportSpec   // imports in this file
    Unresolved         []*Ident        // unresolved identifiers in this file
    Comments           []*CommentGroup // list of all comments in the source file
    GoVersion          string          // minimum Go version required by //go:build or // +build directives; added in Go 1.21
}
```

### func MergePackageFiles 

```go
func MergePackageFiles(pkg *Package, mode MergeMode) *File
```

MergePackageFiles creates a file AST by merging the ASTs of the files
belonging to a package. The mode flags control merging behavior.

### func (\*File) End 

```go
func (f *File) End() token.Pos
```

End returns the end of the last declaration in the file. (Use FileEnd
for the end of the entire file.)

### func (\*File) Pos 

```go
func (f *File) Pos() token.Pos
```

Pos returns the position of the package declaration. (Use FileStart for
the start of the entire file.)

type Filter 
-----------

```go
type Filter func(string) bool
```

type ForStmt 
------------

A ForStmt represents a for statement.

```go
type ForStmt struct {
    For  token.Pos // position of "for" keyword
    Init Stmt      // initialization statement; or nil
    Cond Expr      // condition; or nil
    Post Stmt      // post iteration statement; or nil
    Body *BlockStmt
}
```

### func (\*ForStmt) End 

```go
func (s *ForStmt) End() token.Pos
```

### func (\*ForStmt) Pos 

```go
func (s *ForStmt) Pos() token.Pos
```

type FuncDecl 
-------------

A FuncDecl node represents a function declaration.

```go
type FuncDecl struct {
    Doc  *CommentGroup // associated documentation; or nil
    Recv *FieldList    // receiver (methods); or nil (functions)
    Name *Ident        // function/method name
    Type *FuncType     // function signature: type and value parameters, results, and position of "func" keyword
    Body *BlockStmt    // function body; or nil for external (non-Go) function
}
```

### func (\*FuncDecl) End 

```go
func (d *FuncDecl) End() token.Pos
```

### func (\*FuncDecl) Pos 

```go
func (d *FuncDecl) Pos() token.Pos
```

type FuncLit 
------------

A FuncLit node represents a function literal.

```go
type FuncLit struct {
    Type *FuncType  // function type
    Body *BlockStmt // function body
}
```

### func (\*FuncLit) End 

```go
func (x *FuncLit) End() token.Pos
```

### func (\*FuncLit) Pos 

```go
func (x *FuncLit) Pos() token.Pos
```

type FuncType 
-------------

A FuncType node represents a function type.

```go
type FuncType struct {
    Func       token.Pos  // position of "func" keyword (token.NoPos if there is no "func")
    TypeParams *FieldList // type parameters; or nil; added in Go 1.18
    Params     *FieldList // (incoming) parameters; non-nil
    Results    *FieldList // (outgoing) results; or nil
}
```

### func (\*FuncType) End 

```go
func (x *FuncType) End() token.Pos
```

### func (\*FuncType) Pos 

```go
func (x *FuncType) Pos() token.Pos
```

type GenDecl 
------------

A GenDecl node (generic declaration node) represents an import,
constant, type or variable declaration. A valid Lparen position
(Lparen.IsValid()) indicates a parenthesized declaration.

Relationship between Tok value and Specs element type:

```go
token.IMPORT  *ImportSpec
token.CONST   *ValueSpec
token.TYPE    *TypeSpec
token.VAR     *ValueSpec
```

```go
type GenDecl struct {
    Doc    *CommentGroup // associated documentation; or nil
    TokPos token.Pos     // position of Tok
    Tok    token.Token   // IMPORT, CONST, TYPE, or VAR
    Lparen token.Pos     // position of '(', if any
    Specs  []Spec
    Rparen token.Pos // position of ')', if any
}
```

### func (\*GenDecl) End 

```go
func (d *GenDecl) End() token.Pos
```

### func (\*GenDecl) Pos 

```go
func (d *GenDecl) Pos() token.Pos
```

type GoStmt 
-----------

A GoStmt node represents a go statement.

```go
type GoStmt struct {
    Go   token.Pos // position of "go" keyword
    Call *CallExpr
}
```

### func (\*GoStmt) End 

```go
func (s *GoStmt) End() token.Pos
```

### func (\*GoStmt) Pos 

```go
func (s *GoStmt) Pos() token.Pos
```

type Ident 
----------

An Ident node represents an identifier.

```go
type Ident struct {
    NamePos token.Pos // identifier position
    Name    string    // identifier name
    Obj     *Object   // denoted object; or nil
}
```

### func NewIdent 

```go
func NewIdent(name string) *Ident
```

NewIdent creates a new Ident without position. Useful for ASTs generated
by code other than the Go parser.

### func (\*Ident) End 

```go
func (x *Ident) End() token.Pos
```

### func (\*Ident) IsExported 

```go
func (id *Ident) IsExported() bool
```

IsExported reports whether id starts with an upper-case letter.

### func (\*Ident) Pos 

```go
func (x *Ident) Pos() token.Pos
```

### func (\*Ident) String 

```go
func (id *Ident) String() string
```

type IfStmt 
-----------

An IfStmt node represents an if statement.

```go
type IfStmt struct {
    If   token.Pos // position of "if" keyword
    Init Stmt      // initialization statement; or nil
    Cond Expr      // condition
    Body *BlockStmt
    Else Stmt // else branch; or nil
}
```

### func (\*IfStmt) End 

```go
func (s *IfStmt) End() token.Pos
```

### func (\*IfStmt) Pos 

```go
func (s *IfStmt) Pos() token.Pos
```

type ImportSpec 
---------------

An ImportSpec node represents a single package import.

```go
type ImportSpec struct {
    Doc     *CommentGroup // associated documentation; or nil
    Name    *Ident        // local package name (including "."); or nil
    Path    *BasicLit     // import path
    Comment *CommentGroup // line comments; or nil
    EndPos  token.Pos     // end of spec (overrides Path.Pos if nonzero)
}
```

### func (\*ImportSpec) End 

```go
func (s *ImportSpec) End() token.Pos
```

### func (\*ImportSpec) Pos 

```go
func (s *ImportSpec) Pos() token.Pos
```

type Importer 
-------------

An Importer resolves import paths to package Objects. The imports map
records the packages already imported, indexed by package id (canonical
import path). An Importer must determine the canonical import path and
check the map to see if it is already present in the imports map. If so,
the Importer can return the map entry. Otherwise, the Importer should
load the package data for the given path into a new \*Object (pkg),
record pkg in the imports map, and then return pkg.

```go
type Importer func(imports map[string]*Object, path string) (pkg *Object, err error)
```

type IncDecStmt 
---------------

An IncDecStmt node represents an increment or decrement statement.

```go
type IncDecStmt struct {
    X      Expr
    TokPos token.Pos   // position of Tok
    Tok    token.Token // INC or DEC
}
```

### func (\*IncDecStmt) End 

```go
func (s *IncDecStmt) End() token.Pos
```

### func (\*IncDecStmt) Pos 

```go
func (s *IncDecStmt) Pos() token.Pos
```

type IndexExpr 
--------------

An IndexExpr node represents an expression followed by an index.

```go
type IndexExpr struct {
    X      Expr      // expression
    Lbrack token.Pos // position of "["
    Index  Expr      // index expression
    Rbrack token.Pos // position of "]"
}
```

### func (\*IndexExpr) End 

```go
func (x *IndexExpr) End() token.Pos
```

### func (\*IndexExpr) Pos 

```go
func (x *IndexExpr) Pos() token.Pos
```

type IndexListExpr 
---------------------------------------------------

An IndexListExpr node represents an expression followed by multiple
indices.

```go
type IndexListExpr struct {
    X       Expr      // expression
    Lbrack  token.Pos // position of "["
    Indices []Expr    // index expressions
    Rbrack  token.Pos // position of "]"
}
```

### func (\*IndexListExpr) End 

```go
func (x *IndexListExpr) End() token.Pos
```

### func (\*IndexListExpr) Pos 

```go
func (x *IndexListExpr) Pos() token.Pos
```

type InterfaceType 
------------------

An InterfaceType node represents an interface type.

```go
type InterfaceType struct {
    Interface  token.Pos  // position of "interface" keyword
    Methods    *FieldList // list of embedded interfaces, methods, or types
    Incomplete bool       // true if (source) methods or types are missing in the Methods list
}
```

### func (\*InterfaceType) End 

```go
func (x *InterfaceType) End() token.Pos
```

### func (\*InterfaceType) Pos 

```go
func (x *InterfaceType) Pos() token.Pos
```

type KeyValueExpr 
-----------------

A KeyValueExpr node represents (key : value) pairs in composite
literals.

```go
type KeyValueExpr struct {
    Key   Expr
    Colon token.Pos // position of ":"
    Value Expr
}
```

### func (\*KeyValueExpr) End 

```go
func (x *KeyValueExpr) End() token.Pos
```

### func (\*KeyValueExpr) Pos 

```go
func (x *KeyValueExpr) Pos() token.Pos
```

type LabeledStmt 
----------------

A LabeledStmt node represents a labeled statement.

```go
type LabeledStmt struct {
    Label *Ident
    Colon token.Pos // position of ":"
    Stmt  Stmt
}
```

### func (\*LabeledStmt) End 

```go
func (s *LabeledStmt) End() token.Pos
```

### func (\*LabeledStmt) Pos 

```go
func (s *LabeledStmt) Pos() token.Pos
```

type MapType 
------------

A MapType node represents a map type.

```go
type MapType struct {
    Map   token.Pos // position of "map" keyword
    Key   Expr
    Value Expr
}
```

### func (\*MapType) End 

```go
func (x *MapType) End() token.Pos
```

### func (\*MapType) Pos 

```go
func (x *MapType) Pos() token.Pos
```

type MergeMode 
--------------

The MergeMode flags control the behavior of MergePackageFiles.

```go
type MergeMode uint
```

```go
const (
    // If set, duplicate function declarations are excluded.
    FilterFuncDuplicates MergeMode = 1 << iota
    // If set, comments that are not associated with a specific
    // AST node (as Doc or Comment) are excluded.
    FilterUnassociatedComments
    // If set, duplicate import declarations are excluded.
    FilterImportDuplicates
)
```

type Node 
---------

All node types implement the Node interface.

```go
type Node interface {
    Pos() token.Pos // position of first character belonging to the node
    End() token.Pos // position of first character immediately after the node
}
```

type ObjKind 
------------

ObjKind describes what an object represents.

```go
type ObjKind int
```

The list of possible Object kinds.

```go
const (
    Bad ObjKind = iota // for error handling
    Pkg                // package
    Con                // constant
    Typ                // type
    Var                // variable
    Fun                // function or method
    Lbl                // label
)
```

### func (ObjKind) String 

```go
func (kind ObjKind) String() string
```

type Object 
-----------

An Object describes a named language entity such as a package, constant,
type, variable, function (incl. methods), or label.

The Data fields contains object-specific data:

```go
Kind    Data type         Data value
Pkg     *Scope            package scope
Con     int               iota for the respective declaration
```

```go
type Object struct {
    Kind ObjKind
    Name string // declared name
    Decl any    // corresponding Field, XxxSpec, FuncDecl, LabeledStmt, AssignStmt, Scope; or nil
    Data any    // object-specific data; or nil
    Type any    // placeholder for type information; may be nil
}
```

### func NewObj 

```go
func NewObj(kind ObjKind, name string) *Object
```

NewObj creates a new object of a given kind and name.

### func (\*Object) Pos 

```go
func (obj *Object) Pos() token.Pos
```

Pos computes the source position of the declaration of an object name.
The result may be an invalid position if it cannot be computed (obj.Decl
may be nil or not correct).

type Package 
------------

A Package node represents a set of source files collectively building a
Go package.

```go
type Package struct {
    Name    string             // package name
    Scope   *Scope             // package scope across all files
    Imports map[string]*Object // map of package id -> package object
    Files   map[string]*File   // Go source files by filename
}
```

### func NewPackage 

```go
func NewPackage(fset *token.FileSet, files map[string]*File, importer Importer, universe *Scope) (*Package, error)
```

NewPackage creates a new Package node from a set of File nodes. It
resolves unresolved identifiers across files and updates each file\'s
Unresolved list accordingly. If a non-nil importer and universe scope
are provided, they are used to resolve identifiers not declared in any
of the package files. Any remaining unresolved identifiers are reported
as undeclared. If the files belong to different packages, one package
name is selected and files with different package names are reported and
then ignored. The result is a package node and a scanner.ErrorList if
there were errors.

### func (\*Package) End 

```go
func (p *Package) End() token.Pos
```

### func (\*Package) Pos 

```go
func (p *Package) Pos() token.Pos
```

type ParenExpr 
--------------

A ParenExpr node represents a parenthesized expression.

```go
type ParenExpr struct {
    Lparen token.Pos // position of "("
    X      Expr      // parenthesized expression
    Rparen token.Pos // position of ")"
}
```

### func (\*ParenExpr) End 

```go
func (x *ParenExpr) End() token.Pos
```

### func (\*ParenExpr) Pos 

```go
func (x *ParenExpr) Pos() token.Pos
```

type RangeStmt 
--------------

A RangeStmt represents a for statement with a range clause.

```go
type RangeStmt struct {
    For        token.Pos   // position of "for" keyword
    Key, Value Expr        // Key, Value may be nil
    TokPos     token.Pos   // position of Tok; invalid if Key == nil
    Tok        token.Token // ILLEGAL if Key == nil, ASSIGN, DEFINE
    Range      token.Pos   // position of "range" keyword; added in Go 1.20
    X          Expr        // value to range over
    Body       *BlockStmt
}
```

### func (\*RangeStmt) End 

```go
func (s *RangeStmt) End() token.Pos
```

### func (\*RangeStmt) Pos 

```go
func (s *RangeStmt) Pos() token.Pos
```

type ReturnStmt 
---------------

A ReturnStmt node represents a return statement.

```go
type ReturnStmt struct {
    Return  token.Pos // position of "return" keyword
    Results []Expr    // result expressions; or nil
}
```

### func (\*ReturnStmt) End 

```go
func (s *ReturnStmt) End() token.Pos
```

### func (\*ReturnStmt) Pos 

```go
func (s *ReturnStmt) Pos() token.Pos
```

type Scope 
----------

A Scope maintains the set of named language entities declared in the
scope and a link to the immediately surrounding (outer) scope.

```go
type Scope struct {
    Outer   *Scope
    Objects map[string]*Object
}
```

### func NewScope 

```go
func NewScope(outer *Scope) *Scope
```

NewScope creates a new scope nested in the outer scope.

### func (\*Scope) Insert 

```go
func (s *Scope) Insert(obj *Object) (alt *Object)
```

Insert attempts to insert a named object obj into the scope s. If the
scope already contains an object alt with the same name, Insert leaves
the scope unchanged and returns alt. Otherwise it inserts obj and
returns nil.

### func (\*Scope) Lookup 

```go
func (s *Scope) Lookup(name string) *Object
```

Lookup returns the object with the given name if it is found in scope s,
otherwise it returns nil. Outer scopes are ignored.

### func (\*Scope) String 

```go
func (s *Scope) String() string
```

Debugging support

type SelectStmt 
---------------

A SelectStmt node represents a select statement.

```go
type SelectStmt struct {
    Select token.Pos  // position of "select" keyword
    Body   *BlockStmt // CommClauses only
}
```

### func (\*SelectStmt) End 

```go
func (s *SelectStmt) End() token.Pos
```

### func (\*SelectStmt) Pos 

```go
func (s *SelectStmt) Pos() token.Pos
```

type SelectorExpr 
-----------------

A SelectorExpr node represents an expression followed by a selector.

```go
type SelectorExpr struct {
    X   Expr   // expression
    Sel *Ident // field selector
}
```

### func (\*SelectorExpr) End 

```go
func (x *SelectorExpr) End() token.Pos
```

### func (\*SelectorExpr) Pos 

```go
func (x *SelectorExpr) Pos() token.Pos
```

type SendStmt 
-------------

A SendStmt node represents a send statement.

```go
type SendStmt struct {
    Chan  Expr
    Arrow token.Pos // position of "<-"
    Value Expr
}
```

### func (\*SendStmt) End 

```go
func (s *SendStmt) End() token.Pos
```

### func (\*SendStmt) Pos 

```go
func (s *SendStmt) Pos() token.Pos
```

type SliceExpr 
--------------

A SliceExpr node represents an expression followed by slice indices.

```go
type SliceExpr struct {
    X      Expr      // expression
    Lbrack token.Pos // position of "["
    Low    Expr      // begin of slice range; or nil
    High   Expr      // end of slice range; or nil
    Max    Expr      // maximum capacity of slice; or nil; added in Go 1.2
    Slice3 bool      // true if 3-index slice (2 colons present); added in Go 1.2
    Rbrack token.Pos // position of "]"
}
```

### func (\*SliceExpr) End 

```go
func (x *SliceExpr) End() token.Pos
```

### func (\*SliceExpr) Pos 

```go
func (x *SliceExpr) Pos() token.Pos
```

type Spec 
---------

The Spec type stands for any of \*ImportSpec, \*ValueSpec, and
\*TypeSpec.

```go
type Spec interface {
    Node
    // contains filtered or unexported methods
}
```

type StarExpr 
-------------

A StarExpr node represents an expression of the form \"\*\" Expression.
Semantically it could be a unary \"\*\" expression, or a pointer type.

```go
type StarExpr struct {
    Star token.Pos // position of "*"
    X    Expr      // operand
}
```

### func (\*StarExpr) End 

```go
func (x *StarExpr) End() token.Pos
```

### func (\*StarExpr) Pos 

```go
func (x *StarExpr) Pos() token.Pos
```

type Stmt 
---------

All statement nodes implement the Stmt interface.

```go
type Stmt interface {
    Node
    // contains filtered or unexported methods
}
```

type StructType 
---------------

A StructType node represents a struct type.

```go
type StructType struct {
    Struct     token.Pos  // position of "struct" keyword
    Fields     *FieldList // list of field declarations
    Incomplete bool       // true if (source) fields are missing in the Fields list
}
```

### func (\*StructType) End 

```go
func (x *StructType) End() token.Pos
```

### func (\*StructType) Pos 

```go
func (x *StructType) Pos() token.Pos
```

type SwitchStmt 
---------------

A SwitchStmt node represents an expression switch statement.

```go
type SwitchStmt struct {
    Switch token.Pos  // position of "switch" keyword
    Init   Stmt       // initialization statement; or nil
    Tag    Expr       // tag expression; or nil
    Body   *BlockStmt // CaseClauses only
}
```

### func (\*SwitchStmt) End 

```go
func (s *SwitchStmt) End() token.Pos
```

### func (\*SwitchStmt) Pos 

```go
func (s *SwitchStmt) Pos() token.Pos
```

type TypeAssertExpr 
-------------------

A TypeAssertExpr node represents an expression followed by a type
assertion.

```go
type TypeAssertExpr struct {
    X      Expr      // expression
    Lparen token.Pos // position of "("; added in Go 1.2
    Type   Expr      // asserted type; nil means type switch X.(type)
    Rparen token.Pos // position of ")"; added in Go 1.2
}
```

### func (\*TypeAssertExpr) End 

```go
func (x *TypeAssertExpr) End() token.Pos
```

### func (\*TypeAssertExpr) Pos 

```go
func (x *TypeAssertExpr) Pos() token.Pos
```

type TypeSpec 
-------------

A TypeSpec node represents a type declaration (TypeSpec production).

```go
type TypeSpec struct {
    Doc        *CommentGroup // associated documentation; or nil
    Name       *Ident        // type name
    TypeParams *FieldList    // type parameters; or nil; added in Go 1.18
    Assign     token.Pos     // position of '=', if any; added in Go 1.9
    Type       Expr          // *Ident, *ParenExpr, *SelectorExpr, *StarExpr, or any of the *XxxTypes
    Comment    *CommentGroup // line comments; or nil
}
```

### func (\*TypeSpec) End 

```go
func (s *TypeSpec) End() token.Pos
```

### func (\*TypeSpec) Pos 

```go
func (s *TypeSpec) Pos() token.Pos
```

type TypeSwitchStmt 
-------------------

A TypeSwitchStmt node represents a type switch statement.

```go
type TypeSwitchStmt struct {
    Switch token.Pos  // position of "switch" keyword
    Init   Stmt       // initialization statement; or nil
    Assign Stmt       // x := y.(type) or y.(type)
    Body   *BlockStmt // CaseClauses only
}
```

### func (\*TypeSwitchStmt) End 

```go
func (s *TypeSwitchStmt) End() token.Pos
```

### func (\*TypeSwitchStmt) Pos 

```go
func (s *TypeSwitchStmt) Pos() token.Pos
```

type UnaryExpr 
--------------

A UnaryExpr node represents a unary expression. Unary \"\*\" expressions
are represented via StarExpr nodes.

```go
type UnaryExpr struct {
    OpPos token.Pos   // position of Op
    Op    token.Token // operator
    X     Expr        // operand
}
```

### func (\*UnaryExpr) End 

```go
func (x *UnaryExpr) End() token.Pos
```

### func (\*UnaryExpr) Pos 

```go
func (x *UnaryExpr) Pos() token.Pos
```

type ValueSpec 
--------------

A ValueSpec node represents a constant or variable declaration
(ConstSpec or VarSpec production).

```go
type ValueSpec struct {
    Doc     *CommentGroup // associated documentation; or nil
    Names   []*Ident      // value names (len(Names) > 0)
    Type    Expr          // value type; or nil
    Values  []Expr        // initial values; or nil
    Comment *CommentGroup // line comments; or nil
}
```

### func (\*ValueSpec) End 

```go
func (s *ValueSpec) End() token.Pos
```

### func (\*ValueSpec) Pos 

```go
func (s *ValueSpec) Pos() token.Pos
```

type Visitor 
------------

A Visitor\'s Visit method is invoked for each node encountered by Walk.
If the result visitor w is not nil, Walk visits each of the children of
node with the visitor w, followed by a call of w.Visit(nil).

```go
type Visitor interface {
    Visit(node Node) (w Visitor)
}
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/go/ast/>

