Package filepath
================

-   `import "path/filepath"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package filepath implements utility routines for manipulating filename
paths in a way compatible with the target operating system-defined file
paths.

The filepath package uses either forward slashes or backslashes,
depending on the operating system. To process paths such as URLs that
always use forward slashes regardless of the operating system, see the
path package.

Index 
-----

-   [Constants](#pkg-constants)
-   [Variables](#pkg-variables)
-   [func Abs(path string) (string, error)](#Abs)
-   [func Base(path string) string](#Base)
-   [func Clean(path string) string](#Clean)
-   [func Dir(path string) string](#Dir)
-   [func EvalSymlinks(path string) (string, error)](#EvalSymlinks)
-   [func Ext(path string) string](#Ext)
-   [func FromSlash(path string) string](#FromSlash)
-   [func Glob(pattern string) (matches \[\]string, err error)](#Glob)
-   [func HasPrefix(p, prefix string) bool](#HasPrefix)
-   [func IsAbs(path string) bool](#IsAbs)
-   [func IsLocal(path string) bool](#IsLocal)
-   [func Join(elem \...string) string](#Join)
-   [func Match(pattern, name string) (matched bool, err error)](#Match)
-   [func Rel(basepath, targpath string) (string, error)](#Rel)
-   [func Split(path string) (dir, file string)](#Split)
-   [func SplitList(path string) \[\]string](#SplitList)
-   [func ToSlash(path string) string](#ToSlash)
-   [func VolumeName(path string) string](#VolumeName)
-   [func Walk(root string, fn WalkFunc) error](#Walk)
-   [func WalkDir(root string, fn fs.WalkDirFunc) error](#WalkDir)
-   [type WalkFunc](#WalkFunc)

 
### Examples

[Base](#example_Base)

[Dir](#example_Dir)

[Ext](#example_Ext)

[IsAbs](#example_IsAbs)

[Join](#example_Join)

[Match](#example_Match)

[Rel](#example_Rel)

[Split](#example_Split)

[SplitList](#example_SplitList)

[Walk](#example_Walk)


### Package files

match.go path.go path\_nonwindows.go path\_unix.go symlink.go
symlink\_unix.go

Constants 
---------

```go
const (
    Separator     = os.PathSeparator
    ListSeparator = os.PathListSeparator
)
```

Variables 
---------

ErrBadPattern indicates a pattern was malformed.

```go
var ErrBadPattern = errors.New("syntax error in pattern")
```

SkipAll is used as a return value from WalkFuncs to indicate that all
remaining files and directories are to be skipped. It is not returned as
an error by any function.

```go
var SkipAll error = fs.SkipAll
```

SkipDir is used as a return value from WalkFuncs to indicate that the
directory named in the call is to be skipped. It is not returned as an
error by any function.

```go
var SkipDir error = fs.SkipDir
```

func Abs 
--------

```go
func Abs(path string) (string, error)
```

Abs returns an absolute representation of path. If the path is not
absolute it will be joined with the current working directory to turn it
into an absolute path. The absolute path name for a given file is not
guaranteed to be unique. Abs calls Clean on the result.

func Base 
---------

```go
func Base(path string) string
```

Base returns the last element of path. Trailing path separators are
removed before extracting the last element. If the path is empty, Base
returns \".\". If the path consists entirely of separators, Base returns
a single separator.

#### [Example]

Code:

```go
fmt.Println("On Unix:")
fmt.Println(filepath.Base("/foo/bar/baz.js"))
fmt.Println(filepath.Base("/foo/bar/baz"))
fmt.Println(filepath.Base("/foo/bar/baz/"))
fmt.Println(filepath.Base("dev.txt"))
fmt.Println(filepath.Base("../todo.txt"))
fmt.Println(filepath.Base(".."))
fmt.Println(filepath.Base("."))
fmt.Println(filepath.Base("/"))
fmt.Println(filepath.Base(""))
```

Output:

```go
On Unix:
baz.js
baz
baz
dev.txt
todo.txt
..
.
/
.
```

func Clean 
----------

```go
func Clean(path string) string
```

Clean returns the shortest path name equivalent to path by purely
lexical processing. It applies the following rules iteratively until no
further processing can be done:

1.  Replace multiple Separator elements with a single one.
2.  Eliminate each . path name element (the current directory).
3.  Eliminate each inner .. path name element (the parent directory)
    along with the non-.. element that precedes it.
4.  Eliminate .. elements that begin a rooted path: that is, replace
    \"/..\" by \"/\" at the beginning of a path, assuming Separator is
    \'/\'.

The returned path ends in a slash only if it represents a root
directory, such as \"/\" on Unix or \`C:\\\` on Windows.

Finally, any occurrences of slash are replaced by Separator.

If the result of this process is an empty string, Clean returns the
string \".\".

On Windows, Clean does not modify the volume name other than to replace
occurrences of \"/\" with \`\\\`. For example,
Clean(\"//host/share/../x\") returns \`\\\\host\\share\\x\`.

See also Rob Pike, "Lexical File Names in Plan 9 or Getting Dot-Dot
Right," https://9p.io/sys/doc/lexnames.html>

func Dir 
--------

```go
func Dir(path string) string
```

Dir returns all but the last element of path, typically the path\'s
directory. After dropping the final element, Dir calls Clean on the path
and trailing slashes are removed. If the path is empty, Dir returns
\".\". If the path consists entirely of separators, Dir returns a single
separator. The returned path does not end in a separator unless it is
the root directory.

#### [Example]

Code:

```go
fmt.Println("On Unix:")
fmt.Println(filepath.Dir("/foo/bar/baz.js"))
fmt.Println(filepath.Dir("/foo/bar/baz"))
fmt.Println(filepath.Dir("/foo/bar/baz/"))
fmt.Println(filepath.Dir("/dirty//path///"))
fmt.Println(filepath.Dir("dev.txt"))
fmt.Println(filepath.Dir("../todo.txt"))
fmt.Println(filepath.Dir(".."))
fmt.Println(filepath.Dir("."))
fmt.Println(filepath.Dir("/"))
fmt.Println(filepath.Dir(""))
```

Output:

```go
On Unix:
/foo/bar
/foo/bar
/foo/bar/baz
/dirty/path
.
..
.
.
/
.
```

func EvalSymlinks 
-----------------

```go
func EvalSymlinks(path string) (string, error)
```

EvalSymlinks returns the path name after the evaluation of any symbolic
links. If path is relative the result will be relative to the current
directory, unless one of the components is an absolute symbolic link.
EvalSymlinks calls Clean on the result.

func Ext 
--------

```go
func Ext(path string) string
```

Ext returns the file name extension used by path. The extension is the
suffix beginning at the final dot in the final element of path; it is
empty if there is no dot.

#### [Example]

Code:

```go
fmt.Printf("No dots: %q\n", filepath.Ext("index"))
fmt.Printf("One dot: %q\n", filepath.Ext("index.js"))
fmt.Printf("Two dots: %q\n", filepath.Ext("main.test.js"))
```

Output:

```go
No dots: ""
One dot: ".js"
Two dots: ".js"
```

func FromSlash 
--------------

```go
func FromSlash(path string) string
```

FromSlash returns the result of replacing each slash (\'/\') character
in path with a separator character. Multiple slashes are replaced by
multiple separators.

func Glob 
---------

```go
func Glob(pattern string) (matches []string, err error)
```

Glob returns the names of all files matching pattern or nil if there is
no matching file. The syntax of patterns is the same as in Match. The
pattern may describe hierarchical names such as /usr/\*/bin/ed (assuming
the Separator is \'/\').

Glob ignores file system errors such as I/O errors reading directories.
The only possible returned error is ErrBadPattern, when pattern is
malformed.

func HasPrefix 
--------------

```go
func HasPrefix(p, prefix string) bool
```

HasPrefix exists for historical compatibility and should not be used.

Deprecated: HasPrefix does not respect path boundaries and does not
ignore case when required.

func IsAbs 
----------

```go
func IsAbs(path string) bool
```

IsAbs reports whether the path is absolute.

#### [Example]

Code:

```go
fmt.Println("On Unix:")
fmt.Println(filepath.IsAbs("/home/gopher"))
fmt.Println(filepath.IsAbs(".bashrc"))
fmt.Println(filepath.IsAbs(".."))
fmt.Println(filepath.IsAbs("."))
fmt.Println(filepath.IsAbs("/"))
fmt.Println(filepath.IsAbs(""))
```

Output:

```go
On Unix:
true
false
false
false
true
false
```

func IsLocal 
---------------------------------------------

```go
func IsLocal(path string) bool
```

IsLocal reports whether path, using lexical analysis only, has all of
these properties:

-   is within the subtree rooted at the directory in which path is
    evaluated
-   is not an absolute path
-   is not empty
-   on Windows, is not a reserved name such as \"NUL\"

If IsLocal(path) returns true, then Join(base, path) will always produce
a path contained within base and Clean(path) will always produce an
unrooted path with no \"..\" path elements.

IsLocal is a purely lexical operation. In particular, it does not
account for the effect of any symbolic links that may exist in the
filesystem.

func Join 
---------

```go
func Join(elem ...string) string
```

Join joins any number of path elements into a single path, separating
them with an OS specific Separator. Empty elements are ignored. The
result is Cleaned. However, if the argument list is empty or all its
elements are empty, Join returns an empty string. On Windows, the result
will only be a UNC path if the first non-empty element is a UNC path.

#### [Example]

Code:

```go
fmt.Println("On Unix:")
fmt.Println(filepath.Join("a", "b", "c"))
fmt.Println(filepath.Join("a", "b/c"))
fmt.Println(filepath.Join("a/b", "c"))
fmt.Println(filepath.Join("a/b", "/c"))

