[dart:io](../../dart-io/dart-io-library){._links-link}

dictionary property
===================

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>?
dictionary

::: {.features}
final
:::
:::

Initial compression dictionary.

It should consist of strings (byte sequences) that are likely to be
encountered later in the data to be compressed, with the most commonly
used strings preferably put towards the end of the dictionary. Using a
dictionary is most useful when the data to be compressed is short and
can be predicted with good accuracy; the data can then be compressed
better than with the default empty dictionary.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final List<int>? dictionary;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/GZipCodec/dictionary.html>
:::
