[dart:async](../../dart-async/dart-async-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
dynamic operator \[\](

1.  [Object](../../dart-core/object-class)? key

)
:::

Retrieves the zone-value associated with `key`.

If this zone does not contain the value looks up the same key in the
parent zone. If the `key` is not found returns `null`.

Any object can be used as key, as long as it has compatible
`operator ==` and `hashCode` implementations. By controlling access to
the key, a zone can grant or deny access to the zone value.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
dynamic operator [](Object? key);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/operator_get.html>
:::
