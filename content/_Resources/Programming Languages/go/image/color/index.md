Package color
=============

-   `import "image/color"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Subdirectories](#pkg-subdirectories)

Overview 
--------

Package color implements a basic color library.

Index 
-----

-   [Variables](#pkg-variables)
-   [func CMYKToRGB(c, m, y, k uint8) (uint8, uint8, uint8)](#CMYKToRGB)
-   [func RGBToCMYK(r, g, b uint8) (uint8, uint8, uint8,
    uint8)](#RGBToCMYK)
-   [func RGBToYCbCr(r, g, b uint8) (uint8, uint8, uint8)](#RGBToYCbCr)
-   [func YCbCrToRGB(y, cb, cr uint8) (uint8, uint8,
    uint8)](#YCbCrToRGB)
-   [type Alpha](#Alpha)
-   [func (c Alpha) RGBA() (r, g, b, a uint32)](#Alpha.RGBA)
-   [type Alpha16](#Alpha16)
-   [func (c Alpha16) RGBA() (r, g, b, a uint32)](#Alpha16.RGBA)
-   [type CMYK](#CMYK)
-   [func (c CMYK) RGBA() (uint32, uint32, uint32, uint32)](#CMYK.RGBA)
-   [type Color](#Color)
-   [type Gray](#Gray)
-   [func (c Gray) RGBA() (r, g, b, a uint32)](#Gray.RGBA)
-   [type Gray16](#Gray16)
-   [func (c Gray16) RGBA() (r, g, b, a uint32)](#Gray16.RGBA)
-   [type Model](#Model)
-   [func ModelFunc(f func(Color) Color) Model](#ModelFunc)
-   [type NRGBA](#NRGBA)
-   [func (c NRGBA) RGBA() (r, g, b, a uint32)](#NRGBA.RGBA)
-   [type NRGBA64](#NRGBA64)
-   [func (c NRGBA64) RGBA() (r, g, b, a uint32)](#NRGBA64.RGBA)
-   [type NYCbCrA](#NYCbCrA)
-   [func (c NYCbCrA) RGBA() (uint32, uint32, uint32,
    uint32)](#NYCbCrA.RGBA)
-   [type Palette](#Palette)
-   [func (p Palette) Convert(c Color) Color](#Palette.Convert)
-   [func (p Palette) Index(c Color) int](#Palette.Index)
-   [type RGBA](#RGBA)
-   [func (c RGBA) RGBA() (r, g, b, a uint32)](#RGBA.RGBA)
-   [type RGBA64](#RGBA64)
-   [func (c RGBA64) RGBA() (r, g, b, a uint32)](#RGBA64.RGBA)
-   [type YCbCr](#YCbCr)
-   [func (c YCbCr) RGBA() (uint32, uint32, uint32,
    uint32)](#YCbCr.RGBA)

### Package files

color.go ycbcr.go

Variables 
---------

Standard colors.

```go
var (
    Black       = Gray16{0}
    White       = Gray16{0xffff}
    Transparent = Alpha16{0}
    Opaque      = Alpha16{0xffff}
)
```

func CMYKToRGB 
---------------------------------------------

```go
func CMYKToRGB(c, m, y, k uint8) (uint8, uint8, uint8)
```

CMYKToRGB converts a CMYK quadruple to an RGB triple.

func RGBToCMYK 
---------------------------------------------

```go
func RGBToCMYK(r, g, b uint8) (uint8, uint8, uint8, uint8)
```

RGBToCMYK converts an RGB triple to a CMYK quadruple.

func RGBToYCbCr 
---------------

```go
func RGBToYCbCr(r, g, b uint8) (uint8, uint8, uint8)
```

RGBToYCbCr converts an RGB triple to a Y\'CbCr triple.

func YCbCrToRGB 
---------------

```go
func YCbCrToRGB(y, cb, cr uint8) (uint8, uint8, uint8)
```

YCbCrToRGB converts a Y\'CbCr triple to an RGB triple.

type Alpha 
----------

Alpha represents an 8-bit alpha color.

```go
type Alpha struct {
    A uint8
}
```

### func (Alpha) RGBA 

```go
func (c Alpha) RGBA() (r, g, b, a uint32)
```

type Alpha16 
------------

Alpha16 represents a 16-bit alpha color.

```go
type Alpha16 struct {
    A uint16
}
```

### func (Alpha16) RGBA 

```go
func (c Alpha16) RGBA() (r, g, b, a uint32)
```

type CMYK 
----------------------------------------

CMYK represents a fully opaque CMYK color, having 8 bits for each of
cyan, magenta, yellow and black.

It is not associated with any particular color profile.

```go
type CMYK struct {
    C, M, Y, K uint8
}
```

### func (CMYK) RGBA 

```go
func (c CMYK) RGBA() (uint32, uint32, uint32, uint32)
```

type Color 
----------

Color can convert itself to alpha-premultiplied 16-bits per channel
RGBA. The conversion may be lossy.

```go
type Color interface {
    // RGBA returns the alpha-premultiplied red, green, blue and alpha values
    // for the color. Each value ranges within [0, 0xffff], but is represented
    // by a uint32 so that multiplying by a blend factor up to 0xffff will not
    // overflow.
    //
    // An alpha-premultiplied color component c has been scaled by alpha (a),
    // so has valid values 0 <= c <= a.
    RGBA() (r, g, b, a uint32)
}
```

type Gray 
---------

Gray represents an 8-bit grayscale color.

```go
type Gray struct {
    Y uint8
}
```

### func (Gray) RGBA 

```go
func (c Gray) RGBA() (r, g, b, a uint32)
```

type Gray16 
-----------

Gray16 represents a 16-bit grayscale color.

```go
type Gray16 struct {
    Y uint16
}
```

### func (Gray16) RGBA 

```go
func (c Gray16) RGBA() (r, g, b, a uint32)
```

type Model 
----------

Model can convert any Color to one from its own color model. The
conversion may be lossy.

```go
type Model interface {
    Convert(c Color) Color
}
```

Models for the standard color types.

```go
var (
    RGBAModel    Model = ModelFunc(rgbaModel)
    RGBA64Model  Model = ModelFunc(rgba64Model)
    NRGBAModel   Model = ModelFunc(nrgbaModel)
    NRGBA64Model Model = ModelFunc(nrgba64Model)
    AlphaModel   Model = ModelFunc(alphaModel)
    Alpha16Model Model = ModelFunc(alpha16Model)
    GrayModel    Model = ModelFunc(grayModel)
    Gray16Model  Model = ModelFunc(gray16Model)
)
```

CMYKModel is the Model for CMYK colors.

```go
var CMYKModel Model = ModelFunc(cmykModel)
```

NYCbCrAModel is the Model for non-alpha-premultiplied Y\'CbCr-with-alpha
colors.

```go
var NYCbCrAModel Model = ModelFunc(nYCbCrAModel)
```

YCbCrModel is the Model for Y\'CbCr colors.

```go
var YCbCrModel Model = ModelFunc(yCbCrModel)
```

### func ModelFunc 

```go
func ModelFunc(f func(Color) Color) Model
```

ModelFunc returns a Model that invokes f to implement the conversion.

type NRGBA 
----------

NRGBA represents a non-alpha-premultiplied 32-bit color.

```go
type NRGBA struct {
    R, G, B, A uint8
}
```

### func (NRGBA) RGBA 

```go
func (c NRGBA) RGBA() (r, g, b, a uint32)
```

type NRGBA64 
------------

NRGBA64 represents a non-alpha-premultiplied 64-bit color, having 16
bits for each of red, green, blue and alpha.

```go
type NRGBA64 struct {
    R, G, B, A uint16
}
```

### func (NRGBA64) RGBA 

```go
func (c NRGBA64) RGBA() (r, g, b, a uint32)
```

type NYCbCrA 
-------------------------------------------

NYCbCrA represents a non-alpha-premultiplied Y\'CbCr-with-alpha color,
having 8 bits each for one luma, two chroma and one alpha component.

```go
type NYCbCrA struct {
    YCbCr
    A uint8
}
```

### func (NYCbCrA) RGBA 

```go
func (c NYCbCrA) RGBA() (uint32, uint32, uint32, uint32)
```

type Palette 
------------

Palette is a palette of colors.

```go
type Palette []Color
```

### func (Palette) Convert 

```go
func (p Palette) Convert(c Color) Color
```

Convert returns the palette color closest to c in Euclidean R,G,B space.

### func (Palette) Index 

```go
func (p Palette) Index(c Color) int
```

Index returns the index of the palette color closest to c in Euclidean
R,G,B,A space.

type RGBA 
---------

RGBA represents a traditional 32-bit alpha-premultiplied color, having 8
bits for each of red, green, blue and alpha.

An alpha-premultiplied color component C has been scaled by alpha (A),
so has valid values 0 \<= C \<= A.

```go
type RGBA struct {
    R, G, B, A uint8
}
```

### func (RGBA) RGBA 

```go
func (c RGBA) RGBA() (r, g, b, a uint32)
```

type RGBA64 
-----------

RGBA64 represents a 64-bit alpha-premultiplied color, having 16 bits for
each of red, green, blue and alpha.

An alpha-premultiplied color component C has been scaled by alpha (A),
so has valid values 0 \<= C \<= A.

```go
type RGBA64 struct {
    R, G, B, A uint16
}
```

### func (RGBA64) RGBA 

```go
func (c RGBA64) RGBA() (r, g, b, a uint32)
```

type YCbCr 
----------

YCbCr represents a fully opaque 24-bit Y\'CbCr color, having 8 bits each
for one luma and two chroma components.

JPEG, VP8, the MPEG family and other codecs use this color model. Such
codecs often use the terms YUV and Y\'CbCr interchangeably, but strictly
speaking, the term YUV applies only to analog video signals, and Y\'
(luma) is Y (luminance) after applying gamma correction.

Conversion between RGB and Y\'CbCr is lossy and there are multiple,
slightly different formulae for converting between the two. This package
follows the JFIF specification at
https://www.w3.org/Graphics/JPEG/jfif3.pdf>.

```go
type YCbCr struct {
    Y, Cb, Cr uint8
}
```

### func (YCbCr) RGBA 

```go
func (c YCbCr) RGBA() (uint32, uint32, uint32, uint32)
```

Subdirectories 
--------------

 
Name


Synopsis

[..](../index)

[palette](palette/index)

Package palette provides standard color palettes.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/image/color/>

