[dart:html](../../dart-html/dart-html-library){._links-link}

securityPolicyViolationEvent constant
=====================================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[SecurityPolicyViolationEvent](../securitypolicyviolationevent-class)\>
const securityPolicyViolationEvent
:::

Static factory designed to expose `securitypolicyviolation` events to
event handlers that are not necessarily instances of
[Document](../document-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<SecurityPolicyViolationEvent>
    securityPolicyViolationEvent =
    const EventStreamProvider<SecurityPolicyViolationEvent>(
        'securitypolicyviolation');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/securityPolicyViolationEvent-constant.html>
:::
