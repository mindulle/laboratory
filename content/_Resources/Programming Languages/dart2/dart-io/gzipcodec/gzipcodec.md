[dart:io](../../dart-io/dart-io-library){._links-link}

GZipCodec constructor
=====================

::: {.section .multi-line-signature}
GZipCodec(

1.  {[int](../../dart-core/int-class) level = ZLibOption.defaultLevel,
2.  [int](../../dart-core/int-class) windowBits =
    ZLibOption.defaultWindowBits,
3.  [int](../../dart-core/int-class) memLevel =
    ZLibOption.defaultMemLevel,
4.  [int](../../dart-core/int-class) strategy =
    ZLibOption.strategyDefault,
5.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>?
    dictionary,
6.  [bool](../../dart-core/bool-class) raw = false,
7.  [bool](../../dart-core/bool-class) gzip = true}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
GZipCodec(
    {this.level = ZLibOption.defaultLevel,
    this.windowBits = ZLibOption.defaultWindowBits,
    this.memLevel = ZLibOption.defaultMemLevel,
    this.strategy = ZLibOption.strategyDefault,
    this.dictionary,
    this.raw = false,
    this.gzip = true}) {
  _validateZLibeLevel(level);
  _validateZLibMemLevel(memLevel);
  _validateZLibStrategy(strategy);
  _validateZLibWindowBits(windowBits);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/GZipCodec/GZipCodec.html>
:::
