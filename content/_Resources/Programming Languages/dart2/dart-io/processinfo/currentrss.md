[dart:io](../../dart-io/dart-io-library){._links-link}

currentRss property
===================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) currentRss
:::

The current resident set size of memory for the process.

Note that the meaning of this field is platform dependent. For example,
some memory accounted for here may be shared with other processes, or if
the same page is mapped into a process\'s address space, it may be
counted twice.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static int get currentRss;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ProcessInfo/currentRss.html>
:::
