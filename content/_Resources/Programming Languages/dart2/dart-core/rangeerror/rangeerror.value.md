[dart:core](../../dart-core/dart-core-library){._links-link}

RangeError.value constructor
============================

::: {.section .multi-line-signature}
RangeError.value(

1.  [num](../num-class) value,
2.  \[[String](../string-class)? name,
3.  [String](../string-class)? message\]

)
:::

Create a new [RangeError](../rangeerror-class) with a message for the
given `value`.

An optional `name` can specify the argument name that has the invalid
value, and the `message` can override the default error description.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
RangeError.value(num value, [String? name, String? message])
    : start = null,
      end = null,
      super.value(value, name, message ?? "Value not in range");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RangeError/RangeError.value.html>
:::
