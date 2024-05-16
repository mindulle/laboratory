Package path
============

-   `import "path"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)
-   [Subdirectories](#pkg-subdirectories)

Overview 
--------

Package path implements utility routines for manipulating
slash-separated paths.

The path package should only be used for paths separated by forward
slashes, such as the paths in URLs. This package does not deal with
Windows paths with drive letters or backslashes; to manipulate operating
system paths, use the path/filepath package.

Index 
-----

-   [Variables](#pkg-variables)
-   [func Base(path string) string](#Base)
-   [func Clean(path string) string](#Clean)
-   [func Dir(path string) string](#Dir)
-   [func Ext(path string) string](#Ext)
-   [func IsAbs(path string) bool](#IsAbs)
-   [func Join(elem \...string) string](#Join)
-   [func Match(pattern, name string) (matched bool, err error)](#Match)
-   [func Split(path string) (dir, file string)](#Split)

 
### Examples

[Base](#example_Base)

[Clean](#example_Clean)

[Dir](#example_Dir)

[Ext](#example_Ext)

[IsAbs](#example_IsAbs)

[Join](#example_Join)

[Match](#example_Match)

[Split](#example_Split)


### Package files

match.go path.go

Variables 
---------

ErrBadPattern indicates a pattern was malformed.

```go
var ErrBadPattern = errors.New("syntax error in pattern")
```

func Base 
---------

```go
func Base(path string) string
```

Base returns the last element of path. Trailing slashes are removed
before extracting the last element. If the path is empty, Base returns
\".\". If the path consists entirely of slashes, Base returns \"/\".

#### [Example]

Code:

```go
fmt.Println(path.Base("/a/b"))
fmt.Println(path.Base("/"))
fmt.Println(path.Base(""))
```

Output:

```go
b
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

1.  Replace multiple slashes with a single slash.
2.  Eliminate each . path name element (the current directory).
3.  Eliminate each inner .. path name element (the parent directory)
    along with the non-.. element that precedes it.
4.  Eliminate .. elements that begin a rooted path: that is, replace
    \"/..\" by \"/\" at the beginning of a path.

The returned path ends in a slash only if it is the root \"/\".

If the result of this process is an empty string, Clean returns the
string \".\".

See also Rob Pike, "Lexical File Names in Plan 9 or Getting Dot-Dot
Right," https://9p.io/sys/doc/lexnames.html>

#### [Example]

Code:

```go
paths := []string{
    "a/c",
    "a//c",
    "a/c/.",
    "a/c/b/..",
    "/../a/c",
    "/../a/b/../././/c",
    "",
}

for _, p := range paths {
    fmt.Printf("Clean(%q) = %q\n", p, path.Clean(p))
}
```

Output:

```go
Clean("a/c") = "a/c"
Clean("a//c") = "a/c"
Clean("a/c/.") = "a/c"
Clean("a/c/b/..") = "a/c"
Clean("/../a/c") = "/a/c"
Clean("/../a/b/../././/c") = "/a/c"
Clean("") = "."
```

func Dir 
--------

```go
func Dir(path string) string
```

Dir returns all but the last element of path, typically the path\'s
directory. After dropping the final element using Split, the path is
Cleaned and trailing slashes are removed. If the path is empty, Dir
returns \".\". If the path consists entirely of slashes followed by
non-slash bytes, Dir returns a single slash. In any other case, the
returned path does not end in a slash.

#### [Example]

Code:

```go
fmt.Println(path.Dir("/a/b/c"))
fmt.Println(path.Dir("a/b/c"))
fmt.Println(path.Dir("/a/"))
fmt.Println(path.Dir("a/"))
fmt.Println(path.Dir("/"))
fmt.Println(path.Dir(""))
```

Output:

```go
/a/b
a/b
/a
a
/
.
```

func Ext 
--------

```go
func Ext(path string) string
```

Ext returns the file name extension used by path. The extension is the
suffix beginning at the final dot in the final slash-separated element
of path; it is empty if there is no dot.

#### [Example]

Code:

```go
fmt.Println(path.Ext("/a/b/c/bar.css"))
fmt.Println(path.Ext("/"))
fmt.Println(path.Ext(""))
```

Output:

```go
.css
```

func IsAbs 
----------

```go
func IsAbs(path string) bool
```

IsAbs reports whether the path is absolute.

#### [Example]

Code:

```go
fmt.Println(path.IsAbs("/dev/null"))
```

Output:

```go
true
```

func Join 
---------

```go
func Join(elem ...string) string
```

Join joins any number of path elements into a single path, separating
them with slashes. Empty elements are ignored. The result is Cleaned.
However, if the argument list is empty or all its elements are empty,
Join returns an empty string.

#### [Example]

Code:

```go
fmt.Println(path.Join("a", "b", "c"))
fmt.Println(path.Join("a", "b/c"))
fmt.Println(path.Join("a/b", "c"))

fmt.Println(path.Join("a/b", "../../../xyz"))

fmt.Println(path.Join("", ""))
fmt.Println(path.Join("a", ""))
fmt.Println(path.Join("", "a"))
```

Output:

```go
a/b/c
a/b/c
a/b/c
../xyz

a
a
```

func Match 
----------

```go
func Match(pattern, name string) (matched bool, err error)
```

Match reports whether name matches the shell pattern. The pattern syntax
is:

```go
pattern:
    { term }
term:
    '*'         matches any sequence of non-/ characters
    '?'         matches any single non-/ character
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

#### [Example]

Code:

```go
fmt.Println(path.Match("abc", "abc"))
fmt.Println(path.Match("a*", "abc"))
fmt.Println(path.Match("a*/b", "a/c/b"))
```

Output:

```go
true <nil>
true <nil>
false <nil>
```

func Split 
----------

```go
func Split(path string) (dir, file string)
```

Split splits path immediately following the final slash, separating it
into a directory and file name component. If there is no slash in path,
Split returns an empty dir and file set to path. The returned values
have the property that path = dir+file.

#### [Example]

Code:

```go
split := func(s string) {
    dir, file := path.Split(s)
    fmt.Printf("path.Split(%q) = dir: %q, file: %q\n", s, dir, file)
}
split("static/myfile.css")
split("myfile.css")
split("")
```

Output:

```go
path.Split("static/myfile.css") = dir: "static/", file: "myfile.css"
path.Split("myfile.css") = dir: "", file: "myfile.css"
path.Split("") = dir: "", file: ""
```

Subdirectories 
--------------

 
Name


Synopsis

[..](../index)

[filepath](filepath/index)

Package filepath implements utility routines for manipulating filename
paths in a way compatible with the target operating system-defined file
paths.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/path/>

