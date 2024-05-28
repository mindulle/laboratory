[dart:async](../../dart-async/dart-async-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
void add(

1.  T data

)

::: {.features}
override
:::
:::

Adds event to the controller\'s stream.

As [StreamController.add](../streamcontroller/add), but must not be
called while an event is being added by [add](add), [addError](adderror)
or [close](close).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void add(T data);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/SynchronousStreamController/add.html>
:::
