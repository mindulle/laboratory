Package strings
===============

-   `import "strings"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package strings implements simple functions to manipulate UTF-8 encoded
strings.

For information about UTF-8 strings in Go, see
https://blog.golang.org/strings>.

Index 
-----

-   [func Clone(s string) string](#Clone)
-   [func Compare(a, b string) int](#Compare)
-   [func Contains(s, substr string) bool](#Contains)
-   [func ContainsAny(s, chars string) bool](#ContainsAny)
-   [func ContainsFunc(s string, f func(rune) bool) bool](#ContainsFunc)
-   [func ContainsRune(s string, r rune) bool](#ContainsRune)
-   [func Count(s, substr string) int](#Count)
-   [func Cut(s, sep string) (before, after string, found bool)](#Cut)
-   [func CutPrefix(s, prefix string) (after string, found
    bool)](#CutPrefix)
-   [func CutSuffix(s, suffix string) (before string, found
    bool)](#CutSuffix)
-   [func EqualFold(s, t string) bool](#EqualFold)
-   [func Fields(s string) \[\]string](#Fields)
-   [func FieldsFunc(s string, f func(rune) bool)
    \[\]string](#FieldsFunc)
-   [func HasPrefix(s, prefix string) bool](#HasPrefix)
-   [func HasSuffix(s, suffix string) bool](#HasSuffix)
-   [func Index(s, substr string) int](#Index)
-   [func IndexAny(s, chars string) int](#IndexAny)
-   [func IndexByte(s string, c byte) int](#IndexByte)
-   [func IndexFunc(s string, f func(rune) bool) int](#IndexFunc)
-   [func IndexRune(s string, r rune) int](#IndexRune)
-   [func Join(elems \[\]string, sep string) string](#Join)
-   [func LastIndex(s, substr string) int](#LastIndex)
-   [func LastIndexAny(s, chars string) int](#LastIndexAny)
-   [func LastIndexByte(s string, c byte) int](#LastIndexByte)
-   [func LastIndexFunc(s string, f func(rune) bool)
    int](#LastIndexFunc)
-   [func Map(mapping func(rune) rune, s string) string](#Map)
-   [func Repeat(s string, count int) string](#Repeat)
-   [func Replace(s, old, new string, n int) string](#Replace)
-   [func ReplaceAll(s, old, new string) string](#ReplaceAll)
-   [func Split(s, sep string) \[\]string](#Split)
-   [func SplitAfter(s, sep string) \[\]string](#SplitAfter)
-   [func SplitAfterN(s, sep string, n int) \[\]string](#SplitAfterN)
-   [func SplitN(s, sep string, n int) \[\]string](#SplitN)
-   [func Title(s string) string](#Title)
-   [func ToLower(s string) string](#ToLower)
-   [func ToLowerSpecial(c unicode.SpecialCase, s string)
    string](#ToLowerSpecial)
-   [func ToTitle(s string) string](#ToTitle)
-   [func ToTitleSpecial(c unicode.SpecialCase, s string)
    string](#ToTitleSpecial)
-   [func ToUpper(s string) string](#ToUpper)
-   [func ToUpperSpecial(c unicode.SpecialCase, s string)
    string](#ToUpperSpecial)
-   [func ToValidUTF8(s, replacement string) string](#ToValidUTF8)
-   [func Trim(s, cutset string) string](#Trim)
-   [func TrimFunc(s string, f func(rune) bool) string](#TrimFunc)
-   [func TrimLeft(s, cutset string) string](#TrimLeft)
-   [func TrimLeftFunc(s string, f func(rune) bool)
    string](#TrimLeftFunc)
-   [func TrimPrefix(s, prefix string) string](#TrimPrefix)
-   [func TrimRight(s, cutset string) string](#TrimRight)
-   [func TrimRightFunc(s string, f func(rune) bool)
    string](#TrimRightFunc)
-   [func TrimSpace(s string) string](#TrimSpace)
-   [func TrimSuffix(s, suffix string) string](#TrimSuffix)
-   [type Builder](#Builder)
-   [func (b \*Builder) Cap() int](#Builder.Cap)
-   [func (b \*Builder) Grow(n int)](#Builder.Grow)
-   [func (b \*Builder) Len() int](#Builder.Len)
-   [func (b \*Builder) Reset()](#Builder.Reset)
-   [func (b \*Builder) String() string](#Builder.String)
-   [func (b \*Builder) Write(p \[\]byte) (int, error)](#Builder.Write)
-   [func (b \*Builder) WriteByte(c byte) error](#Builder.WriteByte)
-   [func (b \*Builder) WriteRune(r rune) (int,
    error)](#Builder.WriteRune)
-   [func (b \*Builder) WriteString(s string) (int,
    error)](#Builder.WriteString)
-   [type Reader](#Reader)
-   [func NewReader(s string) \*Reader](#NewReader)
-   [func (r \*Reader) Len() int](#Reader.Len)
-   [func (r \*Reader) Read(b \[\]byte) (n int, err
    error)](#Reader.Read)
-   [func (r \*Reader) ReadAt(b \[\]byte, off int64) (n int, err
    error)](#Reader.ReadAt)
-   [func (r \*Reader) ReadByte() (byte, error)](#Reader.ReadByte)
-   [func (r \*Reader) ReadRune() (ch rune, size int, err
    error)](#Reader.ReadRune)
-   [func (r \*Reader) Reset(s string)](#Reader.Reset)
-   [func (r \*Reader) Seek(offset int64, whence int) (int64,
    error)](#Reader.Seek)
-   [func (r \*Reader) Size() int64](#Reader.Size)
-   [func (r \*Reader) UnreadByte() error](#Reader.UnreadByte)
-   [func (r \*Reader) UnreadRune() error](#Reader.UnreadRune)
-   [func (r \*Reader) WriteTo(w io.Writer) (n int64, err
    error)](#Reader.WriteTo)
-   [type Replacer](#Replacer)
-   [func NewReplacer(oldnew \...string) \*Replacer](#NewReplacer)
-   [func (r \*Replacer) Replace(s string) string](#Replacer.Replace)
-   [func (r \*Replacer) WriteString(w io.Writer, s string) (n int, err
    error)](#Replacer.WriteString)

 
### Examples

[Builder](#example_Builder)

[Clone](#example_Clone)

[Compare](#example_Compare)

[Contains](#example_Contains)

[ContainsAny](#example_ContainsAny)

[ContainsRune](#example_ContainsRune)

[Count](#example_Count)

[Cut](#example_Cut)

[CutPrefix](#example_CutPrefix)

[CutSuffix](#example_CutSuffix)

[EqualFold](#example_EqualFold)

[Fields](#example_Fields)

[FieldsFunc](#example_FieldsFunc)

[HasPrefix](#example_HasPrefix)

[HasSuffix](#example_HasSuffix)

[Index](#example_Index)

[IndexAny](#example_IndexAny)

[IndexByte](#example_IndexByte)

[IndexFunc](#example_IndexFunc)

[IndexRune](#example_IndexRune)

[Join](#example_Join)

[LastIndex](#example_LastIndex)

[LastIndexAny](#example_LastIndexAny)

[LastIndexByte](#example_LastIndexByte)

[LastIndexFunc](#example_LastIndexFunc)

[Map](#example_Map)

[NewReplacer](#example_NewReplacer)

[Repeat](#example_Repeat)

[Replace](#example_Replace)

[ReplaceAll](#example_ReplaceAll)

[Split](#example_Split)

[SplitAfter](#example_SplitAfter)

[SplitAfterN](#example_SplitAfterN)

[SplitN](#example_SplitN)

[Title](#example_Title)

[ToLower](#example_ToLower)

[ToLowerSpecial](#example_ToLowerSpecial)

[ToTitle](#example_ToTitle)

[ToTitleSpecial](#example_ToTitleSpecial)

[ToUpper](#example_ToUpper)

[ToUpperSpecial](#example_ToUpperSpecial)

[ToValidUTF8](#example_ToValidUTF8)

[Trim](#example_Trim)

[TrimFunc](#example_TrimFunc)

[TrimLeft](#example_TrimLeft)

[TrimLeftFunc](#example_TrimLeftFunc)

[TrimPrefix](#example_TrimPrefix)

[TrimRight](#example_TrimRight)

[TrimRightFunc](#example_TrimRightFunc)

[TrimSpace](#example_TrimSpace)

[TrimSuffix](#example_TrimSuffix)


### Package files

builder.go clone.go compare.go reader.go replace.go search.go strings.go

func Clone 
-------------------------------------------

```go
func Clone(s string) string
```

Clone returns a fresh copy of s. It guarantees to make a copy of s into
a new allocation, which can be important when retaining only a small
substring of a much larger string. Using Clone can help such programs
use less memory. Of course, since using Clone makes a copy, overuse of
Clone can make programs use more memory. Clone should typically be used
only rarely, and only when profiling indicates that it is needed. For
strings of length zero the string \"\" will be returned and no
allocation is made.

#### [Example]

Code:

```go
s := "abc"
clone := strings.Clone(s)
fmt.Println(s == clone)
fmt.Println(unsafe.StringData(s) == unsafe.StringData(clone))
```

Output:

```go
true
false
```

func Compare 
-------------------------------------------

```go
func Compare(a, b string) int
```

Compare returns an integer comparing two strings lexicographically. The
result will be 0 if a == b, -1 if a \< b, and +1 if a \> b.

Compare is included only for symmetry with package bytes. It is usually
clearer and always faster to use the built-in string comparison
operators ==, \<, \>, and so on.

#### [Example]

Code:

```go
fmt.Println(strings.Compare("a", "b"))
fmt.Println(strings.Compare("a", "a"))
fmt.Println(strings.Compare("b", "a"))
```

Output:

```go
-1
0
1
```

func Contains 
-------------

```go
func Contains(s, substr string) bool
```

Contains reports whether substr is within s.

#### [Example]

Code:

```go
fmt.Println(strings.Contains("seafood", "foo"))
fmt.Println(strings.Contains("seafood", "bar"))
fmt.Println(strings.Contains("seafood", ""))
fmt.Println(strings.Contains("", ""))
```

Output:

```go
true
false
true
true
```

func ContainsAny 
----------------

```go
func ContainsAny(s, chars string) bool
```

ContainsAny reports whether any Unicode code points in chars are within
s.

#### [Example]

Code:

```go
fmt.Println(strings.ContainsAny("team", "i"))
fmt.Println(strings.ContainsAny("fail", "ui"))
fmt.Println(strings.ContainsAny("ure", "ui"))
fmt.Println(strings.ContainsAny("failure", "ui"))
fmt.Println(strings.ContainsAny("foo", ""))
fmt.Println(strings.ContainsAny("", ""))
```

Output:

```go
false
true
true
true
false
false
```

func ContainsFunc 
--------------------------------------------------

```go
func ContainsFunc(s string, f func(rune) bool) bool
```

ContainsFunc reports whether any Unicode code points r within s satisfy
f(r).

func ContainsRune 
-----------------

```go
func ContainsRune(s string, r rune) bool
```

ContainsRune reports whether the Unicode code point r is within s.

#### [Example]

Code:

```go
// Finds whether a string contains a particular Unicode code point.
// The code point for the lowercase letter "a", for example, is 97.
fmt.Println(strings.ContainsRune("aardvark", 97))
fmt.Println(strings.ContainsRune("timeout", 97))
```

Output:

```go
true
false
```

func Count 
----------

```go
func Count(s, substr string) int
```

Count counts the number of non-overlapping instances of substr in s. If
substr is an empty string, Count returns 1 + the number of Unicode code
points in s.

#### [Example]

Code:

```go
fmt.Println(strings.Count("cheese", "e"))
fmt.Println(strings.Count("five", "")) // before & after each rune
```

Output:

```go
3
5
```

func Cut 
-----------------------------------------

```go
func Cut(s, sep string) (before, after string, found bool)
```

Cut slices s around the first instance of sep, returning the text before
and after sep. The found result reports whether sep appears in s. If sep
does not appear in s, cut returns s, \"\", false.

#### [Example]

Code:

```go
show := func(s, sep string) {
    before, after, found := strings.Cut(s, sep)
    fmt.Printf("Cut(%q, %q) = %q, %q, %v\n", s, sep, before, after, found)
}
show("Gopher", "Go")
show("Gopher", "ph")
show("Gopher", "er")
show("Gopher", "Badger")
```

Output:

```go
Cut("Gopher", "Go") = "", "pher", true
Cut("Gopher", "ph") = "Go", "er", true
Cut("Gopher", "er") = "Goph", "", true
Cut("Gopher", "Badger") = "Gopher", "", false
```

func CutPrefix 
-----------------------------------------------

```go
func CutPrefix(s, prefix string) (after string, found bool)
```

CutPrefix returns s without the provided leading prefix string and
reports whether it found the prefix. If s doesn\'t start with prefix,
CutPrefix returns s, false. If prefix is the empty string, CutPrefix
returns s, true.

#### [Example]

Code:

```go
show := func(s, sep string) {
    after, found := strings.CutPrefix(s, sep)
    fmt.Printf("CutPrefix(%q, %q) = %q, %v\n", s, sep, after, found)
}
show("Gopher", "Go")
show("Gopher", "ph")
```

Output:

```go
CutPrefix("Gopher", "Go") = "pher", true
CutPrefix("Gopher", "ph") = "Gopher", false
```

func CutSuffix 
-----------------------------------------------

```go
func CutSuffix(s, suffix string) (before string, found bool)
```

CutSuffix returns s without the provided ending suffix string and
reports whether it found the suffix. If s doesn\'t end with suffix,
CutSuffix returns s, false. If suffix is the empty string, CutSuffix
returns s, true.

#### [Example]

Code:

```go
show := func(s, sep string) {
    before, found := strings.CutSuffix(s, sep)
    fmt.Printf("CutSuffix(%q, %q) = %q, %v\n", s, sep, before, found)
}
show("Gopher", "Go")
show("Gopher", "er")
```

Output:

```go
CutSuffix("Gopher", "Go") = "Gopher", false
CutSuffix("Gopher", "er") = "Goph", true
```

func EqualFold 
--------------

```go
func EqualFold(s, t string) bool
```

EqualFold reports whether s and t, interpreted as UTF-8 strings, are
equal under simple Unicode case-folding, which is a more general form of
case-insensitivity.

#### [Example]

Code:

```go
fmt.Println(strings.EqualFold("Go", "go"))
fmt.Println(strings.EqualFold("AB", "ab")) // true because comparison uses simple case-folding
fmt.Println(strings.EqualFold("ß", "ss"))  // false because comparison does not use full case-folding
```

Output:

```go
true
true
false
```

func Fields 
-----------

```go
func Fields(s string) []string
```

Fields splits the string s around each instance of one or more
consecutive white space characters, as defined by unicode.IsSpace,
returning a slice of substrings of s or an empty slice if s contains
only white space.

#### [Example]

Code:

```go
fmt.Printf("Fields are: %q", strings.Fields("  foo bar  baz   "))
```

Output:

```go
Fields are: ["foo" "bar" "baz"]
```

func FieldsFunc 
---------------

```go
func FieldsFunc(s string, f func(rune) bool) []string
```

FieldsFunc splits the string s at each run of Unicode code points c
satisfying f(c) and returns an array of slices of s. If all code points
in s satisfy f(c) or the string is empty, an empty slice is returned.

FieldsFunc makes no guarantees about the order in which it calls f(c)
and assumes that f always returns the same value for a given c.

#### [Example]

Code:

```go
f := func(c rune) bool {
    return !unicode.IsLetter(c) && !unicode.IsNumber(c)
}
fmt.Printf("Fields are: %q", strings.FieldsFunc("  foo1;bar2,baz3...", f))
```

Output:

```go
Fields are: ["foo1" "bar2" "baz3"]
```

func HasPrefix 
--------------

```go
func HasPrefix(s, prefix string) bool
```

HasPrefix tests whether the string s begins with prefix.

#### [Example]

Code:

```go
fmt.Println(strings.HasPrefix("Gopher", "Go"))
fmt.Println(strings.HasPrefix("Gopher", "C"))
fmt.Println(strings.HasPrefix("Gopher", ""))
```

Output:

```go
true
false
true
```

func HasSuffix 
--------------

```go
func HasSuffix(s, suffix string) bool
```

HasSuffix tests whether the string s ends with suffix.

#### [Example]

Code:

```go
fmt.Println(strings.HasSuffix("Amigo", "go"))
fmt.Println(strings.HasSuffix("Amigo", "O"))
fmt.Println(strings.HasSuffix("Amigo", "Ami"))
fmt.Println(strings.HasSuffix("Amigo", ""))
```

Output:

```go
true
false
false
true
```

func Index 
----------

```go
func Index(s, substr string) int
```

Index returns the index of the first instance of substr in s, or -1 if
substr is not present in s.

#### [Example]

Code:

```go
fmt.Println(strings.Index("chicken", "ken"))
fmt.Println(strings.Index("chicken", "dmr"))
```

Output:

```go
4
-1
```

func IndexAny 
-------------

```go
func IndexAny(s, chars string) int
```

IndexAny returns the index of the first instance of any Unicode code
point from chars in s, or -1 if no Unicode code point from chars is
present in s.

#### [Example]

Code:

```go
fmt.Println(strings.IndexAny("chicken", "aeiouy"))
fmt.Println(strings.IndexAny("crwth", "aeiouy"))
```

Output:

```go
2
-1
```

func IndexByte 
---------------------------------------------

```go
func IndexByte(s string, c byte) int
```

IndexByte returns the index of the first instance of c in s, or -1 if c
is not present in s.

#### [Example]

Code:

```go
fmt.Println(strings.IndexByte("golang", 'g'))
fmt.Println(strings.IndexByte("gophers", 'h'))
fmt.Println(strings.IndexByte("golang", 'x'))
```

Output:

```go
0
3
-1
```

func IndexFunc 
--------------

```go
func IndexFunc(s string, f func(rune) bool) int
```

IndexFunc returns the index into s of the first Unicode code point
satisfying f(c), or -1 if none do.

#### [Example]

Code:

```go
f := func(c rune) bool {
    return unicode.Is(unicode.Han, c)
}
fmt.Println(strings.IndexFunc("Hello, 世界", f))
fmt.Println(strings.IndexFunc("Hello, world", f))
```

Output:

```go
7
-1
```

func IndexRune 
--------------

```go
func IndexRune(s string, r rune) int
```

IndexRune returns the index of the first instance of the Unicode code
point r, or -1 if rune is not present in s. If r is utf8.RuneError, it
returns the first instance of any invalid UTF-8 byte sequence.

#### [Example]

Code:

```go
fmt.Println(strings.IndexRune("chicken", 'k'))
fmt.Println(strings.IndexRune("chicken", 'd'))
```

Output:

```go
4
-1
```

func Join 
---------

```go
func Join(elems []string, sep string) string
```

Join concatenates the elements of its first argument to create a single
string. The separator string sep is placed between elements in the
resulting string.

#### [Example]

Code:

```go
s := []string{"foo", "bar", "baz"}
fmt.Println(strings.Join(s, ", "))
```

Output:

```go
foo, bar, baz
```

func LastIndex 
--------------

```go
func LastIndex(s, substr string) int
```

LastIndex returns the index of the last instance of substr in s, or -1
if substr is not present in s.

#### [Example]

Code:

```go
fmt.Println(strings.Index("go gopher", "go"))
fmt.Println(strings.LastIndex("go gopher", "go"))
fmt.Println(strings.LastIndex("go gopher", "rodent"))
```

Output:

```go
0
3
-1
```

func LastIndexAny 
-----------------

```go
func LastIndexAny(s, chars string) int
```

LastIndexAny returns the index of the last instance of any Unicode code
point from chars in s, or -1 if no Unicode code point from chars is
present in s.

#### [Example]

Code:

```go
fmt.Println(strings.LastIndexAny("go gopher", "go"))
fmt.Println(strings.LastIndexAny("go gopher", "rodent"))
fmt.Println(strings.LastIndexAny("go gopher", "fail"))
```

Output:

```go
4
8
-1
```

func LastIndexByte 
-------------------------------------------------

```go
func LastIndexByte(s string, c byte) int
```

LastIndexByte returns the index of the last instance of c in s, or -1 if
c is not present in s.

#### [Example]

Code:

```go
fmt.Println(strings.LastIndexByte("Hello, world", 'l'))
fmt.Println(strings.LastIndexByte("Hello, world", 'o'))
fmt.Println(strings.LastIndexByte("Hello, world", 'x'))
```

Output:

```go
10
8
-1
```

func LastIndexFunc 
------------------

```go
func LastIndexFunc(s string, f func(rune) bool) int
```

LastIndexFunc returns the index into s of the last Unicode code point
satisfying f(c), or -1 if none do.

#### [Example]

Code:

```go
fmt.Println(strings.LastIndexFunc("go 123", unicode.IsNumber))
fmt.Println(strings.LastIndexFunc("123 go", unicode.IsNumber))
fmt.Println(strings.LastIndexFunc("go", unicode.IsNumber))
```

Output:

```go
5
2
-1
```

func Map 
--------

```go
func Map(mapping func(rune) rune, s string) string
```

Map returns a copy of the string s with all its characters modified
according to the mapping function. If mapping returns a negative value,
the character is dropped from the string with no replacement.

#### [Example]

Code:

```go
rot13 := func(r rune) rune {
    switch {
    case r >= 'A' && r <= 'Z':
        return 'A' + (r-'A'+13)%26
    case r >= 'a' && r <= 'z':
        return 'a' + (r-'a'+13)%26
    }
    return r
}
fmt.Println(strings.Map(rot13, "'Twas brillig and the slithy gopher..."))
```

Output:

```go
'Gjnf oevyyvt naq gur fyvgul tbcure...
```

func Repeat 
-----------

```go
func Repeat(s string, count int) string
```

Repeat returns a new string consisting of count copies of the string s.

It panics if count is negative or if the result of (len(s) \* count)
overflows.

#### [Example]

Code:

```go
fmt.Println("ba" + strings.Repeat("na", 2))
```

Output:

```go
banana
```

func Replace 
------------

```go
func Replace(s, old, new string, n int) string
```

Replace returns a copy of the string s with the first n non-overlapping
instances of old replaced by new. If old is empty, it matches at the
beginning of the string and after each UTF-8 sequence, yielding up to
k+1 replacements for a k-rune string. If n \< 0, there is no limit on
the number of replacements.

#### [Example]

Code:

```go
fmt.Println(strings.Replace("oink oink oink", "k", "ky", 2))
fmt.Println(strings.Replace("oink oink oink", "oink", "moo", -1))
```

Output:

```go
oinky oinky oink
moo moo moo
```

func ReplaceAll 
------------------------------------------------

```go
func ReplaceAll(s, old, new string) string
```

ReplaceAll returns a copy of the string s with all non-overlapping
instances of old replaced by new. If old is empty, it matches at the
beginning of the string and after each UTF-8 sequence, yielding up to
k+1 replacements for a k-rune string.

#### [Example]

Code:

```go
fmt.Println(strings.ReplaceAll("oink oink oink", "oink", "moo"))
```

Output:

```go
moo moo moo
```

func Split 
----------

```go
func Split(s, sep string) []string
```

Split slices s into all substrings separated by sep and returns a slice
of the substrings between those separators.

If s does not contain sep and sep is not empty, Split returns a slice of
length 1 whose only element is s.

If sep is empty, Split splits after each UTF-8 sequence. If both s and
sep are empty, Split returns an empty slice.

It is equivalent to SplitN with a count of -1.

To split around the first instance of a separator, see Cut.

#### [Example]

Code:

```go
fmt.Printf("%q\n", strings.Split("a,b,c", ","))
fmt.Printf("%q\n", strings.Split("a man a plan a canal panama", "a "))
fmt.Printf("%q\n", strings.Split(" xyz ", ""))
fmt.Printf("%q\n", strings.Split("", "Bernardo O'Higgins"))
```

Output:

```go
["a" "b" "c"]
["" "man " "plan " "canal panama"]
[" " "x" "y" "z" " "]
[""]
```

func SplitAfter 
---------------

```go
func SplitAfter(s, sep string) []string
```

SplitAfter slices s into all substrings after each instance of sep and
returns a slice of those substrings.

If s does not contain sep and sep is not empty, SplitAfter returns a
slice of length 1 whose only element is s.

If sep is empty, SplitAfter splits after each UTF-8 sequence. If both s
and sep are empty, SplitAfter returns an empty slice.

It is equivalent to SplitAfterN with a count of -1.

#### [Example]

Code:

```go
fmt.Printf("%q\n", strings.SplitAfter("a,b,c", ","))
```

Output:

```go
["a," "b," "c"]
```

func SplitAfterN 
----------------

```go
func SplitAfterN(s, sep string, n int) []string
```

SplitAfterN slices s into substrings after each instance of sep and
returns a slice of those substrings.

The count determines the number of substrings to return:

```go
n > 0: at most n substrings; the last substring will be the unsplit remainder.
n == 0: the result is nil (zero substrings)
n < 0: all substrings
```

Edge cases for s and sep (for example, empty strings) are handled as
described in the documentation for SplitAfter.

#### [Example]

Code:

```go
fmt.Printf("%q\n", strings.SplitAfterN("a,b,c", ",", 2))
```

Output:

```go
["a," "b,c"]
```

func SplitN 
-----------

```go
func SplitN(s, sep string, n int) []string
```

SplitN slices s into substrings separated by sep and returns a slice of
the substrings between those separators.

The count determines the number of substrings to return:

```go
n > 0: at most n substrings; the last substring will be the unsplit remainder.
n == 0: the result is nil (zero substrings)
n < 0: all substrings
```

Edge cases for s and sep (for example, empty strings) are handled as
described in the documentation for Split.

To split around the first instance of a separator, see Cut.

#### [Example]

Code:

```go
fmt.Printf("%q\n", strings.SplitN("a,b,c", ",", 2))
z := strings.SplitN("a,b,c", ",", 0)
fmt.Printf("%q (nil = %v)\n", z, z == nil)
```

Output:

```go
["a" "b,c"]
[] (nil = true)
```

func Title 
----------

```go
func Title(s string) string
```

Title returns a copy of the string s with all Unicode letters that begin
words mapped to their Unicode title case.

Deprecated: The rule Title uses for word boundaries does not handle
Unicode punctuation properly. Use golang.org/x/text/cases instead.

#### [Example]

Code:

```go
// Compare this example to the ToTitle example.
fmt.Println(strings.Title("her royal highness"))
fmt.Println(strings.Title("loud noises"))
fmt.Println(strings.Title("хлеб"))
```

Output:

```go
Her Royal Highness
Loud Noises
Хлеб
```

func ToLower 
------------

```go
func ToLower(s string) string
```

ToLower returns s with all Unicode letters mapped to their lower case.

#### [Example]

Code:

```go
fmt.Println(strings.ToLower("Gopher"))
```

Output:

```go
gopher
```

func ToLowerSpecial 
-------------------

```go
func ToLowerSpecial(c unicode.SpecialCase, s string) string
```

ToLowerSpecial returns a copy of the string s with all Unicode letters
mapped to their lower case using the case mapping specified by c.

#### [Example]

Code:

```go
fmt.Println(strings.ToLowerSpecial(unicode.TurkishCase, "Önnek İş"))
```

Output:

```go
önnek iş
```

func ToTitle 
------------

```go
func ToTitle(s string) string
```

ToTitle returns a copy of the string s with all Unicode letters mapped
to their Unicode title case.

#### [Example]

Code:

```go
// Compare this example to the Title example.
fmt.Println(strings.ToTitle("her royal highness"))
fmt.Println(strings.ToTitle("loud noises"))
fmt.Println(strings.ToTitle("хлеб"))
```

Output:

```go
HER ROYAL HIGHNESS
LOUD NOISES
ХЛЕБ
```

func ToTitleSpecial 
-------------------

```go
func ToTitleSpecial(c unicode.SpecialCase, s string) string
```

ToTitleSpecial returns a copy of the string s with all Unicode letters
mapped to their Unicode title case, giving priority to the special
casing rules.

#### [Example]

Code:

```go
fmt.Println(strings.ToTitleSpecial(unicode.TurkishCase, "dünyanın ilk borsa yapısı Aizonai kabul edilir"))
```

Output:

```go
DÜNYANIN İLK BORSA YAPISI AİZONAİ KABUL EDİLİR
```

func ToUpper 
------------

```go
func ToUpper(s string) string
```

ToUpper returns s with all Unicode letters mapped to their upper case.

#### [Example]

Code:

```go
fmt.Println(strings.ToUpper("Gopher"))
```

Output:

```go
GOPHER
```

func ToUpperSpecial 
-------------------

```go
func ToUpperSpecial(c unicode.SpecialCase, s string) string
```

ToUpperSpecial returns a copy of the string s with all Unicode letters
mapped to their upper case using the case mapping specified by c.

#### [Example]

Code:

```go
fmt.Println(strings.ToUpperSpecial(unicode.TurkishCase, "örnek iş"))
```

Output:

```go
ÖRNEK İŞ
```

func ToValidUTF8 
-------------------------------------------------

```go
func ToValidUTF8(s, replacement string) string
```

ToValidUTF8 returns a copy of the string s with each run of invalid
UTF-8 byte sequences replaced by the replacement string, which may be
empty.

#### [Example]

Code:

```go
fmt.Printf("%s\n", strings.ToValidUTF8("abc", "\uFFFD"))
fmt.Printf("%s\n", strings.ToValidUTF8("a\xffb\xC0\xAFc\xff", ""))
fmt.Printf("%s\n", strings.ToValidUTF8("\xed\xa0\x80", "abc"))
```

Output:

```go
abc
abc
abc
```

func Trim 
---------

```go
func Trim(s, cutset string) string
```

Trim returns a slice of the string s with all leading and trailing
Unicode code points contained in cutset removed.

#### [Example]

Code:

```go
fmt.Print(strings.Trim("¡¡¡Hello, Gophers!!!", "!¡"))
```

Output:

```go
Hello, Gophers
```

func TrimFunc 
-------------

```go
func TrimFunc(s string, f func(rune) bool) string
```

TrimFunc returns a slice of the string s with all leading and trailing
Unicode code points c satisfying f(c) removed.

#### [Example]

Code:

```go
fmt.Print(strings.TrimFunc("¡¡¡Hello, Gophers!!!", func(r rune) bool {
    return !unicode.IsLetter(r) && !unicode.IsNumber(r)
}))
```

Output:

```go
Hello, Gophers
```

func TrimLeft 
-------------

```go
func TrimLeft(s, cutset string) string
```

TrimLeft returns a slice of the string s with all leading Unicode code
points contained in cutset removed.

To remove a prefix, use TrimPrefix instead.

#### [Example]

Code:

```go
fmt.Print(strings.TrimLeft("¡¡¡Hello, Gophers!!!", "!¡"))
```

Output:

```go
Hello, Gophers!!!
```

func TrimLeftFunc 
-----------------

```go
func TrimLeftFunc(s string, f func(rune) bool) string
```

TrimLeftFunc returns a slice of the string s with all leading Unicode
code points c satisfying f(c) removed.

#### [Example]

Code:

```go
fmt.Print(strings.TrimLeftFunc("¡¡¡Hello, Gophers!!!", func(r rune) bool {
    return !unicode.IsLetter(r) && !unicode.IsNumber(r)
}))
```

Output:

```go
Hello, Gophers!!!
```

func TrimPrefix 
----------------------------------------------

```go
func TrimPrefix(s, prefix string) string
```

TrimPrefix returns s without the provided leading prefix string. If s
doesn\'t start with prefix, s is returned unchanged.

#### [Example]

Code:

```go
var s = "¡¡¡Hello, Gophers!!!"
s = strings.TrimPrefix(s, "¡¡¡Hello, ")
s = strings.TrimPrefix(s, "¡¡¡Howdy, ")
fmt.Print(s)
```

Output:

```go
Gophers!!!
```

func TrimRight 
--------------

```go
func TrimRight(s, cutset string) string
```

TrimRight returns a slice of the string s, with all trailing Unicode
code points contained in cutset removed.

To remove a suffix, use TrimSuffix instead.

#### [Example]

Code:

```go
fmt.Print(strings.TrimRight("¡¡¡Hello, Gophers!!!", "!¡"))
```

Output:

```go
¡¡¡Hello, Gophers
```

func TrimRightFunc 
------------------

```go
func TrimRightFunc(s string, f func(rune) bool) string
```

TrimRightFunc returns a slice of the string s with all trailing Unicode
code points c satisfying f(c) removed.

#### [Example]

Code:

```go
fmt.Print(strings.TrimRightFunc("¡¡¡Hello, Gophers!!!", func(r rune) bool {
    return !unicode.IsLetter(r) && !unicode.IsNumber(r)
}))
```

Output:

```go
¡¡¡Hello, Gophers
```

func TrimSpace 
--------------

```go
func TrimSpace(s string) string
```

TrimSpace returns a slice of the string s, with all leading and trailing
white space removed, as defined by Unicode.

#### [Example]

Code:

```go
fmt.Println(strings.TrimSpace(" \t\n Hello, Gophers \n\t\r\n"))
```

Output:

```go
Hello, Gophers
```

func TrimSuffix 
----------------------------------------------

```go
func TrimSuffix(s, suffix string) string
```

TrimSuffix returns s without the provided trailing suffix string. If s
doesn\'t end with suffix, s is returned unchanged.

#### [Example]

Code:

```go
var s = "¡¡¡Hello, Gophers!!!"
s = strings.TrimSuffix(s, ", Gophers!!!")
s = strings.TrimSuffix(s, ", Marmots!!!")
fmt.Print(s)
```

Output:

```go
¡¡¡Hello
```

type Builder 
---------------------------------------------

A Builder is used to efficiently build a string using Write methods. It
minimizes memory copying. The zero value is ready to use. Do not copy a
non-zero Builder.

```go
type Builder struct {
    // contains filtered or unexported fields
}
```

#### [Example]

Code:

```go
var b strings.Builder
for i := 3; i >= 1; i-- {
    fmt.Fprintf(&b, "%d...", i)
}
b.WriteString("ignition")
fmt.Println(b.String())
```

Output:

```go
3...2...1...ignition
```

### func (\*Builder) Cap 

```go
func (b *Builder) Cap() int
```

Cap returns the capacity of the builder\'s underlying byte slice. It is
the total space allocated for the string being built and includes any
bytes already written.

### func (\*Builder) Grow 

```go
func (b *Builder) Grow(n int)
```

Grow grows b\'s capacity, if necessary, to guarantee space for another n
bytes. After Grow(n), at least n bytes can be written to b without
another allocation. If n is negative, Grow panics.

### func (\*Builder) Len 

```go
func (b *Builder) Len() int
```

Len returns the number of accumulated bytes; b.Len() == len(b.String()).

### func (\*Builder) Reset 

```go
func (b *Builder) Reset()
```

Reset resets the Builder to be empty.

### func (\*Builder) String 

```go
func (b *Builder) String() string
```

String returns the accumulated string.

### func (\*Builder) Write 

```go
func (b *Builder) Write(p []byte) (int, error)
```

Write appends the contents of p to b\'s buffer. Write always returns
len(p), nil.

### func (\*Builder) WriteByte 

```go
func (b *Builder) WriteByte(c byte) error
```

WriteByte appends the byte c to b\'s buffer. The returned error is
always nil.

### func (\*Builder) WriteRune 

```go
func (b *Builder) WriteRune(r rune) (int, error)
```

WriteRune appends the UTF-8 encoding of Unicode code point r to b\'s
buffer. It returns the length of r and a nil error.

### func (\*Builder) WriteString 

```go
func (b *Builder) WriteString(s string) (int, error)
```

WriteString appends the contents of s to b\'s buffer. It returns the
length of s and a nil error.

type Reader 
-----------

A Reader implements the io.Reader, io.ReaderAt, io.ByteReader,
io.ByteScanner, io.RuneReader, io.RuneScanner, io.Seeker, and
io.WriterTo interfaces by reading from a string. The zero value for
Reader operates like a Reader of an empty string.

```go
type Reader struct {
    // contains filtered or unexported fields
}
```

### func NewReader 

```go
func NewReader(s string) *Reader
```

NewReader returns a new Reader reading from s. It is similar to
bytes.NewBufferString but more efficient and non-writable.

### func (\*Reader) Len 

```go
func (r *Reader) Len() int
```

Len returns the number of bytes of the unread portion of the string.

### func (\*Reader) Read 

```go
func (r *Reader) Read(b []byte) (n int, err error)
```

Read implements the io.Reader interface.

### func (\*Reader) ReadAt 

```go
func (r *Reader) ReadAt(b []byte, off int64) (n int, err error)
```

ReadAt implements the io.ReaderAt interface.

### func (\*Reader) ReadByte 

```go
func (r *Reader) ReadByte() (byte, error)
```

ReadByte implements the io.ByteReader interface.

### func (\*Reader) ReadRune 

```go
func (r *Reader) ReadRune() (ch rune, size int, err error)
```

ReadRune implements the io.RuneReader interface.

### func (\*Reader) Reset 

```go
func (r *Reader) Reset(s string)
```

Reset resets the Reader to be reading from s.

### func (\*Reader) Seek 

```go
func (r *Reader) Seek(offset int64, whence int) (int64, error)
```

Seek implements the io.Seeker interface.

### func (\*Reader) Size 

```go
func (r *Reader) Size() int64
```

Size returns the original length of the underlying string. Size is the
number of bytes available for reading via ReadAt. The returned value is
always the same and is not affected by calls to any other method.

### func (\*Reader) UnreadByte 

```go
func (r *Reader) UnreadByte() error
```

UnreadByte implements the io.ByteScanner interface.

### func (\*Reader) UnreadRune 

```go
func (r *Reader) UnreadRune() error
```

UnreadRune implements the io.RuneScanner interface.

### func (\*Reader) WriteTo 

```go
func (r *Reader) WriteTo(w io.Writer) (n int64, err error)
```

WriteTo implements the io.WriterTo interface.

type Replacer 
-------------

Replacer replaces a list of strings with replacements. It is safe for
concurrent use by multiple goroutines.

```go
type Replacer struct {
    // contains filtered or unexported fields
}
```

### func NewReplacer 

```go
func NewReplacer(oldnew ...string) *Replacer
```

NewReplacer returns a new Replacer from a list of old, new string pairs.
Replacements are performed in the order they appear in the target
string, without overlapping matches. The old string comparisons are done
in argument order.

NewReplacer panics if given an odd number of arguments.

#### [Example]

Code:

```go
r := strings.NewReplacer("<", "&lt;", ">", "&gt;")
fmt.Println(r.Replace("This is <b>HTML</b>!"))
```

Output:

```go
This is &lt;b&gt;HTML&lt;/b&gt;!
```

### func (\*Replacer) Replace 

```go
func (r *Replacer) Replace(s string) string
```

Replace returns a copy of s with all replacements performed.

### func (\*Replacer) WriteString 

```go
func (r *Replacer) WriteString(w io.Writer, s string) (n int, err error)
```

WriteString writes s to w with all replacements performed.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/strings/>

