[dart:async](../../dart-async/dart-async-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
void add(

1.  T event

)

::: {.features}
override
:::
:::

Sends a data `event`.

Listeners receive this event in a later microtask.

Note that a synchronous controller (created by passing true to the
`sync` parameter of the `StreamController` constructor) delivers events
immediately. Since this behavior violates the contract mentioned here,
synchronous controllers should only be used as described in the
documentation to ensure that the delivered events always *appear* as if
they were delivered in a separate microtask.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void add(T event);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamController/add.html>
:::
