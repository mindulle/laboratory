[dart:io](../../dart-io/dart-io-library){._links-link}

getRawOption method
===================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.2\")

</div>

[Uint8List](../../dart-typed_data/uint8list-class) getRawOption(

1.  [RawSocketOption](../rawsocketoption-class) option

)

::: {.features}
\@Since(\"2.2\")
:::
:::

Reads low level information about the [RawSocket](../rawsocket-class).

See [RawSocketOption](../rawsocketoption-class) for available options.

Returns the [RawSocketOption.value](../rawsocketoption/value) on
success.

Throws an [OSError](../oserror-class) on failure.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.2")
Uint8List getRawOption(RawSocketOption option);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocket/getRawOption.html>
:::
