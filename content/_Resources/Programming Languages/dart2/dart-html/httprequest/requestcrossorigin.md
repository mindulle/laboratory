[dart:html](../../dart-html/dart-html-library){._links-link}

requestCrossOrigin method
=========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[String](../../dart-core/string-class)\>
requestCrossOrigin(

1.  [String](../../dart-core/string-class) url,
2.  {[String](../../dart-core/string-class)? method,
3.  [String](../../dart-core/string-class)? sendData}

)
:::

Makes a cross-origin request to the specified URL.

This API provides a subset of [request](request) which works on IE9. If
IE9 cross-origin support is not required then [request](request) should
be used instead.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<String> requestCrossOrigin(String url,
    {String? method, String? sendData}) {
  if (supportsCrossOrigin) {
    return request(url, method: method, sendData: sendData).then((xhr) {
      return xhr.responseText!;
    });
  }
  var completer = new Completer<String>();
  if (method == null) {
    method = 'GET';
  }
  var xhr = JS('var', 'new XDomainRequest()');
  JS('', '#.open(#, #)', xhr, method, url);
  JS(
      '',
      '#.onload = #',
      xhr,
      convertDartClosureToJS((e) {
        var response = JS('String', '#.responseText', xhr);
        completer.complete(response as FutureOr<String>?);
      }, 1));
  JS(
      '',
      '#.onerror = #',
      xhr,
      convertDartClosureToJS((e) {
        completer.completeError(e);
      }, 1));

  // IE9 RTM - XDomainRequest issued requests may abort if all event handlers
  // not specified
  // http://social.msdn.microsoft.com/Forums/ie/en-US/30ef3add-767c-4436-b8a9-f1ca19b4812e/ie9-rtm-xdomainrequest-issued-requests-may-abort-if-all-event-handlers-not-specified
  JS('', '#.onprogress = {}', xhr);
  JS('', '#.ontimeout = {}', xhr);
  JS('', '#.timeout = Number.MAX_VALUE', xhr);

  if (sendData != null) {
    JS('', '#.send(#)', xhr, sendData);
  } else {
    JS('', '#.send()', xhr);
  }

  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/requestCrossOrigin.html>
:::
