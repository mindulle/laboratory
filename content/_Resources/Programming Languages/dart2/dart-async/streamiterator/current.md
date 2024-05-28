[dart:async](../../dart-async/dart-async-library){._links-link}

current property
================

::: {#getter .section .multi-line-signature}
T current
:::

The current value of the stream.

When a [moveNext](movenext) call completes with `true`, the
[current](current) field holds the most recent event of the stream, and
it stays like that until the next call to [moveNext](movenext). This
value must only be read after a call to [moveNext](movenext) has
completed with `true`, and only until the [moveNext](movenext) is called
again.

If the StreamIterator has not yet been moved to the first element
([moveNext](movenext) has not been called and completed yet), or if the
StreamIterator has been moved past the last element
([moveNext](movenext) has returned `false`), then [current](current) is
unspecified. A [StreamIterator](../streamiterator-class) may either
throw or return an iterator-specific default value in that case.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
T get current;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamIterator/current.html>
:::
