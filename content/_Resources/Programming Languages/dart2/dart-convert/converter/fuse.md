[dart:convert](../../dart-convert/dart-convert-library){._links-link}

fuse\<TT\> method
=================

::: {.section .multi-line-signature}
[Converter](../converter-class)\<S, TT\> fuse\<TT\>(

1.  [Converter](../converter-class)\<T, TT\> other

)
:::

Fuses `this` with `other`.

Encoding with the resulting converter is equivalent to converting with
`this` before converting with `other`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Converter<S, TT> fuse<TT>(Converter<T, TT> other) {
  return _FusedConverter<S, T, TT>(this, other);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Converter/fuse.html>
:::
