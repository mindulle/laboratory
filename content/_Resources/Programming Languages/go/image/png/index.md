Package png
===========

-   `import "image/png"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package png implements a PNG image decoder and encoder.

The PNG specification is at https://www.w3.org/TR/PNG/>.

Index 
-----

-   [func Decode(r io.Reader) (image.Image, error)](#Decode)
-   [func DecodeConfig(r io.Reader) (image.Config,
    error)](#DecodeConfig)
-   [func Encode(w io.Writer, m image.Image) error](#Encode)
-   [type CompressionLevel](#CompressionLevel)
-   [type Encoder](#Encoder)
-   [func (enc \*Encoder) Encode(w io.Writer, m image.Image)
    error](#Encoder.Encode)
-   [type EncoderBuffer](#EncoderBuffer)
-   [type EncoderBufferPool](#EncoderBufferPool)
-   [type FormatError](#FormatError)
-   [func (e FormatError) Error() string](#FormatError.Error)
-   [type UnsupportedError](#UnsupportedError)
-   [func (e UnsupportedError) Error() string](#UnsupportedError.Error)

 
### Examples

[Decode](#example_Decode)

[Encode](#example_Encode)


### Package files

paeth.go reader.go writer.go

func Decode 
-----------

```go
func Decode(r io.Reader) (image.Image, error)
```

Decode reads a PNG image from r and returns it as an image.Image. The
type of Image returned depends on the PNG contents.

#### [Example]

Code:

```go
// This example uses png.Decode which can only decode PNG images.
// Consider using the general image.Decode as it can sniff and decode any registered image format.
img, err := png.Decode(gopherPNG())
if err != nil {
    log.Fatal(err)
}

levels := []string{" ", "░", "▒", "▓", "█"}

for y := img.Bounds().Min.Y; y < img.Bounds().Max.Y; y++ {
    for x := img.Bounds().Min.X; x < img.Bounds().Max.X; x++ {
        c := color.GrayModel.Convert(img.At(x, y)).(color.Gray)
        level := c.Y / 51 // 51 * 5 = 255
        if level == 5 {
            level--
        }
        fmt.Print(levels[level])
    }
    fmt.Print("\n")
}
```

func DecodeConfig 
-----------------

```go
func DecodeConfig(r io.Reader) (image.Config, error)
```

DecodeConfig returns the color model and dimensions of a PNG image
without decoding the entire image.

func Encode 
-----------

```go
func Encode(w io.Writer, m image.Image) error
```

Encode writes the Image m to w in PNG format. Any Image may be encoded,
but images that are not image.NRGBA might be encoded lossily.

#### [Example]

Code:

```go
const width, height = 256, 256

// Create a colored image of the given width and height.
img := image.NewNRGBA(image.Rect(0, 0, width, height))

for y := 0; y < height; y++ {
    for x := 0; x < width; x++ {
        img.Set(x, y, color.NRGBA{
            R: uint8((x + y) & 255),
            G: uint8((x + y) << 1 & 255),
            B: uint8((x + y) << 2 & 255),
            A: 255,
        })
    }
}

f, err := os.Create("image.png")
if err != nil {
    log.Fatal(err)
}

if err := png.Encode(f, img); err != nil {
    f.Close()
    log.Fatal(err)
}

if err := f.Close(); err != nil {
    log.Fatal(err)
}
```

type CompressionLevel 
----------------------------------------------------

CompressionLevel indicates the compression level.

```go
type CompressionLevel int
```

```go
const (
    DefaultCompression CompressionLevel = 0
    NoCompression      CompressionLevel = -1
    BestSpeed          CompressionLevel = -2
    BestCompression    CompressionLevel = -3
)
```

type Encoder 
-------------------------------------------

Encoder configures encoding PNG images.

```go
type Encoder struct {
    CompressionLevel CompressionLevel

    // BufferPool optionally specifies a buffer pool to get temporary
    // EncoderBuffers when encoding an image.
    BufferPool EncoderBufferPool // Go 1.9
}
```

### func (\*Encoder) Encode 

```go
func (enc *Encoder) Encode(w io.Writer, m image.Image) error
```

Encode writes the Image m to w in PNG format.

type EncoderBuffer 
-------------------------------------------------

EncoderBuffer holds the buffers used for encoding PNG images.

```go
type EncoderBuffer encoder
```

type EncoderBufferPool 
-----------------------------------------------------

EncoderBufferPool is an interface for getting and returning temporary
instances of the EncoderBuffer struct. This can be used to reuse buffers
when encoding multiple images.

```go
type EncoderBufferPool interface {
    Get() *EncoderBuffer
    Put(*EncoderBuffer)
}
```

type FormatError 
----------------

A FormatError reports that the input is not a valid PNG.

```go
type FormatError string
```

### func (FormatError) Error 

```go
func (e FormatError) Error() string
```

type UnsupportedError 
---------------------

An UnsupportedError reports that the input uses a valid but
unimplemented PNG feature.

```go
type UnsupportedError string
```

### func (UnsupportedError) Error 

```go
func (e UnsupportedError) Error() string
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/image/png/>

