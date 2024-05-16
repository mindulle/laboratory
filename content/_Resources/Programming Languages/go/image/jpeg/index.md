Package jpeg
============

-   `import "image/jpeg"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package jpeg implements a JPEG image decoder and encoder.

JPEG is defined in ITU-T T.81:
https://www.w3.org/Graphics/JPEG/itu-t81.pdf>.

Index 
-----

-   [Constants](#pkg-constants)
-   [func Decode(r io.Reader) (image.Image, error)](#Decode)
-   [func DecodeConfig(r io.Reader) (image.Config,
    error)](#DecodeConfig)
-   [func Encode(w io.Writer, m image.Image, o \*Options)
    error](#Encode)
-   [type FormatError](#FormatError)
-   [func (e FormatError) Error() string](#FormatError.Error)
-   [type Options](#Options)
-   [type Reader](#Reader)
-   [type UnsupportedError](#UnsupportedError)
-   [func (e UnsupportedError) Error() string](#UnsupportedError.Error)

### Package files

fdct.go huffman.go idct.go reader.go scan.go writer.go

Constants 
---------

DefaultQuality is the default quality encoding parameter.

```go
const DefaultQuality = 75
```

func Decode 
-----------

```go
func Decode(r io.Reader) (image.Image, error)
```

Decode reads a JPEG image from r and returns it as an image.Image.

func DecodeConfig 
-----------------

```go
func DecodeConfig(r io.Reader) (image.Config, error)
```

DecodeConfig returns the color model and dimensions of a JPEG image
without decoding the entire image.

func Encode 
-----------

```go
func Encode(w io.Writer, m image.Image, o *Options) error
```

Encode writes the Image m to w in JPEG 4:2:0 baseline format with the
given options. Default parameters are used if a nil \*Options is passed.

type FormatError 
----------------

A FormatError reports that the input is not a valid JPEG.

```go
type FormatError string
```

### func (FormatError) Error 

```go
func (e FormatError) Error() string
```

type Options 
------------

Options are the encoding parameters. Quality ranges from 1 to 100
inclusive, higher is better.

```go
type Options struct {
    Quality int
}
```

type Reader 
-----------

Deprecated: Reader is not used by the image/jpeg package and should not
be used by others. It is kept for compatibility.

```go
type Reader interface {
    io.ByteReader
    io.Reader
}
```

type UnsupportedError 
---------------------

An UnsupportedError reports that the input uses a valid but
unimplemented JPEG feature.

```go
type UnsupportedError string
```

### func (UnsupportedError) Error 

```go
func (e UnsupportedError) Error() string
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/image/jpeg/>

