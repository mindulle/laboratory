[dart:html](../../dart-html/dart-html-library){._links-link}

open method
===========

::: {.section .multi-line-signature}
void open(

1.  [String](../../dart-core/string-class) method,
2.  [String](../../dart-core/string-class) url,
3.  {[bool](../../dart-core/bool-class)? async,
4.  [String](../../dart-core/string-class)? user,
5.  [String](../../dart-core/string-class)? password}

)
:::

Specify the desired `url`, and `method` to use in making the request.

By default the request is done asynchronously, with no user or password
authentication information. If `async` is false, the request will be
sent synchronously.

Calling `open` again on a currently active request is equivalent to
calling [abort](abort).

Note: Most simple HTTP requests can be accomplished using the
[getString](getstring), [request](request),
[requestCrossOrigin](requestcrossorigin), or
[postFormData](postformdata) methods. Use of this `open` method is
intended only for more complex HTTP requests where finer-grained control
is needed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void open(String method, String url,
    {bool? async, String? user, String? password}) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/open.html>
:::
