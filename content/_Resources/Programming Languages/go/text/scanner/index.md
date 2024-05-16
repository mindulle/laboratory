Package scanner
===============

-   `import "text/scanner"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package scanner provides a scanner and tokenizer for UTF-8-encoded text.
It takes an io.Reader providing the source, which then can be tokenized
through repeated calls to the Scan function. For compatibility with
existing tools, the NUL character is not allowed. If the first character
in the source is a UTF-8 encoded byte order mark (BOM), it is discarded.

By default, a Scanner skips white space and Go comments and recognizes
all literals as defined by the Go language specification. It may be
customized to recognize only a subset of those literals and to recognize
different identifier and white space characters.

#### [Example]

Code:

```go
const src = `
// This is scanned code.
if a > 10 {
    someParsable = text
}`

var s scanner.Scanner
s.Init(strings.NewReader(src))
s.Filename = "example"
for tok := s.Scan(); tok != scanner.EOF; tok = s.Scan() {
    fmt.Printf("%s: %s\n", s.Position, s.TokenText())
}
```

Output:

```go
example:3:1: if
example:3:4: a
example:3:6: >
example:3:8: 10
example:3:11: {
example:4:2: someParsable
example:4:15: =
example:4:17: text
example:5:1: }
```

#### [Example (IsIdentRune)]

Code:

```go
const src = "%var1 var2%"

var s scanner.Scanner
s.Init(strings.NewReader(src))
s.Filename = "default"

for tok := s.Scan(); tok != scanner.EOF; tok = s.Scan() {
    fmt.Printf("%s: %s\n", s.Position, s.TokenText())
}

fmt.Println()
s.Init(strings.NewReader(src))
s.Filename = "percent"

// treat leading '%' as part of an identifier
s.IsIdentRune = func(ch rune, i int) bool {
    return ch == '%' && i == 0 || unicode.IsLetter(ch) || unicode.IsDigit(ch) && i > 0
}

for tok := s.Scan(); tok != scanner.EOF; tok = s.Scan() {
    fmt.Printf("%s: %s\n", s.Position, s.TokenText())
}
```

Output:

```go
default:1:1: %
default:1:2: var1
default:1:7: var2
default:1:11: %

percent:1:1: %var1
percent:1:7: var2
percent:1:11: %
```

#### [Example (Mode)]

Code:

```go
const src = `
    // Comment begins at column 5.

This line should not be included in the output.

/*
This multiline comment
should be extracted in
its entirety.
*/
`

var s scanner.Scanner
s.Init(strings.NewReader(src))
s.Filename = "comments"
s.Mode ^= scanner.SkipComments // don't skip comments

for tok := s.Scan(); tok != scanner.EOF; tok = s.Scan() {
    txt := s.TokenText()
    if strings.HasPrefix(txt, "//") || strings.HasPrefix(txt, "/*") {
        fmt.Printf("%s: %s\n", s.Position, txt)
    }
}
```

Output:

```go
comments:2:5: // Comment begins at column 5.
comments:6:1: /*
This multiline comment
should be extracted in
its entirety.
*/
```

#### [Example (Whitespace)]

Code:

```go
// tab-separated values
const src = `aa ab  ac  ad
ba  bb  bc  bd
ca  cb  cc  cd
da  db  dc  dd`

var (
    col, row int
    s        scanner.Scanner
    tsv      [4][4]string // large enough for example above
)
s.Init(strings.NewReader(src))
s.Whitespace ^= 1<<'\t' | 1<<'\n' // don't skip tabs and new lines

for tok := s.Scan(); tok != scanner.EOF; tok = s.Scan() {
    switch tok {
    case '\n':
        row++
        col = 0
    case '\t':
        col++
    default:
        tsv[row][col] = s.TokenText()
    }
}

