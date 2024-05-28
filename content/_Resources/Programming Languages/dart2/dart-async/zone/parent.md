[dart:async](../../dart-async/dart-async-library){._links-link}

parent property
===============

::: {#getter .section .multi-line-signature}
[Zone](../zone-class)? parent
:::

The parent zone of the this zone.

Is `null` if `this` is the [root](root-constant) zone.

Zones are created by [fork](fork) on an existing zone, or by
[runZoned](../runzoned) which forks the [current](current) zone. The new
zone\'s parent zone is the zone it was forked from.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Zone? get parent;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/parent.html>
:::
