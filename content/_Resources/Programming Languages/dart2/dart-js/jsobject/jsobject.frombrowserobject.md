[dart:js](../../dart-js/dart-js-library){._links-link}

JsObject.fromBrowserObject constructor
======================================

::: {.section .multi-line-signature}
JsObject.fromBrowserObject(

1.  [Object](../../dart-core/object-class) object

)
:::

Constructs a [JsObject](../jsobject-class) that proxies a native Dart
object; *for expert use only*.

Use this constructor only if you wish to get access to JavaScript
properties attached to a browser host object, such as a Node or Blob,
that is normally automatically converted into a native Dart object.

An exception will be thrown if `object` has the type `bool`, `num`, or
`String`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory JsObject.fromBrowserObject(Object object);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js/JsObject/JsObject.fromBrowserObject.html>
:::
