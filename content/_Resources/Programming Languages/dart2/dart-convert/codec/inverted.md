[dart:convert](../../dart-convert/dart-convert-library){._links-link}

inverted property
=================

::: {#getter .section .multi-line-signature}
[Codec](../codec-class)\<T, S\> inverted
:::

Inverts `this`.

The [encoder](encoder) and [decoder](decoder) of the resulting codec are
swapped.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Codec<T, S> get inverted => _InvertedCodec<T, S>(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Codec/inverted.html>
:::
