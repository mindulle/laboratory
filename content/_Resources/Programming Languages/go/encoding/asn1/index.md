Package asn1
============

-   `import "encoding/asn1"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package asn1 implements parsing of DER-encoded ASN.1 data structures, as
defined in ITU-T Rec X.690.

See also "A Layman\'s Guide to a Subset of ASN.1, BER, and DER,"
https://luca.ntop.org/Teaching/Appunti/asn1.html>.

Index 
-----

-   [Constants](#pkg-constants)
-   [Variables](#pkg-variables)
-   [func Marshal(val any) (\[\]byte, error)](#Marshal)
-   [func MarshalWithParams(val any, params string) (\[\]byte,
    error)](#MarshalWithParams)
-   [func Unmarshal(b \[\]byte, val any) (rest \[\]byte, err
    error)](#Unmarshal)
-   [func UnmarshalWithParams(b \[\]byte, val any, params string) (rest
    \[\]byte, err error)](#UnmarshalWithParams)
-   [type BitString](#BitString)
-   [func (b BitString) At(i int) int](#BitString.At)
-   [func (b BitString) RightAlign() \[\]byte](#BitString.RightAlign)
-   [type Enumerated](#Enumerated)
-   [type Flag](#Flag)
-   [type ObjectIdentifier](#ObjectIdentifier)
-   [func (oi ObjectIdentifier) Equal(other ObjectIdentifier)
    bool](#ObjectIdentifier.Equal)
-   [func (oi ObjectIdentifier) String()
    string](#ObjectIdentifier.String)
-   [type RawContent](#RawContent)
-   [type RawValue](#RawValue)
-   [type StructuralError](#StructuralError)
-   [func (e StructuralError) Error() string](#StructuralError.Error)
-   [type SyntaxError](#SyntaxError)
-   [func (e SyntaxError) Error() string](#SyntaxError.Error)

### Package files

asn1.go common.go marshal.go

Constants 
---------

ASN.1 tags represent the type of the following object.

```go
const (
    TagBoolean         = 1
    TagInteger         = 2
    TagBitString       = 3
    TagOctetString     = 4
    TagNull            = 5
    TagOID             = 6
    TagEnum            = 10
    TagUTF8String      = 12
    TagSequence        = 16
    TagSet             = 17
    TagNumericString   = 18
    TagPrintableString = 19
    TagT61String       = 20
    TagIA5String       = 22
    TagUTCTime         = 23
    TagGeneralizedTime = 24
    TagGeneralString   = 27
    TagBMPString       = 30
)
```

ASN.1 class types represent the namespace of the tag.

```go
const (
    ClassUniversal       = 0
    ClassApplication     = 1
    ClassContextSpecific = 2
    ClassPrivate         = 3
)
```

Variables 
---------

NullBytes contains bytes representing the DER-encoded ASN.1 NULL type.

```go
var NullBytes = []byte{TagNull, 0}
```

NullRawValue is a RawValue with its Tag set to the ASN.1 NULL type tag
(5).

```go
var NullRawValue = RawValue{Tag: TagNull}
```

func Marshal 
------------

```go
func Marshal(val any) ([]byte, error)
```

Marshal returns the ASN.1 encoding of val.

In addition to the struct tags recognised by Unmarshal, the following
can be used:

```go
ia5:         causes strings to be marshaled as ASN.1, IA5String values
omitempty:   causes empty slices to be skipped
printable:   causes strings to be marshaled as ASN.1, PrintableString values
utf8:        causes strings to be marshaled as ASN.1, UTF8String values
utc:         causes time.Time to be marshaled as ASN.1, UTCTime values
generalized: causes time.Time to be marshaled as ASN.1, GeneralizedTime values
```

func MarshalWithParams 
-------------------------------------------------------

```go
func MarshalWithParams(val any, params string) ([]byte, error)
```

MarshalWithParams allows field parameters to be specified for the
top-level element. The form of the params is the same as the field tags.

func Unmarshal 
--------------

```go
func Unmarshal(b []byte, val any) (rest []byte, err error)
```

Unmarshal parses the DER-encoded ASN.1 data structure b and uses the
reflect package to fill in an arbitrary value pointed at by val. Because
Unmarshal uses the reflect package, the structs being written to must
use upper case field names. If val is nil or not a pointer, Unmarshal
returns an error.

After parsing b, any bytes that were leftover and not used to fill val
will be returned in rest. When parsing a SEQUENCE into a struct, any
trailing elements of the SEQUENCE that do not have matching fields in
val will not be included in rest, as these are considered valid elements
of the SEQUENCE and not trailing data.

An ASN.1 INTEGER can be written to an int, int32, int64, or \*big.Int
(from the math/big package). If the encoded value does not fit in the Go
type, Unmarshal returns a parse error.

An ASN.1 BIT STRING can be written to a BitString.

An ASN.1 OCTET STRING can be written to a \[\]byte.

An ASN.1 OBJECT IDENTIFIER can be written to an ObjectIdentifier.

An ASN.1 ENUMERATED can be written to an Enumerated.

An ASN.1 UTCTIME or GENERALIZEDTIME can be written to a time.Time.

An ASN.1 PrintableString, IA5String, or NumericString can be written to
a string.

Any of the above ASN.1 values can be written to an interface{}. The
value stored in the interface has the corresponding Go type. For
integers, that type is int64.

An ASN.1 SEQUENCE OF x or SET OF x can be written to a slice if an x can
be written to the slice\'s element type.

An ASN.1 SEQUENCE or SET can be written to a struct if each of the
elements in the sequence can be written to the corresponding element in
the struct.

The following tags on struct fields have special meaning to Unmarshal:

```go
application specifies that an APPLICATION tag is used
private     specifies that a PRIVATE tag is used
default:x   sets the default value for optional integer fields (only used if optional is also present)
explicit    specifies that an additional, explicit tag wraps the implicit one
optional    marks the field as ASN.1 OPTIONAL
set         causes a SET, rather than a SEQUENCE type to be expected
tag:x       specifies the ASN.1 tag number; implies ASN.1 CONTEXT SPECIFIC
```

When decoding an ASN.1 value with an IMPLICIT tag into a string field,
Unmarshal will default to a PrintableString, which doesn\'t support
characters such as \'@\' and \'&\'. To force other encodings, use the
following tags:

```go
ia5     causes strings to be unmarshaled as ASN.1 IA5String values
numeric causes strings to be unmarshaled as ASN.1 NumericString values
utf8    causes strings to be unmarshaled as ASN.1 UTF8String values
```

If the type of the first field of a structure is RawContent then the raw
ASN1 contents of the struct will be stored in it.

If the name of a slice type ends with \"SET\" then it\'s treated as if
the \"set\" tag was set on it. This results in interpreting the type as
a SET OF x rather than a SEQUENCE OF x. This can be used with nested
slices where a struct tag cannot be given.

Other ASN.1 types are not supported; if it encounters them, Unmarshal
returns a parse error.

func UnmarshalWithParams 
------------------------

```go
func UnmarshalWithParams(b []byte, val any, params string) (rest []byte, err error)
```

UnmarshalWithParams allows field parameters to be specified for the
top-level element. The form of the params is the same as the field tags.

type BitString 
--------------

BitString is the structure to use when you want an ASN.1 BIT STRING
type. A bit string is padded up to the nearest byte in memory and the
number of valid bits is recorded. Padding bits will be zero.

```go
type BitString struct {
    Bytes     []byte // bits packed into bytes.
    BitLength int    // length in bits.
}
```

### func (BitString) At 

```go
func (b BitString) At(i int) int
```

At returns the bit at the given index. If the index is out of range it
returns 0.

### func (BitString) RightAlign 

```go
func (b BitString) RightAlign() []byte
```

RightAlign returns a slice where the padding bits are at the beginning.
The slice may share memory with the BitString.

type Enumerated 
---------------

An Enumerated is represented as a plain int.

```go
type Enumerated int
```

type Flag 
---------

A Flag accepts any data and is set to true if present.

```go
type Flag bool
```

type ObjectIdentifier 
---------------------

An ObjectIdentifier represents an ASN.1 OBJECT IDENTIFIER.

```go
type ObjectIdentifier []int
```

### func (ObjectIdentifier) Equal 

```go
func (oi ObjectIdentifier) Equal(other ObjectIdentifier) bool
```

Equal reports whether oi and other represent the same identifier.

### func (ObjectIdentifier) String 

```go
func (oi ObjectIdentifier) String() string
```

type RawContent 
---------------

RawContent is used to signal that the undecoded, DER data needs to be
preserved for a struct. To use it, the first field of the struct must
have this type. It\'s an error for any of the other fields to have this
type.

```go
type RawContent []byte
```

type RawValue 
-------------

A RawValue represents an undecoded ASN.1 object.

```go
type RawValue struct {
    Class, Tag int
    IsCompound bool
    Bytes      []byte
    FullBytes  []byte // includes the tag and length
}
```

type StructuralError 
--------------------

A StructuralError suggests that the ASN.1 data is valid, but the Go type
which is receiving it doesn\'t match.

```go
type StructuralError struct {
    Msg string
}
```

### func (StructuralError) Error 

```go
func (e StructuralError) Error() string
```

type SyntaxError 
----------------

A SyntaxError suggests that the ASN.1 data is invalid.

```go
type SyntaxError struct {
    Msg string
}
```

### func (SyntaxError) Error 

```go
func (e SyntaxError) Error() string
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/encoding/asn1/>

