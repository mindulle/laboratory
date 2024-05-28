[dart:async](../../dart-async/dart-async-library){._links-link}

inSameErrorZone method
======================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) inSameErrorZone(

1.  [Zone](../zone-class) otherZone

)
:::

Whether this zone and `otherZone` are in the same error zone.

Two zones are in the same error zone if they have the same
[errorZone](errorzone).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool inSameErrorZone(Zone otherZone);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/inSameErrorZone.html>
:::
