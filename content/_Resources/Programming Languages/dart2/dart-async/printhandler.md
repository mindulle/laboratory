[dart:async](../dart-async/dart-async-library){._links-link}

PrintHandler typedef
====================

::: {.section .multi-line-signature}
PrintHandler = void Function([Zone](zone-class) self,
[ZoneDelegate](zonedelegate-class) parent, [Zone](zone-class) zone,
[String](../dart-core/string-class) line)
:::

The type of a custom [Zone.print](zone/print) implementation function.

Receives the [Zone](zone-class) that the handler was registered on as
`self`, a delegate forwarding to the handlers of `self`\'s parent zone
as `parent`, and the current zone where the error was uncaught as
`zone`, which will have `self` as a parent zone.

The string `line` is the one which was passed to
[Zone.print](zone/print) of `zone`, (possibly through the global
[print](../dart-core/print) function).

The custom handler can intercept print operations and redirect them to
other targets than the console.

The function must only access zone-related functionality through `self`,
`parent` or `zone`. It should not depend on the current zone
([Zone.current](zone/current)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef void PrintHandler(
    Zone self, ZoneDelegate parent, Zone zone, String line);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/PrintHandler.html>
:::
