[dart:core](../../dart-core/dart-core-library){._links-link}

offset property
===============

::: {.section .multi-line-signature}
[int](../int-class)? offset

::: {.features}
final
:::
:::

The offset in [source](source) where the error was detected.

A zero-based offset into the source that marks the format error causing
this exception to be created. If `source` is a string, this should be a
string index in the range `0 <= offset <= source.length`.

If input is a string, the [toString](tostring) method may represent this
offset as a line and character position. The offset should be inside the
string, or at the end of the string.

May be omitted. If present, [source](source) should also be present if
possible.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final int? offset;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/FormatException/offset.html>
:::
