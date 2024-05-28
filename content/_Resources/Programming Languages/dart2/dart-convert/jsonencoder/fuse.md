[dart:convert](../../dart-convert/dart-convert-library){._links-link}

fuse\<T\> method
================

::: {.section .multi-line-signature}
[Converter](../converter-class)\<[Object](../../dart-core/object-class)?,
T\> fuse\<T\>(

1.  [Converter](../converter-class)\<[String](../../dart-core/string-class),
    T\> other

)

::: {.features}
override
:::
:::

Fuses `this` with `other`.

Encoding with the resulting converter is equivalent to converting with
`this` before converting with `other`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Converter<Object?, T> fuse<T>(Converter<String, T> other) {
  if (other is Utf8Encoder) {
    // The instance check guarantees that `T` is (a subtype of) List<int>,
    // but the static type system doesn't know that, and so we cast.
    return JsonUtf8Encoder(indent, _toEncodable) as Converter<Object?, T>;
  }
  return super.fuse<T>(other);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonEncoder/fuse.html>
:::
