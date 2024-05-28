[dart:html](../../dart-html/dart-html-library){._links-link}

requestMidiAccess method
========================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'requestMIDIAccess\')

</div>

[Future](../../dart-async/future-class) requestMidiAccess(

1.  \[[Map](../../dart-core/map-class)? options\]

)

::: {.features}
\@JSName(\'requestMIDIAccess\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('requestMIDIAccess')
Future requestMidiAccess([Map? options]) {
  var options_dict = null;
  if (options != null) {
    options_dict = convertDartToNative_Dictionary(options);
  }
  return promiseToFuture(
      JS("", "#.requestMIDIAccess(#)", this, options_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Navigator/requestMidiAccess.html>
:::