fmt.Println(filepath.Join("a/b", "../../../xyz"))
```

Output:

```go
On Unix:
a/b/c
a/b/c
a/b/c
a/b/c
../xyz
```

func Match 
----------

```go
func Match(pattern, name string) (matched bool, err error)
```

Match reports whether name matches the shell file name pattern. The
pattern syntax is:

```go
pattern:
    { term }
term:
    '*'         matches any sequence of non-Separator characters
    '?'         matches any single non-Separator character
    '[' [ '^' ] { character-range } ']'
                character class (must be non-empty)
    c           matches character c (c != '*', '?', '\\', '[')
    '\\' c      matches character c

character-range:
    c           matches character c (c != '\\', '-', ']')
    '\\' c      matches character c
    lo '-' hi   matches character c for lo <= c <= hi
```

Match requires pattern to match all of name, not just a substring. The
only possible returned error is ErrBadPattern, when pattern is
malformed.

On Windows, escaping is disabled. Instead, \'\\\\\' is treated as path
separator.

#### [Example]

Code:

```go
fmt.Println("On Unix:")
fmt.Println(filepath.Match("/home/catch/*", "/home/catch/foo"))
fmt.Println(filepath.Match("/home/catch/*", "/home/catch/foo/bar"))
fmt.Println(filepath.Match("/home/?opher", "/home/gopher"))
fmt.Println(filepath.Match("/home/\\*", "/home/*"))
```

Output:

```go
On Unix:
true <nil>
false <nil>
true <nil>
true <nil>
```

func Rel 
--------

```go
func Rel(basepath, targpath string) (string, error)
```

Rel returns a relative path that is lexically equivalent to targpath
when joined to basepath with an intervening separator. That is,
Join(basepath, Rel(basepath, targpath)) is equivalent to targpath
itself. On success, the returned path will always be relative to
basepath, even if basepath and targpath share no elements. An error is
returned if targpath can\'t be made relative to basepath or if knowing
the current working directory would be necessary to compute it. Rel
calls Clean on the result.

#### [Example]

Code:

```go
paths := []string{
    "/a/b/c",
    "/b/c",
    "./b/c",
}
base := "/a"

