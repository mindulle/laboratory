[dart:convert](../../dart-convert/dart-convert-library){._links-link}

fuse\<R\> method
================

::: {.section .multi-line-signature}
[Codec](../codec-class)\<S, R\> fuse\<R\>(

1.  [Codec](../codec-class)\<T, R\> other

)
:::

Fuses `this` with `other`.

When encoding, the resulting codec encodes with `this` before encoding
with `other`.

When decoding, the resulting codec decodes with `other` before decoding
with `this`.

In some cases one needs to use the [inverted](inverted) codecs to be
able to fuse them correctly. That is, the output type of `this` (`T`)
must match the input type of the second codec `other`.

Examples:

``` {.language-dart data-language="dart"}
final jsonToBytes = json.fuse(utf8);
List<int> bytes = jsonToBytes.encode(["json-object"]);
var decoded = jsonToBytes.decode(bytes);
assert(decoded is List && decoded[0] == "json-object");

var inverted = json.inverted;
var jsonIdentity = json.fuse(inverted);
var jsonObject = jsonIdentity.encode(["1", 2]);
assert(jsonObject is List && jsonObject[0] == "1" && jsonObject[1] == 2);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// TODO(floitsch): use better example with line-splitter once that one is
// in this library.
Codec<S, R> fuse<R>(Codec<T, R> other) {
  return _FusedCodec<S, T, R>(this, other);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Codec/fuse.html>
:::
