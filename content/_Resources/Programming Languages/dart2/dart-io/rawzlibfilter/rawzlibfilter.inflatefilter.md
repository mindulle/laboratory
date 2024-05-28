[dart:io](../../dart-io/dart-io-library){._links-link}

RawZLibFilter.inflateFilter constructor
=======================================

::: {.section .multi-line-signature}
RawZLibFilter.inflateFilter(

1.  {[int](../../dart-core/int-class) windowBits =
    ZLibOption.defaultWindowBits,
2.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>?
    dictionary,
3.  [bool](../../dart-core/bool-class) raw = false}

)
:::

Returns a a [RawZLibFilter](../rawzlibfilter-class) whose
[process](process) and [processed](processed) methods decompress data.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory RawZLibFilter.inflateFilter({
  int windowBits = ZLibOption.defaultWindowBits,
  List<int>? dictionary,
  bool raw = false,
}) {
  return _makeZLibInflateFilter(windowBits, dictionary, raw);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawZLibFilter/RawZLibFilter.inflateFilter.html>
:::
