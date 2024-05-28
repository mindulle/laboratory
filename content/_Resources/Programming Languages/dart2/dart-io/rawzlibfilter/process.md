[dart:io](../../dart-io/dart-io-library){._links-link}

process method
==============

::: {.section .multi-line-signature}
void process(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    data,
2.  [int](../../dart-core/int-class) start,
3.  [int](../../dart-core/int-class) end

)
:::

Process a chunk of data.

This method must only be called when [processed](processed) returns
`null`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void process(List<int> data, int start, int end);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawZLibFilter/process.html>
:::
