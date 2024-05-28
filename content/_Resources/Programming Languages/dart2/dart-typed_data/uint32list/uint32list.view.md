[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

Uint32List.view constructor
===========================

::: {.section .multi-line-signature}
Uint32List.view(

1.  [ByteBuffer](../bytebuffer-class) buffer,
2.  \[[int](../../dart-core/int-class) offsetInBytes = 0,
3.  [int](../../dart-core/int-class)? length\]

)
:::

Creates a [Uint32List](../uint32list-class) *view* of the specified
region in the specified byte buffer.

Changes in the [Uint32List](../uint32list-class) will be visible in the
byte buffer and vice versa. If the `offsetInBytes` index of the region
is not specified, it defaults to zero (the first byte in the byte
buffer). If the length is not provided, the view extends to the end of
the byte buffer.

The `offsetInBytes` and `length` must be non-negative, and
`offsetInBytes` + (`length` \*
[bytesPerElement](bytesperelement-constant)) must be less than or equal
to the length of `buffer`.

The `offsetInBytes` must be a multiple of
[bytesPerElement](bytesperelement-constant).

Note that when creating a view from a [TypedData](../typeddata-class)
list or byte data, that list or byte data may itself be a view on a
larger buffer with a
[TypedData.offsetInBytes](../typeddata/offsetinbytes) greater than zero.
Merely doing `Uint32List.view(other.buffer, 0, count)` may not point to
the bytes you intended. Instead you may need to do:

``` {.language-dart data-language="dart"}
Uint32List.view(other.buffer, other.offsetInBytes, count)
```

Alternatively, use [Uint32List.sublistView](uint32list.sublistview)
which includes this computation:

``` {.language-dart data-language="dart"}
Uint32List.sublistView(other, 0, count);
```

(The third argument is an end index rather than a length, so if you
start from a position greater than zero, you need not reduce the count
correspondingly).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Uint32List.view(ByteBuffer buffer,
    [int offsetInBytes = 0, int? length]) {
  return buffer.asUint32List(offsetInBytes, length);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Uint32List/Uint32List.view.html>
:::