fmt.Print(tsv)
```

Output:

```go
[[aa ab ac ad] [ba bb bc bd] [ca cb cc cd] [da db dc dd]]
```

Index 
-----

-   [Constants](#pkg-constants)
-   [func TokenString(tok rune) string](#TokenString)
-   [type Position](#Position)
-   [func (pos \*Position) IsValid() bool](#Position.IsValid)
-   [func (pos Position) String() string](#Position.String)
-   [type Scanner](#Scanner)
-   [func (s \*Scanner) Init(src io.Reader) \*Scanner](#Scanner.Init)
-   [func (s \*Scanner) Next() rune](#Scanner.Next)
-   [func (s \*Scanner) Peek() rune](#Scanner.Peek)
-   [func (s \*Scanner) Pos() (pos Position)](#Scanner.Pos)
-   [func (s \*Scanner) Scan() rune](#Scanner.Scan)
-   [func (s \*Scanner) TokenText() string](#Scanner.TokenText)

 
### Examples

[Package](#example_)

[Package (IsIdentRune)](#example__isIdentRune)

[Package (Mode)](#example__mode)

[Package (Whitespace)](#example__whitespace)


### Package files

scanner.go

Constants 
---------

Predefined mode bits to control recognition of tokens. For instance, to
configure a Scanner such that it only recognizes (Go) identifiers,
integers, and skips comments, set the Scanner\'s Mode field to:

```go
ScanIdents | ScanInts | SkipComments
```

With the exceptions of comments, which are skipped if SkipComments is
set, unrecognized tokens are not ignored. Instead, the scanner simply
returns the respective individual characters (or possibly sub-tokens).
For instance, if the mode is ScanIdents (not ScanStrings), the string
\"foo\" is scanned as the token sequence \'\"\' Ident \'\"\'.

Use GoTokens to configure the Scanner such that it accepts all Go
literal tokens including Go identifiers. Comments will be skipped.

```go
const (
    ScanIdents     = 1 << -Ident
    ScanInts       = 1 << -Int
    ScanFloats     = 1 << -Float // includes Ints and hexadecimal floats
    ScanChars      = 1 << -Char
    ScanStrings    = 1 << -String
    ScanRawStrings = 1 << -RawString
    ScanComments   = 1 << -Comment
    SkipComments   = 1 << -skipComment // if set with ScanComments, comments become white space
    GoTokens       = ScanIdents | ScanFloats | ScanChars | ScanStrings | ScanRawStrings | ScanComments | SkipComments
)
```

The result of Scan is one of these tokens or a Unicode character.

```go
const (
    EOF = -(iota + 1)
    Ident
    Int
    Float
    Char
    String
    RawString
    Comment
)
```

GoWhitespace is the default value for the Scanner\'s Whitespace field.
Its value selects Go\'s white space characters.

```go
const GoWhitespace = 1<<'\t' | 1<<'\n' | 1<<'\r' | 1<<' '
```

func TokenString 
----------------

```go
func TokenString(tok rune) string
```

TokenString returns a printable string for a token or Unicode character.

type Position 
-------------

Position is a value that represents a source position. A position is
valid if Line \> 0.

```go
type Position struct {
    Filename string // filename, if any
    Offset   int    // byte offset, starting at 0
    Line     int    // line number, starting at 1
    Column   int    // column number, starting at 1 (character count per line)
}
```

### func (\*Position) IsValid 

```go
func (pos *Position) IsValid() bool
```

IsValid reports whether the position is valid.

### func (Position) String 

```go
func (pos Position) String() string
```

type Scanner 
------------

A Scanner implements reading of Unicode characters and tokens from an
io.Reader.

```go
type Scanner struct {

    // Error is called for each error encountered. If no Error
    // function is set, the error is reported to os.Stderr.
    Error func(s *Scanner, msg string)

    // ErrorCount is incremented by one for each error encountered.
    ErrorCount int

    // The Mode field controls which tokens are recognized. For instance,
    // to recognize Ints, set the ScanInts bit in Mode. The field may be
    // changed at any time.
    Mode uint

    // The Whitespace field controls which characters are recognized
    // as white space. To recognize a character ch <= ' ' as white space,
    // set the ch'th bit in Whitespace (the Scanner's behavior is undefined
    // for values ch > ' '). The field may be changed at any time.
    Whitespace uint64

    // IsIdentRune is a predicate controlling the characters accepted
    // as the ith rune in an identifier. The set of valid characters
    // must not intersect with the set of white space characters.
    // If no IsIdentRune function is set, regular Go identifiers are
    // accepted instead. The field may be changed at any time.
    IsIdentRune func(ch rune, i int) bool // Go 1.4

    // Start position of most recently scanned token; set by Scan.
    // Calling Init or Next invalidates the position (Line == 0).
    // The Filename field is always left untouched by the Scanner.
    // If an error is reported (via Error) and Position is invalid,
    // the scanner is not inside a token. Call Pos to obtain an error
    // position in that case, or to obtain the position immediately
    // after the most recently scanned token.
    Position
    // contains filtered or unexported fields
}
```

### func (\*Scanner) Init 

```go
func (s *Scanner) Init(src io.Reader) *Scanner
```

Init initializes a Scanner with a new source and returns s. Error is set
to nil, ErrorCount is set to 0, Mode is set to GoTokens, and Whitespace
is set to GoWhitespace.

### func (\*Scanner) Next 

```go
func (s *Scanner) Next() rune
```

Next reads and returns the next Unicode character. It returns EOF at the
end of the source. It reports a read error by calling s.Error, if not
nil; otherwise it prints an error message to os.Stderr. Next does not
update the Scanner\'s Position field; use Pos() to get the current
position.

### func (\*Scanner) Peek 

```go
func (s *Scanner) Peek() rune
```

Peek returns the next Unicode character in the source without advancing
the scanner. It returns EOF if the scanner\'s position is at the last
character of the source.

### func (\*Scanner) Pos 

```go
func (s *Scanner) Pos() (pos Position)
```

Pos returns the position of the character immediately after the
character or token returned by the last call to Next or Scan. Use the
Scanner\'s Position field for the start position of the most recently
scanned token.

### func (\*Scanner) Scan 

```go
func (s *Scanner) Scan() rune
```

Scan reads the next token or Unicode character from source and returns
it. It only recognizes tokens t for which the respective Mode bit
(1\<\<-t) is set. It returns EOF at the end of the source. It reports
scanner errors (read and token errors) by calling s.Error, if not nil;
otherwise it prints an error message to os.Stderr.

### func (\*Scanner) TokenText 

```go
func (s *Scanner) TokenText() string
```

TokenText returns the string corresponding to the most recently scanned
token. Valid after calling Scan and in calls of Scanner.Error.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/text/scanner/>

