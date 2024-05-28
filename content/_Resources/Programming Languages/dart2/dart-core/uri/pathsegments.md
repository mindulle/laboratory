[dart:core](../../dart-core/dart-core-library){._links-link}

pathSegments property
=====================

::: {#getter .section .multi-line-signature}
[List](../list-class)\<[String](../string-class)\> pathSegments
:::

The URI path split into its segments.

Each of the segments in the list has been decoded. If the path is empty,
the empty list will be returned. A leading slash `/` does not affect the
segments returned.

The list is unmodifiable and will throw
[UnsupportedError](../unsupportederror-class) on any calls that would
mutate it.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<String> get pathSegments;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/pathSegments.html>
:::
