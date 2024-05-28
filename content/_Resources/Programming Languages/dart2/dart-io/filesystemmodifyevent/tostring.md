[dart:io](../../dart-io/dart-io-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) toString()

::: {.features}
override
:::
:::

A string representation of this object.

Some classes have a default textual representation, often paired with a
static `parse` function (like [int.parse](../../dart-core/int/parse)).
These classes will provide the textual representation as their string
representation.

Other classes have no meaningful textual representation that a program
will care about. Such classes will typically override `toString` to
provide useful information when inspecting the object, mainly for
debugging or logging.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString() =>
    "FileSystemModifyEvent('$path', contentChanged=$contentChanged)";
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemModifyEvent/toString.html>
:::
