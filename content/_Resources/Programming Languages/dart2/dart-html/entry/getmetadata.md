[dart:html](../../dart-html/dart-html-library){._links-link}

getMetadata method
==================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'getMetadata\')

</div>

[Future](../../dart-async/future-class)\<[Metadata](../metadata-class)\>
getMetadata()

::: {.features}
\@JSName(\'getMetadata\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('getMetadata')
Future<Metadata> getMetadata() {
  var completer = new Completer<Metadata>();
  _getMetadata((value) {
    applyExtension('Metadata', value);
    completer.complete(value);
  }, (error) {
    completer.completeError(error);
  });
  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Entry/getMetadata.html>
:::
