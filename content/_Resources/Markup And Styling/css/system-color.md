\<system-color\>
================

The `<system-color>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) usually reflects the default color choices used for the
different parts of a web page.

However, user agents can provide an accessibility feature called *forced
colors mode*, in which colors are restricted into a user- and user
agent-defined palette, overriding the author\'s choice of colors in
certain properties. In forced colors mode, `<system-color>` exposes the
chosen colors, so that the rest of the page can integrate with them. An
example of forced colors mode is [high contrast mode on
Windows](https://blogs.windows.com/msedgedev/2020/09/17/styling-for-windows-high-contrast-with-new-standards-for-forced-colors/).

In forced colors mode, authors should use colors from the
`<system-color>` type for all properties that are *not* in the set of
properties whose colors are overridden. This ensures that the page
consistently uses the same color palette across all properties.

Authors can detect forced colors mode using the
[`forced-colors`](forced-colors.md) media feature.

A `<system-color>` value can be used anywhere a [`<color>`](color_value.md)
can be used.

Syntax
------

Note that these keywords are *case insensitive*, but are listed here
with mixed case for readability.

[`AccentColor`](#accentcolor)

:   Background of accented user interface controls

[`AccentColorText`](#accentcolortext)

:   Text of accented user interface controls

[`ActiveText`](#activetext)

:   Text of active links

[`ButtonBorder`](#buttonborder)

:   Base border color of controls

[`ButtonFace`](#buttonface)

:   Background color of controls

[`ButtonText`](#buttontext)

:   Text color of controls

[`Canvas`](#canvas)

:   Background of application content or documents

[`CanvasText`](#canvastext)

:   Text color in application content or documents

[`Field`](#field)

:   Background of input fields

[`FieldText`](#fieldtext)

:   Text in input fields

[`GrayText`](#graytext)

:   Text color for disabled items (e.g. a disabled control)

[`Highlight`](#highlight)

:   Background of selected items

[`HighlightText`](#highlighttext)

:   Text color of selected items

[`LinkText`](#linktext)

:   Text of non-active, non-visited links

[`Mark`](#mark)

:   Background of text that has been specially marked (such as by the
    HTML `mark` element)

[`MarkText`](#marktext)

:   Text that has been specially marked (such as by the HTML `mark`
    element)

[`VisitedText`](#visitedtext)

:   Text of visited links

### Deprecated system color keywords

The following keywords were defined in earlier versions of the CSS Color
Module. They are now deprecated for use on public web pages.

[`ActiveBorder`](#activeborder) [Deprecated]

:   Active window border.

[`ActiveCaption`](#activecaption) [Deprecated]

:   Active window caption. Should be used with `CaptionText` as
    foreground color.

[`AppWorkspace`](#appworkspace) [Deprecated]

:   Background color of multiple document interface.

[`Background`](#background) [Deprecated]

:   Desktop background.

[`ButtonHighlight`](#buttonhighlight) [Deprecated]

:   The color of the border facing the light source for 3-D elements
    that appear 3-D due to that layer of surrounding border.

[`ButtonShadow`](#buttonshadow) [Deprecated]

:   The color of the border away from the light source for 3-D elements
    that appear 3-D due to that layer of surrounding border.

[`CaptionText`](#captiontext) [Deprecated]

:   Text in caption, size box, and scrollbar arrow box. Should be used
    with the `ActiveCaption` background color.

[`InactiveBorder`](#inactiveborder) [Deprecated]

:   Inactive window border.

[`InactiveCaption`](#inactivecaption) [Deprecated]

:   Inactive window caption. Should be used with the
    `InactiveCaptionText` foreground color.

[`InactiveCaptionText`](#inactivecaptiontext) [Deprecated]

:   Color of text in an inactive caption. Should be used with the
    `InactiveCaption` background color.

[`InfoBackground`](#infobackground) [Deprecated]

:   Background color for tooltip controls. Should be used with the
    `InfoText` foreground color.

[`InfoText`](#infotext) [Deprecated]

:   Text color for tooltip controls. Should be used with the
    `InfoBackground` background color.

[`Menu`](#menu) [Deprecated]

:   Menu background. Should be used with the `MenuText` or
    `-moz-MenuBarText` foreground color.

[`MenuText`](#menutext) [Deprecated]

:   Text in menus. Should be used with the `Menu` background color.

[`Scrollbar`](#scrollbar) [Deprecated]

:   Background color of scroll bars.

[`ThreeDDarkShadow`](#threeddarkshadow) [Deprecated]

:   The color of the darker (generally outer) of the two borders away
    from the light source for 3-D elements that appear 3-D due to two
    concentric layers of surrounding border.

[`ThreeDFace`](#threedface) [Deprecated]

:   The face background color for 3-D elements that appear 3-D due to
    two concentric layers of surrounding border. Should be used with the
    `ButtonText` foreground color.

[`ThreeDHighlight`](#threedhighlight) [Deprecated]

:   The color of the lighter (generally outer) of the two borders facing
    the light source for 3-D elements that appear 3-D due to two
    concentric layers of surrounding border.

[`ThreeDLightShadow`](#threedlightshadow) [Deprecated]

:   The color of the darker (generally inner) of the two borders facing
    the light source for 3-D elements that appear 3-D due to two
    concentric layers of surrounding border.

[`ThreeDShadow`](#threedshadow) [Deprecated]

:   The color of the lighter (generally inner) of the two borders away
    from the light source for 3-D elements that appear 3-D due to two
    concentric layers of surrounding border.

[`Window`](#window) [Deprecated]

:   Window background. Should be used with the `WindowText` foreground
    color.

[`WindowFrame`](#windowframe) [Deprecated]

:   Window frame.

[`WindowText`](#windowtext) [Deprecated]

:   Text in windows. Should be used with the `Window` background color.

Examples
--------

### Using system colors

In this example we have a button that normally gets its contrast using
the [`box-shadow`](box-shadow.md) property. In forced colors mode,
`box-shadow` is forced to `none`, so the example uses the
`forced-colors` media feature to ensure there is a border of the
appropriate color (`ButtonBorder` in this case).

#### HTML

[html]

```html
<button class="button">Press me!</button>
```

#### CSS

[css]

```css
.button {
  border: 0;
  padding: 10px;
  box-shadow:
    -2px -2px 5px gray,
    2px 2px 5px gray;
}

@media (forced-colors: active) {
  .button {
    /* Use a border instead, since box-shadow
    is forced to 'none' in forced-colors mode */
    border: 2px ButtonBorder solid;
  }
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\#
  css-system-colors]](https://drafts.csswg.org/css-color/#css-system-colors)

  ------------------------------------------------------------------------------------

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

`system-color`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`mark_marktext_buttonborder`

No

No

109

No

No

No

No

No

109

No

No

No

See also
--------

- [`<color>`](color_value.md): the data type these keywords belong to

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/system-color>
