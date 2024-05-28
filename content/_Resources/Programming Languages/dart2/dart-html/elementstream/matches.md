[dart:html](../../dart-html/dart-html-library){._links-link}

matches method
==============

::: {.section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<T\> matches(

1.  [String](../../dart-core/string-class) selector

)
:::

Return a stream that only fires when the particular event fires for
elements matching the specified CSS selector.

This is the Dart equivalent to jQuery\'s
[delegate](http://api.jquery.com/delegate/).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<T> matches(String selector);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ElementStream/matches.html>
:::
