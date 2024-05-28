[dart:async](../../dart-async/dart-async-library){._links-link}

root constant
=============

::: {.section .multi-line-signature}
[Zone](../zone-class) const root
:::

The root zone.

All isolate entry functions (`main` or spawned functions) start running
in the root zone (that is, [Zone.current](current) is identical to
[Zone.root](root-constant) when the entry function is called). If no
custom zone is created, the rest of the program always runs in the root
zone.

The root zone implements the default behavior of all zone operations.
Many methods, like [registerCallback](registercallback) do the bare
minimum required of the function, and are only provided as a hook for
custom zones. Others, like [scheduleMicrotask](schedulemicrotask),
interact with the underlying system to implement the desired behavior.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const Zone root = _rootZone;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/root-constant.html>
:::
