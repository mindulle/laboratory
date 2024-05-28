[dart:developer](../../dart-developer/dart-developer-library){._links-link}

step method
===========

::: {.section .multi-line-signature}
[Flow](../flow-class) step(

1.  [int](../../dart-core/int-class) id

)
:::

A \"step\" Flow event.

When passed to a [Timeline](../timeline-class) method, generates a
\"step\" Flow event. The `id` argument is required. It can come either
from another [Flow](../flow-class) event, or some id that comes from the
environment.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Flow step(int id) => new Flow._(_step, id);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Flow/step.html>
:::