fmt.Println("On Unix:")
for _, p := range paths {
    rel, err := filepath.Rel(base, p)
    fmt.Printf("%q: %q %v\n", p, rel, err)
}
```

Output:

```go
On Unix:
"/a/b/c": "b/c" <nil>
"/b/c": "../b/c" <nil>
"./b/c": "" Rel: can't make ./b/c relative to /a
```

func Split 
----------

```go
func Split(path string) (dir, file string)
```

Split splits path immediately following the final Separator, separating
it into a directory and file name component. If there is no Separator in
path, Split returns an empty dir and file set to path. The returned
values have the property that path = dir+file.

#### [Example]

Code:

```go
paths := []string{
    "/home/arnie/amelia.jpg",
    "/mnt/photos/",
    "rabbit.jpg",
    "/usr/local//go",
}
fmt.Println("On Unix:")
for _, p := range paths {
    dir, file := filepath.Split(p)
    fmt.Printf("input: %q\n\tdir: %q\n\tfile: %q\n", p, dir, file)
}
```

Output:

```go
On Unix:
input: "/home/arnie/amelia.jpg"
    dir: "/home/arnie/"
    file: "amelia.jpg"
input: "/mnt/photos/"
    dir: "/mnt/photos/"
    file: ""
input: "rabbit.jpg"
    dir: ""
    file: "rabbit.jpg"
input: "/usr/local//go"
    dir: "/usr/local//"
    file: "go"
