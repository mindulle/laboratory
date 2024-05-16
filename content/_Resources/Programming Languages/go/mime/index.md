Package mime
============

-   `import "mime"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)
-   [Subdirectories](#pkg-subdirectories)

Overview 
--------

Package mime implements parts of the MIME spec.

Index 
-----

-   [Constants](#pkg-constants)
-   [Variables](#pkg-variables)
-   [func AddExtensionType(ext, typ string) error](#AddExtensionType)
-   [func ExtensionsByType(typ string) (\[\]string, error)](#ExtensionsByType)
-   [func FormatMediaType(t string, param map\[string\]string)
    string](#FormatMediaType)
-   [func ParseMediaType(v string) (mediatype string, params
    map\[string\]string, err error)](#ParseMediaType)
-   [func TypeByExtension(ext string) string](#TypeByExtension)
-   [type WordDecoder](#WordDecoder)
-   [func (d \*WordDecoder) Decode(word string) (string,
    error)](#WordDecoder.Decode)
-   [func (d \*WordDecoder) DecodeHeader(header string) (string,
    error)](#WordDecoder.DecodeHeader)
-   [type WordEncoder](#WordEncoder)
-   [func (e WordEncoder) Encode(charset, s string)
    string](#WordEncoder.Encode)

 
### Examples

[FormatMediaType](#example_FormatMediaType)

[ParseMediaType](#example_ParseMediaType)

[WordDecoder.Decode](#example_WordDecoder_Decode)

[WordDecoder.DecodeHeader](#example_WordDecoder_DecodeHeader)

[WordEncoder.Encode](#example_WordEncoder_Encode)


### Package files

encodedword.go grammar.go mediatype.go type.go type\_unix.go

Constants 
---------

```go
const (
    // BEncoding represents Base64 encoding scheme as defined by RFC 2045.
    BEncoding = WordEncoder('b')
    // QEncoding represents the Q-encoding scheme as defined by RFC 2047.
    QEncoding = WordEncoder('q')
)
```

Variables 
---------

ErrInvalidMediaParameter is returned by ParseMediaType if the media type
value was found but there was an error parsing the optional parameters

```go
var ErrInvalidMediaParameter = errors.New("mime: invalid media parameter")
```

func AddExtensionType 
---------------------

```go
func AddExtensionType(ext, typ string) error
```

AddExtensionType sets the MIME type associated with the extension ext to
typ. The extension should begin with a leading dot, as in \".html\".

func ExtensionsByType 
----------------------------------------------------

```go
func ExtensionsByType(typ string) ([]string, error)
```

ExtensionsByType returns the extensions known to be associated with the
MIME type typ. The returned extensions will each begin with a leading
dot, as in \".html\". When typ has no associated extensions,
ExtensionsByType returns an nil slice.

func FormatMediaType 
--------------------

```go
func FormatMediaType(t string, param map[string]string) string
```

FormatMediaType serializes mediatype t and the parameters param as a
media type conforming to RFC 2045 and RFC 2616. The type and parameter
names are written in lower-case. When any of the arguments result in a
standard violation then FormatMediaType returns the empty string.

#### [Example]

Code:

```go
mediatype := "text/html"
params := map[string]string{
    "charset": "utf-8",
}

result := mime.FormatMediaType(mediatype, params)

fmt.Println("result:", result)
```

Output:

```go
result: text/html; charset=utf-8
```

func ParseMediaType 
-------------------

```go
func ParseMediaType(v string) (mediatype string, params map[string]string, err error)
```

ParseMediaType parses a media type value and any optional parameters,
per RFC 1521. Media types are the values in Content-Type and
Content-Disposition headers (RFC 2183). On success, ParseMediaType
returns the media type converted to lowercase and trimmed of white space
and a non-nil map. If there is an error parsing the optional parameter,
the media type will be returned along with the error
ErrInvalidMediaParameter. The returned map, params, maps from the
lowercase attribute to the attribute value with its case preserved.

#### [Example]

Code:

```go
mediatype, params, err := mime.ParseMediaType("text/html; charset=utf-8")
if err != nil {
    panic(err)
}

