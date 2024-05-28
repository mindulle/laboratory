[dart:io](../../dart-io/dart-io-library){._links-link}

encoding property
=================

::: {#getter .section .multi-line-signature}
[Encoding](../../dart-convert/encoding-class) encoding

::: {.features}
inherited
:::
:::

The [Encoding](../../dart-convert/encoding-class) used when writing
strings.

Depending on the underlying consumer, this property might be mutable.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Encoding get encoding => _sink.encoding;
```

::: {#setter .section .multi-line-signature}
void encoding=([Encoding](../../dart-convert/encoding-class) encoding)

::: {.features}
inherited
:::
:::

The [Encoding](../../dart-convert/encoding-class) used when writing
strings.

Depending on the underlying consumer, this property might be mutable.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void set encoding(Encoding encoding) {
  _sink.encoding = encoding;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Stdout/encoding.html>
:::
