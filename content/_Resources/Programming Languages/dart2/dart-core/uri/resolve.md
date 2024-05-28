[dart:core](../../dart-core/dart-core-library){._links-link}

resolve method
==============

::: {.section .multi-line-signature}
[Uri](../uri-class) resolve(

1.  [String](../string-class) reference

)
:::

Resolve `reference` as an URI relative to `this`.

First turn `reference` into a URI using [Uri.parse](parse). Then resolve
the resulting URI relative to `this`.

Returns the resolved URI.

See [resolveUri](resolveuri) for details.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uri resolve(String reference);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/resolve.html>
:::
