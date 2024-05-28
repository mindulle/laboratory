[dart:io](../../dart-io/dart-io-library){._links-link}

ZLibDecoder constructor
=======================

::: {.section .multi-line-signature}
ZLibDecoder(

1.  {[int](../../dart-core/int-class) windowBits =
    ZLibOption.defaultWindowBits,
2.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>?
    dictionary,
3.  [bool](../../dart-core/bool-class) raw = false}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ZLibDecoder(
    {this.windowBits = ZLibOption.defaultWindowBits,
    this.dictionary,
    this.raw = false}) {
  _validateZLibWindowBits(windowBits);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ZLibDecoder/ZLibDecoder.html>
:::
