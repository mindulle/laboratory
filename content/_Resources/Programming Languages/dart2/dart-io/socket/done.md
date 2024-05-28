[dart:io](../../dart-io/dart-io-library){._links-link}

done property
=============

::: {#getter .section .multi-line-signature}
[Future](../../dart-async/future-class) done

::: {.features}
override
:::
:::

A future that will complete when the consumer closes, or when an error
occurs.

This future is identical to the future returned by [close](close).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future get done;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Socket/done.html>
:::
