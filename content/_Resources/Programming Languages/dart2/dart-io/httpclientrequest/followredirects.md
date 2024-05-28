[dart:io](../../dart-io/dart-io-library){._links-link}

followRedirects property
========================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) followRedirects

::: {.features}
read / write
:::
:::

Whether to follow redirects automatically.

Set this property to `false` if this request should not automatically
follow redirects. The default is `true`.

Automatic redirect will only happen for \"GET\" and \"HEAD\" requests
and only for the status codes
[HttpStatus.movedPermanently](../../dart-html/httpstatus/movedpermanently-constant)
(301), [HttpStatus.found](../../dart-html/httpstatus/found-constant)
(302),
[HttpStatus.movedTemporarily](../../dart-html/httpstatus/movedtemporarily-constant)
(302, alias for
[HttpStatus.found](../../dart-html/httpstatus/found-constant)),
[HttpStatus.seeOther](../../dart-html/httpstatus/seeother-constant)
(303),
[HttpStatus.temporaryRedirect](../../dart-html/httpstatus/temporaryredirect-constant)
(307) and
[HttpStatus.permanentRedirect](../../dart-html/httpstatus/permanentredirect-constant)
(308). For
[HttpStatus.seeOther](../../dart-html/httpstatus/seeother-constant)
(303) automatic redirect will also happen for \"POST\" requests with the
method changed to \"GET\" when following the redirect.

All headers added to the request will be added to the redirection
request(s) except when forwarding sensitive headers like
\"Authorization\", \"WWW-Authenticate\", and \"Cookie\". Those headers
will be skipped if following a redirect to a domain that is not a
subdomain match or exact match of the initial domain. For example, a
redirect from \"foo.com\" to either \"foo.com\" or \"sub.foo.com\" will
forward the sensitive headers, but a redirect to \"bar.com\" will not.

Any body send with the request will not be part of the redirection
request(s).

For precise control of redirect handling, set this property to `false`
and make a separate HTTP request to process the redirect. For example:

``` {.language-dart data-language="dart"}
final client = HttpClient();
var uri = Uri.parse("http://localhost/");
var request = await client.getUrl(uri);
request.followRedirects = false;
var response = await request.close();
while (response.isRedirect) {
  response.drain();
  final location = response.headers.value(HttpHeaders.locationHeader);
  if (location != null) {
    uri = uri.resolve(location);
    request = await client.getUrl(uri);
    // Set the body or headers as desired.
    request.followRedirects = false;
    response = await request.close();
  }
}
// Do something with the final response.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool followRedirects = true;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientRequest/followRedirects.html>
:::
