[dart:io](../../dart-io/dart-io-library){._links-link}

encode method
=============

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
encode(

1.  [String](../../dart-core/string-class) input

)

::: {.features}
override
:::
:::

Encodes `input`.

The input is encoded as if by `encoder.convert`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<int> encode(String input) => encoder.convert(input);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SystemEncoding/encode.html>
:::
