Package fstest
==============

-   `import "testing/fstest"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package fstest implements support for testing implementations and users
of file systems.

Index 
-----

-   [func TestFS(fsys fs.FS, expected \...string) error](#TestFS)
-   [type MapFS](#MapFS)
-   [func (fsys MapFS) Glob(pattern string) (\[\]string,
    error)](#MapFS.Glob)
-   [func (fsys MapFS) Open(name string) (fs.File, error)](#MapFS.Open)
-   [func (fsys MapFS) ReadDir(name string) (\[\]fs.DirEntry,
    error)](#MapFS.ReadDir)
-   [func (fsys MapFS) ReadFile(name string) (\[\]byte,
    error)](#MapFS.ReadFile)
-   [func (fsys MapFS) Stat(name string) (fs.FileInfo,
    error)](#MapFS.Stat)
-   [func (fsys MapFS) Sub(dir string) (fs.FS, error)](#MapFS.Sub)
-   [type MapFile](#MapFile)

### Package files

mapfs.go testfs.go

func TestFS 
--------------------------------------------

```go
func TestFS(fsys fs.FS, expected ...string) error
```

TestFS tests a file system implementation. It walks the entire tree of
files in fsys, opening and checking that each file behaves correctly. It
also checks that the file system contains at least the expected files.
As a special case, if no expected files are listed, fsys must be empty.
Otherwise, fsys must contain at least the listed files; it can also
contain others. The contents of fsys must not change concurrently with
TestFS.

If TestFS finds any misbehaviors, it returns an error reporting all of
them. The error text spans multiple lines, one per detected misbehavior.

Typical usage inside a test is:

```go
if err := fstest.TestFS(myFS, "file/that/should/be/present"); err != nil {
    t.Fatal(err)
}
```

type MapFS 
-------------------------------------------

A MapFS is a simple in-memory file system for use in tests, represented
as a map from path names (arguments to Open) to information about the
files or directories they represent.

The map need not include parent directories for files contained in the
map; those will be synthesized if needed. But a directory can still be
included by setting the MapFile.Mode\'s ModeDir bit; this may be
necessary for detailed control over the directory\'s FileInfo or to
create an empty directory.

File system operations read directly from the map, so that the file
system can be changed by editing the map as needed. An implication is
that file system operations must not run concurrently with changes to
the map, which would be a race. Another implication is that opening or
reading a directory requires iterating over the entire map, so a MapFS
should typically be used with not more than a few hundred entries or
directory reads.

```go
type MapFS map[string]*MapFile
```

### func (MapFS) Glob 

```go
func (fsys MapFS) Glob(pattern string) ([]string, error)
```

### func (MapFS) Open 

```go
func (fsys MapFS) Open(name string) (fs.File, error)
```

Open opens the named file.

### func (MapFS) ReadDir 

```go
func (fsys MapFS) ReadDir(name string) ([]fs.DirEntry, error)
```

### func (MapFS) ReadFile 

```go
func (fsys MapFS) ReadFile(name string) ([]byte, error)
```

### func (MapFS) Stat 

```go
func (fsys MapFS) Stat(name string) (fs.FileInfo, error)
```

### func (MapFS) Sub 

```go
func (fsys MapFS) Sub(dir string) (fs.FS, error)
```

type MapFile 
---------------------------------------------

A MapFile describes a single file in a MapFS.

```go
type MapFile struct {
    Data    []byte      // file content
    Mode    fs.FileMode // FileInfo.Mode
    ModTime time.Time   // FileInfo.ModTime
    Sys     any         // FileInfo.Sys
}
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/testing/fstest/>

