[dart:convert](../../dart-convert/dart-convert-library){._links-link}

JsonCodec.withReviver constructor
=================================

::: {.section .multi-line-signature}
JsonCodec.withReviver(

1.  dynamic reviver(
    1.  [Object](../../dart-core/object-class)? key,
    2.  [Object](../../dart-core/object-class)? value

    )

)
:::

Creates a `JsonCodec` with the given reviver.

The `reviver` function is called once for each object or list property
that has been parsed during decoding. The `key` argument is either the
integer list index for a list property, the string map key for object
properties, or `null` for the final result.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
JsonCodec.withReviver(dynamic reviver(Object? key, Object? value))
    : this(reviver: reviver);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonCodec/JsonCodec.withReviver.html>
:::
