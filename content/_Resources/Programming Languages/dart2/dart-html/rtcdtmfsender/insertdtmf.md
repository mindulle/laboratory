[dart:html](../../dart-html/dart-html-library){._links-link}

insertDtmf method
=================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'insertDTMF\')

</div>

void insertDtmf(

1.  [String](../../dart-core/string-class) tones,
2.  \[[int](../../dart-core/int-class)? duration,
3.  [int](../../dart-core/int-class)? interToneGap\]

)

::: {.features}
\@JSName(\'insertDTMF\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('insertDTMF')
void insertDtmf(String tones, [int? duration, int? interToneGap]) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcDtmfSender/insertDtmf.html>
:::
