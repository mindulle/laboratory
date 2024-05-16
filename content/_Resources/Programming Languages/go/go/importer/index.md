Package importer
================

-   `import "go/importer"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package importer provides access to export data importers.

Index 
-----

-   [func Default() types.Importer](#Default)
-   [func For(compiler string, lookup Lookup) types.Importer](#For)
-   [func ForCompiler(fset \*token.FileSet, compiler string, lookup
    Lookup) types.Importer](#ForCompiler)
-   [type Lookup](#Lookup)

### Package files

importer.go

func Default 
-------------------------------------------

```go
func Default() types.Importer
```

Default returns an Importer for the compiler that built the running
binary. If available, the result implements types.ImporterFrom.

func For 
---------------------------------------

```go
func For(compiler string, lookup Lookup) types.Importer
```

For calls ForCompiler with a new FileSet.

Deprecated: Use ForCompiler, which populates a FileSet with the
positions of objects created by the importer.

func ForCompiler 
-------------------------------------------------

```go
func ForCompiler(fset *token.FileSet, compiler string, lookup Lookup) types.Importer
```

ForCompiler returns an Importer for importing from installed packages
for the compilers \"gc\" and \"gccgo\", or for importing directly from
the source if the compiler argument is \"source\". In this latter case,
importing may fail under circumstances where the exported API is not
entirely defined in pure Go source code (if the package API depends on
cgo-defined entities, the type checker won\'t have access to those).

The lookup function is called each time the resulting importer needs to
resolve an import path. In this mode the importer can only be invoked
with canonical import paths (not relative or absolute ones); it is
assumed that the translation to canonical import paths is being done by
the client of the importer.

A lookup function must be provided for correct module-aware operation.
Deprecated: If lookup is nil, for backwards-compatibility, the importer
will attempt to resolve imports in the \$GOPATH workspace.

type Lookup 
------------------------------------------

A Lookup function returns a reader to access package data for a given
import path, or an error if no matching package is found.

```go
type Lookup func(path string) (io.ReadCloser, error)
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/go/importer/>

