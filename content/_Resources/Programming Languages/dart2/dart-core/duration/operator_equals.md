[dart:core](../../dart-core/dart-core-library){._links-link}

operator == method
==================

::: {.section .multi-line-signature}
[bool](../bool-class) operator ==(

1.  [Object](../object-class) other

)

::: {.features}
override
:::
:::

Whether this [Duration](../duration-class) has the same length as
`other`.

Durations have the same length if they have the same number of
microseconds, as reported by [inMicroseconds](inmicroseconds).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool operator ==(Object other) =>
    other is Duration && _duration == other.inMicroseconds;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/operator_equals.html>
:::
