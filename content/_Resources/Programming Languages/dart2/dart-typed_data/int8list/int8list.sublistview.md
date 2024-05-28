[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

Int8List.sublistView constructor
================================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.8\")

</div>

Int8List.sublistView(

1.  [TypedData](../typeddata-class) data,
2.  \[[int](../../dart-core/int-class) start = 0,
3.  [int](../../dart-core/int-class)? end\]

)
:::

Creates an [Int8List](../int8list-class) view on a range of elements of
`data`.

Creates a view on the range of `data.buffer` which corresponds to the
elements of `data` from `start` until `end`. If `data` is a typed data
list, like [Uint16List](../uint16list-class), then the view is on the
bytes of the elements with indices from `start` until `end`. If `data`
is a [ByteData](../bytedata-class), it\'s treated like a list of bytes.

If provided, `start` and `end` must satisfy

0 ≤ `start` ≤ `end` ≤ *elementCount*

where *elementCount* is the number of elements in `data`, which is the
same as the [List.length](../../dart-core/list/length) of a typed data
list.

If omitted, `start` defaults to zero and `end` to *elementCount*.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.8")
factory Int8List.sublistView(TypedData data, [int start = 0, int? end]) {
  int elementSize = data.elementSizeInBytes;
  end = RangeError.checkValidRange(
      start, end, data.lengthInBytes ~/ elementSize);
  return data.buffer.asInt8List(
      data.offsetInBytes + start * elementSize, (end - start) * elementSize);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Int8List/Int8List.sublistView.html>
:::
