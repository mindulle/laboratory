[dart:convert](../../dart-convert/dart-convert-library){._links-link}

JsonDecoder constructor
=======================

::: {.section .multi-line-signature}
const JsonDecoder(

1.  \[[Object](../../dart-core/object-class)? reviver(
    1.  [Object](../../dart-core/object-class)? key,
    2.  [Object](../../dart-core/object-class)? value

    )?\]

)
:::

Constructs a new JsonDecoder.

The `reviver` may be `null`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const JsonDecoder([Object? reviver(Object? key, Object? value)?])
    : _reviver = reviver;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonDecoder/JsonDecoder.html>
:::
