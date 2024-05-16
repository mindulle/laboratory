Package fmt
===========

-   `import "fmt"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package fmt implements formatted I/O with functions analogous to C\'s
printf and scanf. The format \'verbs\' are derived from C\'s but are
simpler.

### Printing 

The verbs:

General:

```go
%v  the value in a default format
    when printing structs, the plus flag (%+v) adds field names
%#v a Go-syntax representation of the value
%T  a Go-syntax representation of the type of the value
%%  a literal percent sign; consumes no value
```

Boolean:

```go
%t  the word true or false
```

Integer:

```go
%b  base 2
%c  the character represented by the corresponding Unicode code point
%d  base 10
%o  base 8
%O  base 8 with 0o prefix
%q  a single-quoted character literal safely escaped with Go syntax.
%x  base 16, with lower-case letters for a-f
%X  base 16, with upper-case letters for A-F
%U  Unicode format: U+1234; same as "U+%04X"
```

Floating-point and complex constituents:

```go
%b  decimalless scientific notation with exponent a power of two,
    in the manner of strconv.FormatFloat with the 'b' format,
    e.g. -123456p-78
%e  scientific notation, e.g. -1.234456e+78
%E  scientific notation, e.g. -1.234456E+78
%f  decimal point but no exponent, e.g. 123.456
%F  synonym for %f
%g  %e for large exponents, %f otherwise. Precision is discussed below.
%G  %E for large exponents, %F otherwise
%x  hexadecimal notation (with decimal power of two exponent), e.g. -0x1.23abcp+20
%X  upper-case hexadecimal notation, e.g. -0X1.23ABCP+20
```

String and slice of bytes (treated equivalently with these verbs):

```go
%s  the uninterpreted bytes of the string or slice
%q  a double-quoted string safely escaped with Go syntax
%x  base 16, lower-case, two characters per byte
%X  base 16, upper-case, two characters per byte
```

Slice:

```go
%p  address of 0th element in base 16 notation, with leading 0x
```

Pointer:

```go
%p  base 16 notation, with leading 0x
The %b, %d, %o, %x and %X verbs also work with pointers,
formatting the value exactly as if it were an integer.
```

The default format for %v is:

```go
bool:                    %t
int, int8 etc.:          %d
uint, uint8 etc.:        %d, %#x if printed with %#v
float32, complex64, etc: %g
string:                  %s
chan:                    %p
pointer:                 %p
```

For compound objects, the elements are printed using these rules,
recursively, laid out like this:

```go
struct:             {field0 field1 ...}
array, slice:       [elem0 elem1 ...]
maps:               map[key1:value1 key2:value2 ...]
pointer to above:   &{}, &[], &map[]
```

Width is specified by an optional decimal number immediately preceding
the verb. If absent, the width is whatever is necessary to represent the
value. Precision is specified after the (optional) width by a period
followed by a decimal number. If no period is present, a default
precision is used. A period with no following number specifies a
precision of zero. Examples:

```go
%f     default width, default precision
%9f    width 9, default precision
%.2f   default width, precision 2
%9.2f  width 9, precision 2
%9.f   width 9, precision 0
```

Width and precision are measured in units of Unicode code points, that
is, runes. (This differs from C\'s printf where the units are always
measured in bytes.) Either or both of the flags may be replaced with the
character \'\*\', causing their values to be obtained from the next
operand (preceding the one to format), which must be of type int.

For most values, width is the minimum number of runes to output, padding
the formatted form with spaces if necessary.

For strings, byte slices and byte arrays, however, precision limits the
length of the input to be formatted (not the size of the output),
truncating if necessary. Normally it is measured in runes, but for these
types when formatted with the %x or %X format it is measured in bytes.

For floating-point values, width sets the minimum width of the field and
precision sets the number of places after the decimal, if appropriate,
except that for %g/%G precision sets the maximum number of significant
digits (trailing zeros are removed). For example, given 12.345 the
format %6.3f prints 12.345 while %.3g prints 12.3. The default precision
for %e, %f and %\#g is 6; for %g it is the smallest number of digits
necessary to identify the value uniquely.

For complex numbers, the width and precision apply to the two components
independently and the result is parenthesized, so %f applied to 1.2+3.4i
produces (1.200000+3.400000i).

When formatting a single integer code point or a rune string (type
\[\]rune) with %q, invalid Unicode code points are changed to the
Unicode replacement character, U+FFFD, as in strconv.QuoteRune.

Other flags:

```go
'+' always print a sign for numeric values;
    guarantee ASCII-only output for %q (%+q)
