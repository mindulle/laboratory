[dart:io](../../dart-io/dart-io-library){._links-link}

all constant
============

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) const all
:::

Bitfield for [FileSystemEntity.watch](../filesystementity/watch), for
enabling all of [create](create-constant), [modify](modify-constant),
[delete](delete-constant) and [move](move-constant).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const int all = create | modify | delete | move;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEvent/all-constant.html>
:::
