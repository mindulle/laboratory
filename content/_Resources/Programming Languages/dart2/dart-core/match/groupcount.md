[dart:core](../../dart-core/dart-core-library){._links-link}

groupCount property
===================

::: {#getter .section .multi-line-signature}
[int](../int-class) groupCount
:::

Returns the number of captured groups in the match.

Some patterns may capture parts of the input that was used to compute
the full match. This is the number of captured groups, which is also the
maximal allowed argument to the [group](group) method.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get groupCount;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Match/groupCount.html>
:::