'-' pad with spaces on the right rather than the left (left-justify the field)
'#' alternate format: add leading 0b for binary (%#b), 0 for octal (%#o),
    0x or 0X for hex (%#x or %#X); suppress 0x for %p (%#p);
    for %q, print a raw (backquoted) string if strconv.CanBackquote
    returns true;
    always print a decimal point for %e, %E, %f, %F, %g and %G;
    do not remove trailing zeros for %g and %G;
    write e.g. U+0078 'x' if the character is printable for %U (%#U).
' ' (space) leave a space for elided sign in numbers (% d);
    put spaces between bytes printing strings or slices in hex (% x, % X)
'0' pad with leading zeros rather than spaces;
    for numbers, this moves the padding after the sign;
    ignored for strings, byte slices and byte arrays
```

Flags are ignored by verbs that do not expect them. For example there is
no alternate decimal format, so %\#d and %d behave identically.

For each Printf-like function, there is also a Print function that takes
no format and is equivalent to saying %v for every operand. Another
variant Println inserts blanks between operands and appends a newline.

Regardless of the verb, if an operand is an interface value, the
internal concrete value is used, not the interface itself. Thus:

```go
var i interface{} = 23
fmt.Printf("%v\n", i)
```

will print 23.

Except when printed using the verbs %T and %p, special formatting
considerations apply for operands that implement certain interfaces. In
order of application:

1\. If the operand is a reflect.Value, the operand is replaced by the
concrete value that it holds, and printing continues with the next rule.

2\. If an operand implements the Formatter interface, it will be
invoked. In this case the interpretation of verbs and flags is
controlled by that implementation.

3\. If the %v verb is used with the \# flag (%\#v) and the operand
implements the GoStringer interface, that will be invoked.

If the format (which is implicitly %v for Println etc.) is valid for a
string (%s %q %v %x %X), the following two rules apply:

4\. If an operand implements the error interface, the Error method will
be invoked to convert the object to a string, which will then be
formatted as required by the verb (if any).

5\. If an operand implements method String() string, that method will be
invoked to convert the object to a string, which will then be formatted
as required by the verb (if any).

For compound operands such as slices and structs, the format applies to
the elements of each operand, recursively, not to the operand as a
whole. Thus %q will quote each element of a slice of strings, and %6.2f
will control formatting for each element of a floating-point array.

However, when printing a byte slice with a string-like verb (%s %q %x
%X), it is treated identically to a string, as a single item.

To avoid recursion in cases such as

```go
type X string
func (x X) String() string { return Sprintf("<%s>", x) }
```

convert the value before recurring:

```go
func (x X) String() string { return Sprintf("<%s>", string(x)) }
```

Infinite recursion can also be triggered by self-referential data
structures, such as a slice that contains itself as an element, if that
type has a String method. Such pathologies are rare, however, and the
package does not protect against them.

When printing a struct, fmt cannot and therefore does not invoke
formatting methods such as Error or String on unexported fields.

### Explicit argument indexes 

In Printf, Sprintf, and Fprintf, the default behavior is for each
formatting verb to format successive arguments passed in the call.
However, the notation \[n\] immediately before the verb indicates that
the nth one-indexed argument is to be formatted instead. The same
notation before a \'\*\' for a width or precision selects the argument
index holding the value. After processing a bracketed expression \[n\],
subsequent verbs will use arguments n+1, n+2, etc. unless otherwise
directed.

For example,

```go
fmt.Sprintf("%[2]d %[1]d\n", 11, 22)
```

will yield \"22 11\", while

```go
fmt.Sprintf("%[3]*.[2]*[1]f", 12.0, 2, 6)
```

equivalent to

```go
fmt.Sprintf("%6.2f", 12.0)
```

will yield \" 12.00\". Because an explicit index affects subsequent
verbs, this notation can be used to print the same values multiple times
by resetting the index for the first argument to be repeated:

```go
fmt.Sprintf("%d %d %#[1]x %#x", 16, 17)
```

will yield \"16 17 0x10 0x11\".

### Format errors 

If an invalid argument is given for a verb, such as providing a string
to %d, the generated string will contain a description of the problem,
as in these examples:

```go
Wrong type or unknown verb: %!verb(type=value)
    Printf("%d", "hi"):        %!d(string=hi)
Too many arguments: %!(EXTRA type=value)
    Printf("hi", "guys"):      hi%!(EXTRA string=guys)
Too few arguments: %!verb(MISSING)
    Printf("hi%d"):            hi%!d(MISSING)
Non-int for width or precision: %!(BADWIDTH) or %!(BADPREC)
    Printf("%*s", 4.5, "hi"):  %!(BADWIDTH)hi
    Printf("%.*s", 4.5, "hi"): %!(BADPREC)hi
Invalid or invalid use of argument index: %!(BADINDEX)
    Printf("%*[2]d", 7):       %!d(BADINDEX)
    Printf("%.[2]d", 7):       %!d(BADINDEX)
```

All errors begin with the string \"%!\" followed sometimes by a single
character (the verb) and end with a parenthesized description.

If an Error or String method triggers a panic when called by a print
routine, the fmt package reformats the error message from the panic,
decorating it with an indication that it came through the fmt package.
For example, if a String method calls panic(\"bad\"), the resulting
formatted message will look like

```go
%!s(PANIC=bad)
```

The %!s just shows the print verb in use when the failure occurred. If
the panic is caused by a nil receiver to an Error or String method,
however, the output is the undecorated string, \"\<nil\>\".

### Scanning 

An analogous set of functions scans formatted text to yield values.
Scan, Scanf and Scanln read from os.Stdin; Fscan, Fscanf and Fscanln
read from a specified io.Reader; Sscan, Sscanf and Sscanln read from an
argument string.

Scan, Fscan, Sscan treat newlines in the input as spaces.

Scanln, Fscanln and Sscanln stop scanning at a newline and require that
the items be followed by a newline or EOF.

Scanf, Fscanf, and Sscanf parse the arguments according to a format
string, analogous to that of Printf. In the text that follows, \'space\'
means any Unicode whitespace character except newline.

In the format string, a verb introduced by the % character consumes and
parses input; these verbs are described in more detail below. A
character other than %, space, or newline in the format consumes exactly
that input character, which must be present. A newline with zero or more
spaces before it in the format string consumes zero or more spaces in
the input followed by a single newline or the end of the input. A space
following a newline in the format string consumes zero or more spaces in
the input. Otherwise, any run of one or more spaces in the format string
consumes as many spaces as possible in the input. Unless the run of
spaces in the format string appears adjacent to a newline, the run must
consume at least one space from the input or find the end of the input.

The handling of spaces and newlines differs from that of C\'s scanf
family: in C, newlines are treated as any other space, and it is never
an error when a run of spaces in the format string finds no spaces to
consume in the input.

The verbs behave analogously to those of Printf. For example, %x will
scan an integer as a hexadecimal number, and %v will scan the default
representation format for the value. The Printf verbs %p and %T and the
flags \# and + are not implemented. For floating-point and complex
values, all valid formatting verbs (%b %e %E %f %F %g %G %x %X and %v)
are equivalent and accept both decimal and hexadecimal notation (for
example: \"2.3e+7\", \"0x4.5p-8\") and digit-separating underscores (for
example: \"3.14159\_26535\_89793\").

Input processed by verbs is implicitly space-delimited: the
implementation of every verb except %c starts by discarding leading
spaces from the remaining input, and the %s verb (and %v reading into a
string) stops consuming input at the first space or newline character.

The familiar base-setting prefixes 0b (binary), 0o and 0 (octal), and 0x
(hexadecimal) are accepted when scanning integers without a format or
with the %v verb, as are digit-separating underscores.

Width is interpreted in the input text but there is no syntax for
scanning with a precision (no %5.2f, just %5f). If width is provided, it
applies after leading spaces are trimmed and specifies the maximum
number of runes to read to satisfy the verb. For example,

```go
Sscanf(" 1234567 ", "%5s%d", &s, &i)
```

will set s to \"12345\" and i to 67 while

```go
Sscanf(" 12 34 567 ", "%5s%d", &s, &i)
```

will set s to \"12\" and i to 34.

In all the scanning functions, a carriage return followed immediately by
a newline is treated as a plain newline (\\r\\n means the same as \\n).

In all the scanning functions, if an operand implements method Scan
(that is, it implements the Scanner interface) that method will be used
to scan the text for that operand. Also, if the number of arguments
scanned is less than the number of arguments provided, an error is
returned.

All arguments to be scanned must be either pointers to basic types or
implementations of the Scanner interface.

Like Scanf and Fscanf, Sscanf need not consume its entire input. There
is no way to recover how much of the input string Sscanf used.

Note: Fscan etc. can read one character (rune) past the input they
return, which means that a loop calling a scan routine may skip some of
the input. This is usually a problem only when there is no space between
input values. If the reader provided to Fscan implements ReadRune, that
method will be used to read characters. If the reader also implements
UnreadRune, that method will be used to save the character and
successive calls will not lose data. To attach ReadRune and UnreadRune
methods to a reader without that capability, use bufio.NewReader.

#### [Example (Formats)]

These examples demonstrate the basics of printing using a format string.
Printf, Sprintf, and Fprintf all take a format string that specifies how
to format the subsequent arguments. For example, %d (we call that a
\'verb\') says to print the corresponding argument, which must be an
integer (or something containing an integer, such as a slice of ints) in
decimal. The verb %v (\'v\' for \'value\') always formats the argument
in its default form, just how Print or Println would show it. The
special verb %T (\'T\' for \'Type\') prints the type of the argument
rather than its value. The examples are not exhaustive; see the package
comment for all the details.

Code:

```go
// A basic set of examples showing that %v is the default format, in this
// case decimal for integers, which can be explicitly requested with %d;
// the output is just what Println generates.
integer := 23
// Each of these prints "23" (without the quotes).
fmt.Println(integer)
fmt.Printf("%v\n", integer)
fmt.Printf("%d\n", integer)

// The special verb %T shows the type of an item rather than its value.
fmt.Printf("%T %T\n", integer, &integer)
// Result: int *int

// Println(x) is the same as Printf("%v\n", x) so we will use only Printf
// in the following examples. Each one demonstrates how to format values of
// a particular type, such as integers or strings. We start each format
// string with %v to show the default output and follow that with one or
// more custom formats.

// Booleans print as "true" or "false" with %v or %t.
truth := true
fmt.Printf("%v %t\n", truth, truth)
// Result: true true

// Integers print as decimals with %v and %d,
// or in hex with %x, octal with %o, or binary with %b.
answer := 42
fmt.Printf("%v %d %x %o %b\n", answer, answer, answer, answer, answer)
// Result: 42 42 2a 52 101010

// Floats have multiple formats: %v and %g print a compact representation,
// while %f prints a decimal point and %e uses exponential notation. The
// format %6.2f used here shows how to set the width and precision to
// control the appearance of a floating-point value. In this instance, 6 is
// the total width of the printed text for the value (note the extra spaces
// in the output) and 2 is the number of decimal places to show.
pi := math.Pi
fmt.Printf("%v %g %.2f (%6.2f) %e\n", pi, pi, pi, pi, pi)
// Result: 3.141592653589793 3.141592653589793 3.14 (  3.14) 3.141593e+00

// Complex numbers format as parenthesized pairs of floats, with an 'i'
// after the imaginary part.
point := 110.7 + 22.5i
fmt.Printf("%v %g %.2f %.2e\n", point, point, point, point)
// Result: (110.7+22.5i) (110.7+22.5i) (110.70+22.50i) (1.11e+02+2.25e+01i)

// Runes are integers but when printed with %c show the character with that
// Unicode value. The %q verb shows them as quoted characters, %U as a
// hex Unicode code point, and %#U as both a code point and a quoted
// printable form if the rune is printable.
smile := '😀'
fmt.Printf("%v %d %c %q %U %#U\n", smile, smile, smile, smile, smile, smile)
// Result: 128512 128512 😀 '😀' U+1F600 U+1F600 '😀'

// Strings are formatted with %v and %s as-is, with %q as quoted strings,
// and %#q as backquoted strings.
placeholders := `foo "bar"`
fmt.Printf("%v %s %q %#q\n", placeholders, placeholders, placeholders, placeholders)
// Result: foo "bar" foo "bar" "foo \"bar\"" `foo "bar"`

// Maps formatted with %v show keys and values in their default formats.
// The %#v form (the # is called a "flag" in this context) shows the map in
// the Go source format. Maps are printed in a consistent order, sorted
// by the values of the keys.
isLegume := map[string]bool{
    "peanut":    true,
    "dachshund": false,
}
fmt.Printf("%v %#v\n", isLegume, isLegume)
// Result: map[dachshund:false peanut:true] map[string]bool{"dachshund":false, "peanut":true}

// Structs formatted with %v show field values in their default formats.
// The %+v form shows the fields by name, while %#v formats the struct in
// Go source format.
person := struct {
    Name string
    Age  int
}{"Kim", 22}
fmt.Printf("%v %+v %#v\n", person, person, person)
// Result: {Kim 22} {Name:Kim Age:22} struct { Name string; Age int }{Name:"Kim", Age:22}

// The default format for a pointer shows the underlying value preceded by
// an ampersand. The %p verb prints the pointer value in hex. We use a
// typed nil for the argument to %p here because the value of any non-nil
// pointer would change from run to run; run the commented-out Printf
// call yourself to see.
pointer := &person
fmt.Printf("%v %p\n", pointer, (*int)(nil))
// Result: &{Kim 22} 0x0
// fmt.Printf("%v %p\n", pointer, pointer)
// Result: &{Kim 22} 0x010203 // See comment above.

// Arrays and slices are formatted by applying the format to each element.
greats := [5]string{"Kitano", "Kobayashi", "Kurosawa", "Miyazaki", "Ozu"}
fmt.Printf("%v %q\n", greats, greats)
// Result: [Kitano Kobayashi Kurosawa Miyazaki Ozu] ["Kitano" "Kobayashi" "Kurosawa" "Miyazaki" "Ozu"]

kGreats := greats[:3]
fmt.Printf("%v %q %#v\n", kGreats, kGreats, kGreats)
// Result: [Kitano Kobayashi Kurosawa] ["Kitano" "Kobayashi" "Kurosawa"] []string{"Kitano", "Kobayashi", "Kurosawa"}

// Byte slices are special. Integer verbs like %d print the elements in
// that format. The %s and %q forms treat the slice like a string. The %x
// verb has a special form with the space flag that puts a space between
// the bytes.
cmd := []byte("a⌘")
fmt.Printf("%v %d %s %q %x % x\n", cmd, cmd, cmd, cmd, cmd, cmd)
// Result: [97 226 140 152] [97 226 140 152] a⌘ "a⌘" 61e28c98 61 e2 8c 98

// Types that implement Stringer are printed the same as strings. Because
// Stringers return a string, we can print them using a string-specific
// verb such as %q.
now := time.Unix(123456789, 0).UTC() // time.Time implements fmt.Stringer.
fmt.Printf("%v %q\n", now, now)
// Result: 1973-11-29 21:33:09 +0000 UTC "1973-11-29 21:33:09 +0000 UTC"
```

Output:

```go
23
23
23
int *int
true true
42 42 2a 52 101010
3.141592653589793 3.141592653589793 3.14 (  3.14) 3.141593e+00
(110.7+22.5i) (110.7+22.5i) (110.70+22.50i) (1.11e+02+2.25e+01i)
128512 128512 😀 '😀' U+1F600 U+1F600 '😀'
foo "bar" foo "bar" "foo \"bar\"" `foo "bar"`
map[dachshund:false peanut:true] map[string]bool{"dachshund":false, "peanut":true}
{Kim 22} {Name:Kim Age:22} struct { Name string; Age int }{Name:"Kim", Age:22}
&{Kim 22} 0x0
[Kitano Kobayashi Kurosawa Miyazaki Ozu] ["Kitano" "Kobayashi" "Kurosawa" "Miyazaki" "Ozu"]
[Kitano Kobayashi Kurosawa] ["Kitano" "Kobayashi" "Kurosawa"] []string{"Kitano", "Kobayashi", "Kurosawa"}
[97 226 140 152] [97 226 140 152] a⌘ "a⌘" 61e28c98 61 e2 8c 98
1973-11-29 21:33:09 +0000 UTC "1973-11-29 21:33:09 +0000 UTC"
```

#### [Example (Printers)]

Print, Println, and Printf lay out their arguments differently. In this
example we can compare their behaviors. Println always adds blanks
between the items it prints, while Print adds blanks only between
non-string arguments and Printf does exactly what it is told. Sprint,
Sprintln, Sprintf, Fprint, Fprintln, and Fprintf behave the same as
their corresponding Print, Println, and Printf functions shown here.

Code:

```go
a, b := 3.0, 4.0
h := math.Hypot(a, b)

// Print inserts blanks between arguments when neither is a string.
// It does not add a newline to the output, so we add one explicitly.
fmt.Print("The vector (", a, b, ") has length ", h, ".\n")

// Println always inserts spaces between its arguments,
// so it cannot be used to produce the same output as Print in this case;
// its output has extra spaces.
// Also, Println always adds a newline to the output.
fmt.Println("The vector (", a, b, ") has length", h, ".")

// Printf provides complete control but is more complex to use.
// It does not add a newline to the output, so we add one explicitly
// at the end of the format specifier string.
fmt.Printf("The vector (%g %g) has length %g.\n", a, b, h)
```

Output:

```go
The vector (3 4) has length 5.
The vector ( 3 4 ) has length 5 .
The vector (3 4) has length 5.
```

Index 
-----

-   [func Append(b \[\]byte, a \...any) \[\]byte](#Append)
-   [func Appendf(b \[\]byte, format string, a \...any)
    \[\]byte](#Appendf)
-   [func Appendln(b \[\]byte, a \...any) \[\]byte](#Appendln)
-   [func Errorf(format string, a \...any) error](#Errorf)
-   [func FormatString(state State, verb rune) string](#FormatString)
-   [func Fprint(w io.Writer, a \...any) (n int, err error)](#Fprint)
-   [func Fprintf(w io.Writer, format string, a \...any) (n int, err
    error)](#Fprintf)
-   [func Fprintln(w io.Writer, a \...any) (n int, err
    error)](#Fprintln)
-   [func Fscan(r io.Reader, a \...any) (n int, err error)](#Fscan)
-   [func Fscanf(r io.Reader, format string, a \...any) (n int, err
    error)](#Fscanf)
-   [func Fscanln(r io.Reader, a \...any) (n int, err error)](#Fscanln)
-   [func Print(a \...any) (n int, err error)](#Print)
-   [func Printf(format string, a \...any) (n int, err error)](#Printf)
-   [func Println(a \...any) (n int, err error)](#Println)
-   [func Scan(a \...any) (n int, err error)](#Scan)
-   [func Scanf(format string, a \...any) (n int, err error)](#Scanf)
-   [func Scanln(a \...any) (n int, err error)](#Scanln)
-   [func Sprint(a \...any) string](#Sprint)
-   [func Sprintf(format string, a \...any) string](#Sprintf)
-   [func Sprintln(a \...any) string](#Sprintln)
-   [func Sscan(str string, a \...any) (n int, err error)](#Sscan)
-   [func Sscanf(str string, format string, a \...any) (n int, err
    error)](#Sscanf)
-   [func Sscanln(str string, a \...any) (n int, err error)](#Sscanln)
-   [type Formatter](#Formatter)
-   [type GoStringer](#GoStringer)
-   [type ScanState](#ScanState)
-   [type Scanner](#Scanner)
-   [type State](#State)
-   [type Stringer](#Stringer)

 
### Examples

[Errorf](#example_Errorf)

[Fprint](#example_Fprint)

[Fprintf](#example_Fprintf)

[Fprintln](#example_Fprintln)

[Fscanf](#example_Fscanf)

[Fscanln](#example_Fscanln)

[GoStringer](#example_GoStringer)

[Print](#example_Print)

[Printf](#example_Printf)

[Println](#example_Println)

[Sprint](#example_Sprint)

[Sprintf](#example_Sprintf)

[Sprintln](#example_Sprintln)

[Sscanf](#example_Sscanf)

[Stringer](#example_Stringer)

[Package (Formats)](#example__formats)

[Package (Printers)](#example__printers)


### Package files

doc.go errors.go format.go print.go scan.go

func Append 
--------------------------------------------

```go
func Append(b []byte, a ...any) []byte
```

Append formats using the default formats for its operands, appends the
result to the byte slice, and returns the updated slice.

func Appendf 
---------------------------------------------

```go
func Appendf(b []byte, format string, a ...any) []byte
```

Appendf formats according to a format specifier, appends the result to
the byte slice, and returns the updated slice.

func Appendln 
----------------------------------------------

```go
func Appendln(b []byte, a ...any) []byte
```

Appendln formats using the default formats for its operands, appends the
result to the byte slice, and returns the updated slice. Spaces are
always added between operands and a newline is appended.

func Errorf 
-----------

```go
func Errorf(format string, a ...any) error
```

Errorf formats according to a format specifier and returns the string as
a value that satisfies error.

If the format specifier includes a %w verb with an error operand, the
returned error will implement an Unwrap method returning the operand. If
there is more than one %w verb, the returned error will implement an
Unwrap method returning a \[\]error containing all the %w operands in
the order they appear in the arguments. It is invalid to supply the %w
verb with an operand that does not implement the error interface. The %w
verb is otherwise a synonym for %v.

#### [Example]

The Errorf function lets us use formatting features to create
descriptive error messages.

Code:

```go
const name, id = "bueller", 17
err := fmt.Errorf("user %q (id %d) not found", name, id)
fmt.Println(err.Error())
```

Output:

```go
user "bueller" (id 17) not found
```

func FormatString 
--------------------------------------------------

```go
func FormatString(state State, verb rune) string
```

FormatString returns a string representing the fully qualified
formatting directive captured by the State, followed by the argument
verb. (State does not itself contain the verb.) The result has a leading
percent sign followed by any flags, the width, and the precision.
Missing flags, width, and precision are omitted. This function allows a
Formatter to reconstruct the original directive triggering the call to
Format.

func Fprint 
-----------

```go
func Fprint(w io.Writer, a ...any) (n int, err error)
```

Fprint formats using the default formats for its operands and writes to
w. Spaces are added between operands when neither is a string. It
returns the number of bytes written and any write error encountered.

#### [Example]

Code:

```go
const name, age = "Kim", 22
n, err := fmt.Fprint(os.Stdout, name, " is ", age, " years old.\n")

// The n and err return values from Fprint are
// those returned by the underlying io.Writer.
if err != nil {
    fmt.Fprintf(os.Stderr, "Fprint: %v\n", err)
}
fmt.Print(n, " bytes written.\n")
```

Output:

```go
Kim is 22 years old.
21 bytes written.
```

func Fprintf 
------------

```go
func Fprintf(w io.Writer, format string, a ...any) (n int, err error)
```

Fprintf formats according to a format specifier and writes to w. It
returns the number of bytes written and any write error encountered.

#### [Example]

Code:

```go
const name, age = "Kim", 22
n, err := fmt.Fprintf(os.Stdout, "%s is %d years old.\n", name, age)

// The n and err return values from Fprintf are
// those returned by the underlying io.Writer.
if err != nil {
    fmt.Fprintf(os.Stderr, "Fprintf: %v\n", err)
}
fmt.Printf("%d bytes written.\n", n)
```

Output:

```go
Kim is 22 years old.
21 bytes written.
```

func Fprintln 
-------------

```go
func Fprintln(w io.Writer, a ...any) (n int, err error)
```

Fprintln formats using the default formats for its operands and writes
to w. Spaces are always added between operands and a newline is
appended. It returns the number of bytes written and any write error
encountered.

#### [Example]

Code:

```go
const name, age = "Kim", 22
n, err := fmt.Fprintln(os.Stdout, name, "is", age, "years old.")

// The n and err return values from Fprintln are
// those returned by the underlying io.Writer.
if err != nil {
    fmt.Fprintf(os.Stderr, "Fprintln: %v\n", err)
}
fmt.Println(n, "bytes written.")
```

Output:

```go
Kim is 22 years old.
21 bytes written.
```

func Fscan 
----------

```go
func Fscan(r io.Reader, a ...any) (n int, err error)
```

Fscan scans text read from r, storing successive space-separated values
into successive arguments. Newlines count as space. It returns the
number of items successfully scanned. If that is less than the number of
arguments, err will report why.

func Fscanf 
-----------

```go
func Fscanf(r io.Reader, format string, a ...any) (n int, err error)
```

Fscanf scans text read from r, storing successive space-separated values
into successive arguments as determined by the format. It returns the
number of items successfully parsed. Newlines in the input must match
newlines in the format.

#### [Example]

Code:

```go
var (
    i int
    b bool
    s string
)
r := strings.NewReader("5 true gophers")
n, err := fmt.Fscanf(r, "%d %t %s", &i, &b, &s)
if err != nil {
    fmt.Fprintf(os.Stderr, "Fscanf: %v\n", err)
}
fmt.Println(i, b, s)
fmt.Println(n)
```

Output:

```go
5 true gophers
3
```

func Fscanln 
------------

```go
func Fscanln(r io.Reader, a ...any) (n int, err error)
```

Fscanln is similar to Fscan, but stops scanning at a newline and after
the final item there must be a newline or EOF.

#### [Example]

Code:

```go
s := `dmr 1771 1.61803398875
    ken 271828 3.14159`
r := strings.NewReader(s)
var a string
var b int
var c float64
for {
    n, err := fmt.Fscanln(r, &a, &b, &c)
    if err == io.EOF {
        break
    }
    if err != nil {
        panic(err)
    }
    fmt.Printf("%d: %s, %d, %f\n", n, a, b, c)
}
```

Output:

```go
3: dmr, 1771, 1.618034
3: ken, 271828, 3.141590
```

func Print 
----------

```go
func Print(a ...any) (n int, err error)
```

Print formats using the default formats for its operands and writes to
standard output. Spaces are added between operands when neither is a
string. It returns the number of bytes written and any write error
encountered.

#### [Example]

Code:

```go
const name, age = "Kim", 22
fmt.Print(name, " is ", age, " years old.\n")

// It is conventional not to worry about any
// error returned by Print.
```

Output:

```go
Kim is 22 years old.
```

func Printf 
-----------

```go
func Printf(format string, a ...any) (n int, err error)
```

Printf formats according to a format specifier and writes to standard
output. It returns the number of bytes written and any write error
encountered.

#### [Example]

Code:

```go
const name, age = "Kim", 22
fmt.Printf("%s is %d years old.\n", name, age)

// It is conventional not to worry about any
// error returned by Printf.
```

Output:

```go
Kim is 22 years old.
```

func Println 
------------

```go
func Println(a ...any) (n int, err error)
```

Println formats using the default formats for its operands and writes to
standard output. Spaces are always added between operands and a newline
is appended. It returns the number of bytes written and any write error
encountered.

#### [Example]

Code:

```go
const name, age = "Kim", 22
fmt.Println(name, "is", age, "years old.")

// It is conventional not to worry about any
// error returned by Println.
```

Output:

```go
Kim is 22 years old.
```

func Scan 
---------

```go
func Scan(a ...any) (n int, err error)
```

Scan scans text read from standard input, storing successive
space-separated values into successive arguments. Newlines count as
space. It returns the number of items successfully scanned. If that is
less than the number of arguments, err will report why.

func Scanf 
----------

```go
func Scanf(format string, a ...any) (n int, err error)
```

Scanf scans text read from standard input, storing successive
space-separated values into successive arguments as determined by the
format. It returns the number of items successfully scanned. If that is
less than the number of arguments, err will report why. Newlines in the
input must match newlines in the format. The one exception: the verb %c
always scans the next rune in the input, even if it is a space (or tab
etc.) or newline.

func Scanln 
-----------

```go
func Scanln(a ...any) (n int, err error)
```

Scanln is similar to Scan, but stops scanning at a newline and after the
final item there must be a newline or EOF.

func Sprint 
-----------

```go
func Sprint(a ...any) string
```

Sprint formats using the default formats for its operands and returns
the resulting string. Spaces are added between operands when neither is
a string.

#### [Example]

Code:

```go
const name, age = "Kim", 22
s := fmt.Sprint(name, " is ", age, " years old.\n")

io.WriteString(os.Stdout, s) // Ignoring error for simplicity.
```

Output:

```go
Kim is 22 years old.
```

func Sprintf 
------------

```go
func Sprintf(format string, a ...any) string
```

Sprintf formats according to a format specifier and returns the
resulting string.

#### [Example]

Code:

```go
const name, age = "Kim", 22
s := fmt.Sprintf("%s is %d years old.\n", name, age)

io.WriteString(os.Stdout, s) // Ignoring error for simplicity.
```

Output:

```go
Kim is 22 years old.
```

func Sprintln 
-------------

```go
func Sprintln(a ...any) string
```

Sprintln formats using the default formats for its operands and returns
the resulting string. Spaces are always added between operands and a
newline is appended.

#### [Example]

Code:

```go
const name, age = "Kim", 22
s := fmt.Sprintln(name, "is", age, "years old.")

io.WriteString(os.Stdout, s) // Ignoring error for simplicity.
```

Output:

```go
Kim is 22 years old.
```

func Sscan 
----------

```go
func Sscan(str string, a ...any) (n int, err error)
```

Sscan scans the argument string, storing successive space-separated
values into successive arguments. Newlines count as space. It returns
the number of items successfully scanned. If that is less than the
number of arguments, err will report why.

func Sscanf 
-----------

```go
func Sscanf(str string, format string, a ...any) (n int, err error)
```

Sscanf scans the argument string, storing successive space-separated
values into successive arguments as determined by the format. It returns
the number of items successfully parsed. Newlines in the input must
match newlines in the format.

#### [Example]

Code:

```go
var name string
var age int
n, err := fmt.Sscanf("Kim is 22 years old", "%s is %d years old", &name, &age)
if err != nil {
    panic(err)
}
fmt.Printf("%d: %s, %d\n", n, name, age)
```

Output:

```go
2: Kim, 22
```

func Sscanln 
------------

```go
func Sscanln(str string, a ...any) (n int, err error)
```

Sscanln is similar to Sscan, but stops scanning at a newline and after
the final item there must be a newline or EOF.

type Formatter 
--------------

Formatter is implemented by any value that has a Format method. The
implementation controls how State and rune are interpreted, and may call
Sprint() or Fprint(f) etc. to generate its output.

```go
type Formatter interface {
    Format(f State, verb rune)
}
```

type GoStringer 
---------------

GoStringer is implemented by any value that has a GoString method, which
defines the Go syntax for that value. The GoString method is used to
print values passed as an operand to a %\#v format.

```go
type GoStringer interface {
    GoString() string
}
```

#### [Example]

Code:

```go
package fmt_test

import (
    "fmt"
)

// Address has a City, State and a Country.
type Address struct {
    City    string
    State   string
    Country string
}

// Person has a Name, Age and Address.
type Person struct {
    Name string
    Age  uint
    Addr *Address
}

// GoString makes Person satisfy the GoStringer interface.
// The return value is valid Go code that can be used to reproduce the Person struct.
func (p Person) GoString() string {
    if p.Addr != nil {
        return fmt.Sprintf("Person{Name: %q, Age: %d, Addr: &Address{City: %q, State: %q, Country: %q}}", p.Name, int(p.Age), p.Addr.City, p.Addr.State, p.Addr.Country)
    }
    return fmt.Sprintf("Person{Name: %q, Age: %d}", p.Name, int(p.Age))
}

func ExampleGoStringer() {
    p1 := Person{
        Name: "Warren",
        Age:  31,
        Addr: &Address{
            City:    "Denver",
            State:   "CO",
            Country: "U.S.A.",
        },
    }
    // If GoString() wasn't implemented, the output of `fmt.Printf("%#v", p1)` would be similar to
    // Person{Name:"Warren", Age:0x1f, Addr:(*main.Address)(0x10448240)}
    fmt.Printf("%#v\n", p1)

    p2 := Person{
        Name: "Theia",
        Age:  4,
    }
    // If GoString() wasn't implemented, the output of `fmt.Printf("%#v", p2)` would be similar to
    // Person{Name:"Theia", Age:0x4, Addr:(*main.Address)(nil)}
    fmt.Printf("%#v\n", p2)

    // Output:
    // Person{Name: "Warren", Age: 31, Addr: &Address{City: "Denver", State: "CO", Country: "U.S.A."}}
    // Person{Name: "Theia", Age: 4}
}
```

type ScanState 
--------------

ScanState represents the scanner state passed to custom scanners.
Scanners may do rune-at-a-time scanning or ask the ScanState to discover
the next space-delimited token.

```go
type ScanState interface {
    // ReadRune reads the next rune (Unicode code point) from the input.
    // If invoked during Scanln, Fscanln, or Sscanln, ReadRune() will
    // return EOF after returning the first '\n' or when reading beyond
    // the specified width.
    ReadRune() (r rune, size int, err error)
    // UnreadRune causes the next call to ReadRune to return the same rune.
    UnreadRune() error
    // SkipSpace skips space in the input. Newlines are treated appropriately
    // for the operation being performed; see the package documentation
    // for more information.
    SkipSpace()
    // Token skips space in the input if skipSpace is true, then returns the
    // run of Unicode code points c satisfying f(c).  If f is nil,
    // !unicode.IsSpace(c) is used; that is, the token will hold non-space
    // characters. Newlines are treated appropriately for the operation being
    // performed; see the package documentation for more information.
    // The returned slice points to shared data that may be overwritten
    // by the next call to Token, a call to a Scan function using the ScanState
    // as input, or when the calling Scan method returns.
    Token(skipSpace bool, f func(rune) bool) (token []byte, err error)
    // Width returns the value of the width option and whether it has been set.
    // The unit is Unicode code points.
    Width() (wid int, ok bool)
    // Because ReadRune is implemented by the interface, Read should never be
    // called by the scanning routines and a valid implementation of
    // ScanState may choose always to return an error from Read.
    Read(buf []byte) (n int, err error)
}
```

type Scanner 
------------

Scanner is implemented by any value that has a Scan method, which scans
the input for the representation of a value and stores the result in the
receiver, which must be a pointer to be useful. The Scan method is
called for any argument to Scan, Scanf, or Scanln that implements it.

```go
type Scanner interface {
    Scan(state ScanState, verb rune) error
}
```

type State 
----------

State represents the printer state passed to custom formatters. It
provides access to the io.Writer interface plus information about the
flags and options for the operand\'s format specifier.

```go
type State interface {
    // Write is the function to call to emit formatted output to be printed.
    Write(b []byte) (n int, err error)
    // Width returns the value of the width option and whether it has been set.
    Width() (wid int, ok bool)
    // Precision returns the value of the precision option and whether it has been set.
    Precision() (prec int, ok bool)

    // Flag reports whether the flag c, a character, has been set.
    Flag(c int) bool
}
```

type Stringer 
-------------

Stringer is implemented by any value that has a String method, which
defines the "native" format for that value. The String method is used to
print values passed as an operand to any format that accepts a string or
to an unformatted printer such as Print.

```go
type Stringer interface {
    String() string
}
```

#### [Example]

Code:

```go
package fmt_test

import (
    "fmt"
)

// Animal has a Name and an Age to represent an animal.
type Animal struct {
    Name string
    Age  uint
}

// String makes Animal satisfy the Stringer interface.
func (a Animal) String() string {
    return fmt.Sprintf("%v (%d)", a.Name, a.Age)
}

func ExampleStringer() {
    a := Animal{
        Name: "Gopher",
        Age:  2,
    }
    fmt.Println(a)
    // Output: Gopher (2)
}
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/fmt/>