fmt.Println("type:", mediatype)
fmt.Println("charset:", params["charset"])
```

Output:

```go
type: text/html
charset: utf-8
```

func TypeByExtension 
--------------------

```go
func TypeByExtension(ext string) string
```

TypeByExtension returns the MIME type associated with the file extension
ext. The extension ext should begin with a leading dot, as in \".html\".
When ext has no associated type, TypeByExtension returns \"\".

Extensions are looked up first case-sensitively, then
case-insensitively.

The built-in table is small but on unix it is augmented by the local
system\'s MIME-info database or mime.types file(s) if available under
one or more of these names:

```go
/usr/local/share/mime/globs2
/usr/share/mime/globs2
/etc/mime.types
/etc/apache2/mime.types
/etc/apache/mime.types
```

On Windows, MIME types are extracted from the registry.

Text types have the charset parameter set to \"utf-8\" by default.

type WordDecoder 
-----------------------------------------------

A WordDecoder decodes MIME headers containing RFC 2047 encoded-words.

```go
type WordDecoder struct {
    // CharsetReader, if non-nil, defines a function to generate
    // charset-conversion readers, converting from the provided
    // charset into UTF-8.
    // Charsets are always lower-case. utf-8, iso-8859-1 and us-ascii charsets
    // are handled by default.
    // One of the CharsetReader's result values must be non-nil.
    CharsetReader func(charset string, input io.Reader) (io.Reader, error)
}
```

### func (\*WordDecoder) Decode 

```go
func (d *WordDecoder) Decode(word string) (string, error)
```

Decode decodes an RFC 2047 encoded-word.

#### [Example]

Code:

```go
dec := new(mime.WordDecoder)
header, err := dec.Decode("=?utf-8?q?=C2=A1Hola,_se=C3=B1or!?=")
if err != nil {
    panic(err)
}
fmt.Println(header)

dec.CharsetReader = func(charset string, input io.Reader) (io.Reader, error) {
    switch charset {
    case "x-case":
        // Fake character set for example.
        // Real use would integrate with packages such
        // as code.google.com/p/go-charset
        content, err := io.ReadAll(input)
        if err != nil {
            return nil, err
        }
        return bytes.NewReader(bytes.ToUpper(content)), nil
    default:
        return nil, fmt.Errorf("unhandled charset %q", charset)
    }
}
header, err = dec.Decode("=?x-case?q?hello!?=")
if err != nil {
    panic(err)
}
fmt.Println(header)
```

Output:

```go
¡Hola, señor!
HELLO!
```

### func (\*WordDecoder) DecodeHeader 

```go
func (d *WordDecoder) DecodeHeader(header string) (string, error)
```

DecodeHeader decodes all encoded-words of the given string. It returns
an error if and only if CharsetReader of d returns an error.

#### [Example]

Code:

```go
dec := new(mime.WordDecoder)
header, err := dec.DecodeHeader("=?utf-8?q?=C3=89ric?= <eric@example.org>, =?utf-8?q?Ana=C3=AFs?= <anais@example.org>")
if err != nil {
    panic(err)
}
fmt.Println(header)

header, err = dec.DecodeHeader("=?utf-8?q?=C2=A1Hola,?= =?utf-8?q?_se=C3=B1or!?=")
if err != nil {
    panic(err)
}
fmt.Println(header)

dec.CharsetReader = func(charset string, input io.Reader) (io.Reader, error) {
    switch charset {
    case "x-case":
        // Fake character set for example.
        // Real use would integrate with packages such
        // as code.google.com/p/go-charset
        content, err := io.ReadAll(input)
        if err != nil {
            return nil, err
        }
        return bytes.NewReader(bytes.ToUpper(content)), nil
    default:
        return nil, fmt.Errorf("unhandled charset %q", charset)
    }
}
header, err = dec.DecodeHeader("=?x-case?q?hello_?= =?x-case?q?world!?=")
if err != nil {
    panic(err)
}
fmt.Println(header)
```

Output:

```go
Éric <eric@example.org>, Anaïs <anais@example.org>
¡Hola, señor!
HELLO WORLD!
```

type WordEncoder 
-----------------------------------------------

A WordEncoder is an RFC 2047 encoded-word encoder.

```go
type WordEncoder byte
```

### func (WordEncoder) Encode 

```go
func (e WordEncoder) Encode(charset, s string) string
```

Encode returns the encoded-word form of s. If s is ASCII without special
characters, it is returned unchanged. The provided charset is the IANA
charset name of s. It is case insensitive.

#### [Example]

Code:

```go
fmt.Println(mime.QEncoding.Encode("utf-8", "¡Hola, señor!"))
fmt.Println(mime.QEncoding.Encode("utf-8", "Hello!"))
fmt.Println(mime.BEncoding.Encode("UTF-8", "¡Hola, señor!"))
fmt.Println(mime.QEncoding.Encode("ISO-8859-1", "Caf\xE9"))
```

Output:

```go
=?utf-8?q?=C2=A1Hola,_se=C3=B1or!?=
Hello!
=?UTF-8?b?wqFIb2xhLCBzZcOxb3Ih?=
=?ISO-8859-1?q?Caf=E9?=
```

Subdirectories 
--------------

 
Name


Synopsis

[..](../index)

[multipart](multipart/index)

Package multipart implements MIME multipart parsing, as defined in RFC
2046.

[quotedprintable](quotedprintable/index)

Package quotedprintable implements quoted-printable encoding as
specified by RFC 2045.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/mime/>

