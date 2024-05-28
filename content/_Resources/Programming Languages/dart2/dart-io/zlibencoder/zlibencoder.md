[dart:io](../../dart-io/dart-io-library){._links-link}

ZLibEncoder constructor
=======================

::: {.section .multi-line-signature}
ZLibEncoder(

1.  {[bool](../../dart-core/bool-class) gzip = false,
2.  [int](../../dart-core/int-class) level = ZLibOption.defaultLevel,
3.  [int](../../dart-core/int-class) windowBits =
    ZLibOption.defaultWindowBits,
4.  [int](../../dart-core/int-class) memLevel =
    ZLibOption.defaultMemLevel,
5.  [int](../../dart-core/int-class) strategy =
    ZLibOption.strategyDefault,
6.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>?
    dictionary,
7.  [bool](../../dart-core/bool-class) raw = false}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ZLibEncoder(
    {this.gzip = false,
    this.level = ZLibOption.defaultLevel,
    this.windowBits = ZLibOption.defaultWindowBits,
    this.memLevel = ZLibOption.defaultMemLevel,
    this.strategy = ZLibOption.strategyDefault,
    this.dictionary,
    this.raw = false}) {
  _validateZLibeLevel(level);
  _validateZLibMemLevel(memLevel);
  _validateZLibStrategy(strategy);
  _validateZLibWindowBits(windowBits);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ZLibEncoder/ZLibEncoder.html>
:::
