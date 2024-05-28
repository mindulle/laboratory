[dart:html](../../dart-html/dart-html-library){._links-link}

HttpRequest constructor
=======================

::: {.section .multi-line-signature}
HttpRequest()
:::

General constructor for any type of request (GET, POST, etc).

This call is used in conjunction with [open](open):

``` {.language-dart data-language="dart"}
var request = new HttpRequest();
request.open('GET', 'http://dartlang.org');
request.onLoad.listen((event) => print(
    'Request complete ${event.target.reponseText}'));
request.send();
```

is the (more verbose) equivalent of

``` {.language-dart data-language="dart"}
HttpRequest.getString('http://dartlang.org').then(
    (result) => print('Request complete: $result'));
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory HttpRequest() {
  return HttpRequest._create_1();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/HttpRequest.html>
:::
