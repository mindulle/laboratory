[dart:html](../../dart-html/dart-html-library){._links-link}

Notification constructor
========================

::: {.section .multi-line-signature}
Notification(

1.  [String](../../dart-core/string-class) title,
2.  {[String](../../dart-core/string-class)? dir,
3.  [String](../../dart-core/string-class)? body,
4.  [String](../../dart-core/string-class)? lang,
5.  [String](../../dart-core/string-class)? tag,
6.  [String](../../dart-core/string-class)? icon}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Notification(String title,
    {String? dir, String? body, String? lang, String? tag, String? icon}) {
  var parsedOptions = {};
  if (dir != null) parsedOptions['dir'] = dir;
  if (body != null) parsedOptions['body'] = body;
  if (lang != null) parsedOptions['lang'] = lang;
  if (tag != null) parsedOptions['tag'] = tag;
  if (icon != null) parsedOptions['icon'] = icon;
  return Notification._factoryNotification(title, parsedOptions);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Notification/Notification.html>
:::
