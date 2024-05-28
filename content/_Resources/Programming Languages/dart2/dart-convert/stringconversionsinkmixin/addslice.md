[dart:convert](../../dart-convert/dart-convert-library){._links-link}

addSlice method
===============

::: {.section .multi-line-signature}
void addSlice(

1.  [String](../../dart-core/string-class) str,
2.  [int](../../dart-core/int-class) start,
3.  [int](../../dart-core/int-class) end,
4.  [bool](../../dart-core/bool-class) isLast

)

::: {.features}
override
:::
:::

Adds the next `chunk` to `this`.

Adds the substring defined by `start` and `end`-exclusive to `this`.

If `isLast` is `true` closes `this`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addSlice(String str, int start, int end, bool isLast);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/StringConversionSinkMixin/addSlice.html>
:::
