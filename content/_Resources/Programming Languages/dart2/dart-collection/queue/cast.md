[dart:collection](../../dart-collection/dart-collection-library){._links-link}

cast\<R\> method
================

::: {.section .multi-line-signature}
[Queue](../queue-class)\<R\> cast\<R\>()

::: {.features}
override
:::
:::

Provides a view of this queue as a queue of `R` instances, if necessary.

If this queue contains only instances of `R`, all read operations will
work correctly. If any operation tries to access an element that is not
an instance of `R`, the access will throw instead.

Elements added to the queue (e.g., by using [addFirst](addfirst) or
[addAll](addall)) must be instances of `R` to be valid arguments to the
adding function, and they must also be instances of `E` to be accepted
by this queue as well.

Methods which accept `Object?` as argument, like
[contains](../../dart-core/iterable/contains) and [remove](remove), will
pass the argument directly to the this queue\'s method without any
checks. That means that you can do
`queueOfStrings.cast<int>().remove("a")` successfully, even if it looks
like it shouldn\'t have any effect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Queue<R> cast<R>();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/Queue/cast.html>
:::
