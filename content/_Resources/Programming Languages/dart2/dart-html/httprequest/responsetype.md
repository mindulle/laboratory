[dart:html](../../dart-html/dart-html-library){._links-link}

responseType property
=====================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) responseType
:::

[String](../../dart-core/string-class) telling the server the desired
response format.

Default is `String`. Other options are one of \'arraybuffer\', \'blob\',
\'document\', \'json\', \'text\'. Some newer browsers will throw
NS\_ERROR\_DOM\_INVALID\_ACCESS\_ERR if `responseType` is set while
performing a synchronous request.

See also: [MDN
responseType](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest#xmlhttprequest-responsetype)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get responseType native;
```

::: {#setter .section .multi-line-signature}
void responseType=([String](../../dart-core/string-class) value)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set responseType(String value) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/responseType.html>
:::