```

func SplitList 
--------------

```go
func SplitList(path string) []string
```

SplitList splits a list of paths joined by the OS-specific
ListSeparator, usually found in PATH or GOPATH environment variables.
Unlike strings.Split, SplitList returns an empty slice when passed an
empty string.

#### [Example]

Code:

```go
fmt.Println("On Unix:", filepath.SplitList("/a/b/c:/usr/bin"))
```

Output:

```go
On Unix: [/a/b/c /usr/bin]
```

func ToSlash 
------------

```go
func ToSlash(path string) string
```

ToSlash returns the result of replacing each separator character in path
with a slash (\'/\') character. Multiple separators are replaced by
multiple slashes.

func VolumeName 
---------------

```go
func VolumeName(path string) string
```

VolumeName returns leading volume name. Given \"C:\\foo\\bar\" it
returns \"C:\" on Windows. Given \"\\\\host\\share\\foo\" it returns
\"\\\\host\\share\". On other platforms it returns \"\".

func Walk 
---------

```go
func Walk(root string, fn WalkFunc) error
```

Walk walks the file tree rooted at root, calling fn for each file or
directory in the tree, including root.

All errors that arise visiting files and directories are filtered by fn:
see the WalkFunc documentation for details.

The files are walked in lexical order, which makes the output
deterministic but requires Walk to read an entire directory into memory
before proceeding to walk that directory.

Walk does not follow symbolic links.

Walk is less efficient than WalkDir, introduced in Go 1.16, which avoids
calling os.Lstat on every visited file or directory.

#### [Example]

Code:

```go
package filepath_test

import (
    "fmt"
    "io/fs"
    "os"
    "path/filepath"
)

func prepareTestDirTree(tree string) (string, error) {
    tmpDir, err := os.MkdirTemp("", "")
    if err != nil {
        return "", fmt.Errorf("error creating temp directory: %v\n", err)
    }

    err = os.MkdirAll(filepath.Join(tmpDir, tree), 0755)
    if err != nil {
        os.RemoveAll(tmpDir)
        return "", err
    }

    return tmpDir, nil
}

func ExampleWalk() {
    tmpDir, err := prepareTestDirTree("dir/to/walk/skip")
    if err != nil {
        fmt.Printf("unable to create test dir tree: %v\n", err)
        return
    }
    defer os.RemoveAll(tmpDir)
    os.Chdir(tmpDir)

    subDirToSkip := "skip"

    fmt.Println("On Unix:")
    err = filepath.Walk(".", func(path string, info fs.FileInfo, err error) error {
        if err != nil {
            fmt.Printf("prevent panic by handling failure accessing a path %q: %v\n", path, err)
            return err
        }
        if info.IsDir() && info.Name() == subDirToSkip {
            fmt.Printf("skipping a dir without errors: %+v \n", info.Name())
            return filepath.SkipDir
        }
        fmt.Printf("visited file or dir: %q\n", path)
        return nil
    })
    if err != nil {
        fmt.Printf("error walking the path %q: %v\n", tmpDir, err)
        return
    }
    // Output:
    // On Unix:
    // visited file or dir: "."
    // visited file or dir: "dir"
    // visited file or dir: "dir/to"
    // visited file or dir: "dir/to/walk"
    // skipping a dir without errors: skip
}
```

func WalkDir 
---------------------------------------------

```go
func WalkDir(root string, fn fs.WalkDirFunc) error
```

WalkDir walks the file tree rooted at root, calling fn for each file or
directory in the tree, including root.

All errors that arise visiting files and directories are filtered by fn:
see the fs.WalkDirFunc documentation for details.

The files are walked in lexical order, which makes the output
deterministic but requires WalkDir to read an entire directory into
memory before proceeding to walk that directory.

WalkDir does not follow symbolic links.

WalkDir calls fn with paths that use the separator character appropriate
for the operating system. This is unlike io/fs.WalkDir, which always
uses slash separated paths.

type WalkFunc 
-------------

WalkFunc is the type of the function called by Walk to visit each file
or directory.

The path argument contains the argument to Walk as a prefix. That is, if
Walk is called with root argument \"dir\" and finds a file named \"a\"
in that directory, the walk function will be called with argument
\"dir/a\".

The directory and file are joined with Join, which may clean the
directory name: if Walk is called with the root argument \"x/../dir\"
and finds a file named \"a\" in that directory, the walk function will
be called with argument \"dir/a\", not \"x/../dir/a\".

The info argument is the fs.FileInfo for the named path.

The error result returned by the function controls how Walk continues.
If the function returns the special value SkipDir, Walk skips the
current directory (path if info.IsDir() is true, otherwise path\'s
parent directory). If the function returns the special value SkipAll,
Walk skips all remaining files and directories. Otherwise, if the
function returns a non-nil error, Walk stops entirely and returns that
error.

The err argument reports an error related to path, signaling that Walk
will not walk into that directory. The function can decide how to handle
that error; as described earlier, returning the error will cause Walk to
stop walking the entire tree.

Walk calls the function with a non-nil err argument in two cases.

First, if an os.Lstat on the root directory or any directory or file in
the tree fails, Walk calls the function with path set to that directory
or file\'s path, info set to nil, and err set to the error from
os.Lstat.

Second, if a directory\'s Readdirnames method fails, Walk calls the
function with path set to the directory\'s path, info, set to an
fs.FileInfo describing the directory, and err set to the error from
Readdirnames.

```go
type WalkFunc func(path string, info fs.FileInfo, err error) error
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/path/filepath/>

