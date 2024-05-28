[dart:html](../../dart-html/dart-html-library){._links-link}

EventSource constructor
=======================

::: {.section .multi-line-signature}
EventSource(

1.  [String](../../dart-core/string-class) url,
2.  {dynamic withCredentials = false}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory EventSource(String url, {withCredentials: false}) {
  var parsedOptions = {
    'withCredentials': withCredentials,
  };
  return EventSource._factoryEventSource(url, parsedOptions);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/EventSource/EventSource.html>
:::
