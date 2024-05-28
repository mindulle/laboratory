[dart:async](../../dart-async/dart-async-library){._links-link}

load method
===========

::: {.section .multi-line-signature}
[Future](../future-class)\<[Null](../../dart-core/null-class)\> load()
:::

Ensure that [libraryName](libraryname) has been loaded.

If the library fails to load, the [Future](../future-class) will
complete with a [DeferredLoadException](../deferredloadexception-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Future<Null> load();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/DeferredLibrary/load.html>
:::
