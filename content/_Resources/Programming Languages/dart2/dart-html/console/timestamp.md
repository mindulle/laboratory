[dart:html](../../dart-html/dart-html-library){._links-link}

timeStamp method
================

::: {.section .multi-line-signature}
void timeStamp(

1.  \[[Object](../../dart-core/object-class)? arg\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void timeStamp([Object? arg]) =>
    _isConsoleDefined ? JS('void', 'window.console.timeStamp(#)', arg) : null;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Console/timeStamp.html>
:::
