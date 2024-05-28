[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

BytesBuilder constructor
========================

::: {.section .multi-line-signature}
BytesBuilder(

1.  {[bool](../../dart-core/bool-class) copy = true}

)
:::

Construct a new empty [BytesBuilder](../bytesbuilder-class).

If `copy` is true (the default), the created builder is a *copying*
builder. A copying builder maintains its own internal buffer and copies
the bytes added to it eagerly.

If `copy` set to false, the created builder assumes that lists added to
it will not change. Any [Uint8List](../uint8list-class) added using
[add](add) is kept until [toBytes](tobytes) or [takeBytes](takebytes) is
called, and only then are their contents copied. A
non-[Uint8List](../uint8list-class) may be copied eagerly. If only a
single [Uint8List](../uint8list-class) is added to the builder, that
list is returned by [toBytes](tobytes) or [takeBytes](takebytes)
directly, without any copying. A list added to a non-copying builder
*should not* change its content after being added, and it *must not*
change its length after being added. (Normal
[Uint8List](../uint8list-class)s are fixed length lists, but growing
lists implementing [Uint8List](../uint8list-class) exist.)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory BytesBuilder({bool copy = true}) =>
    copy ? _CopyingBytesBuilder() : _BytesBuilder();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/BytesBuilder/BytesBuilder.html>
:::
