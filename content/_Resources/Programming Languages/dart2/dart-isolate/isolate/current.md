[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

current property
================

::: {#getter .section .multi-line-signature}
[Isolate](../isolate-class) current
:::

An [Isolate](../isolate-class) object representing the current isolate.

The current isolate for code using [current](current) is the isolate
running the code.

The isolate object provides the capabilities required to inspect, pause
or kill the isolate, and allows granting these capabilities to others.

It is possible to pause the current isolate, but doing so *without*
first passing the ability to resume it again to another isolate, is a
sure way to hang your program.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Isolate get current;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/current.html>
:::
