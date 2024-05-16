Package bzip2
=============

-   `import "compress/bzip2"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package bzip2 implements bzip2 decompression.

Index 
-----

-   [func NewReader(r io.Reader) io.Reader](#NewReader)
-   [type StructuralError](#StructuralError)
-   [func (s StructuralError) Error() string](#StructuralError.Error)

### Package files

bit\_reader.go bzip2.go huffman.go move\_to\_front.go

func NewReader 
--------------

```go
func NewReader(r io.Reader) io.Reader
```

NewReader returns an io.Reader which decompresses bzip2 data from r. If
r does not also implement io.ByteReader, the decompressor may read more
data than necessary from r.

type StructuralError 
--------------------

A StructuralError is returned when the bzip2 data is found to be
syntactically invalid.

```go
type StructuralError string
```

### func (StructuralError) Error 

```go
func (s StructuralError) Error() string
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/compress/bzip2/>

