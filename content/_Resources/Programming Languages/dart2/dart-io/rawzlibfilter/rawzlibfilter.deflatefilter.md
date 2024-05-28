[dart:io](../../dart-io/dart-io-library){._links-link}

RawZLibFilter.deflateFilter constructor
=======================================

::: {.section .multi-line-signature}
RawZLibFilter.deflateFilter(

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

Returns a a [RawZLibFilter](../rawzlibfilter-class) whose
[process](process) and [processed](processed) methods compress data.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory RawZLibFilter.deflateFilter({
  bool gzip = false,
  int level = ZLibOption.defaultLevel,
  int windowBits = ZLibOption.defaultWindowBits,
  int memLevel = ZLibOption.defaultMemLevel,
  int strategy = ZLibOption.strategyDefault,
  List<int>? dictionary,
  bool raw = false,
}) {
  return _makeZLibDeflateFilter(
      gzip, level, windowBits, memLevel, strategy, dictionary, raw);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawZLibFilter/RawZLibFilter.deflateFilter.html>
:::
