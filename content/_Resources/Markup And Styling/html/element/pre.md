\<pre\>: The Preformatted Text element
======================================

The `<pre>` [HTML](../index) element represents preformatted text which
is to be presented exactly as written in the HTML file. The text is
typically rendered using a non-proportional, or
[monospaced](https://en.wikipedia.org/wiki/Monospaced_font), font.
Whitespace inside this element is displayed as written.

Try it
------

If you have to display reserved characters such as `<`, `>`, `&`, and
`"` within the `<pre>` tag, the characters must be escaped using their
respective [HTML
entity](https://developer.mozilla.org/en-US/docs/Glossary/Entity).

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`cols`](#cols) [Non-standard]

:   Contains the *preferred* count of characters that a line should
    have. It was a non-standard synonym of [`width`](#width). To achieve
    such an effect, use CSS
    [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)
    instead.

[`width`](#width) [Deprecated]

:   Contains the *preferred* count of characters that a line should
    have. Though technically still implemented, this attribute has no
    visual effect; to achieve such an effect, use CSS
    [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)
    instead.

[`wrap`](#wrap) [Non-standard]

:   Is a *hint* indicating how the overflow must happen. In modern
    browser this hint is ignored and no visual effect results in its
    present; to achieve such an effect, use CSS
    [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space)
    instead.

Accessibility concerns
----------------------

It is important to provide an alternate description for any images or
diagrams created using preformatted text. The alternate description
should clearly and concisely describe the image or diagram\'s content.

People experiencing low vision conditions and browsing with the aid of
assistive technology such as a screen reader may not understand what the
preformatted text characters are representing when they are read out in
sequence.

A combination of the [`<figure>`](figure) and
[`<figcaption>`](figcaption) elements, supplemented by the
[ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA)
`role` and
[`aria-label`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label)
attributes on the `pre` element allow the preformatted
[ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII) art to
be announced as an image with alternative text, and the `figcaption`
serving as the image\'s caption.

### Example

[html]

```html
<figure>
  <pre role="img" aria-label="ASCII COW">
      ___________________________
  &lt; I'm an expert in my field. &gt;
      ---------------------------
          \   ^__^
           \  (oo)\_______
              (__)\       )\/\
                  ||----w |
                  ||     ||
  </pre>
  <figcaption id="cow-caption">
    A cow saying, "I'm an expert in my field." The cow is illustrated using
    preformatted text characters.
  </figcaption>
</figure>
```

- [MDN Understanding WCAG, Guideline 1.1
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%E2%80%94_providing_text_alternatives_for_non-text_content)
- [H86: Providing text alternatives for ASCII art, emoticons, and
    leetspeak \| W3C Techniques for WCAG
    2.0](https://www.w3.org/TR/WCAG20-TECHS/H86.html)

Examples
--------

### Basic example

#### HTML

[html]

```html
<p>Using CSS to change the font color is easy.</p>
<pre>
body {
  color: red;
}
</pre>
```

#### Result

### Escaping reserved characters

#### HTML

[html]

```html
<pre>
let i = 5;

if (i &lt; 10 &amp;&amp; i &gt; 0)
  return &quot;Single Digit Number&quot;
</pre>
```

#### Result

Technical summary
-----------------

  --------------------------------------------- -------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role                            `generic`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLPreElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPreElement)
  --------------------------------------------- -------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-pre-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-pre-element)

  ---------------------------------------------------------------------------------------------------------

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`pre`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`cols`

No

No

1--29

No

No

No

No

No

4--29

No

No

No

`width`

1Specifying the `width` attribute has no layout effect.

12Specifying the `width` attribute has no layout effect.

1Since Firefox 29, specifying the `width` attribute has no layout
effect.

YesSpecifying the `width` attribute has no layout effect.

15Specifying the `width` attribute has no layout effect.

3Specifying the `width` attribute has no layout effect.

4.4Specifying the `width` attribute has no layout effect.

18Specifying the `width` attribute has no layout effect.

4Since Firefox 29, specifying the `width` attribute has no layout
effect.

14Specifying the `width` attribute has no layout effect.

2Specifying the `width` attribute has no layout effect.

1.0Specifying the `width` attribute has no layout effect.

`wrap`

16

79

1

No

15

6

4.4

18

4

14

6

1.0

See also
--------

- CSS:
    [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space),
    [`word-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/word-break)
- [HTML
    Entity](https://developer.mozilla.org/en-US/docs/Glossary/Entity)
- Related element: [`<code>`](code)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/pre>>
