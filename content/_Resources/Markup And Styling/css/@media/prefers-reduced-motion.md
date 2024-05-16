prefers-reduced-motion
======================

**Warning:** An embedded example at the bottom of this page has a
scaling movement that may be problematic for some readers. Readers with
vestibular motion disorders may wish to enable the reduce motion feature
on their device before viewing the animation.

The `prefers-reduced-motion`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) is used to detect if a user has
enabled a setting on their device to minimize the amount of
non-essential motion. The setting is used to convey to the browser on
the device that the user prefers an interface that removes, reduces, or
replaces motion-based animations.

Such animations can trigger discomfort for those with [vestibular motion
disorders](https://www.a11yproject.com/posts/understanding-vestibular-disorders/).
Animations such as scaling or panning large objects can be vestibular
motion triggers.

[css]

```css
@media (prefers-reduced-motion) {
  /* styles to apply if a user's device settings are set to reduced motion */
}
```

Syntax
------

[`no-preference`](#no-preference)

:   Indicates that a user has made no preference known on the device.
    This keyword value evaluates as false.

[`reduce`](#reduce)

:   Indicates that a user has enabled the setting on their device for
    reduced motion. This keyword value evaluates as true.

User preferences
----------------

For Firefox, the `reduce` request is honoured if:

- In GTK/GNOME: Settings \> Accessibility \> Seeing \> Reduced
    animation is turned on.
  - In older versions of GNOME, GNOME Tweaks \> General tab (or
        Appearance, depending on version) \> Animations is turned off.
  - Alternatively, add `gtk-enable-animations = false` to the
        `[Settings]` block of [the GTK 3 configuration
        file](https://wiki.archlinux.org/title/GTK#Configuration).
- In Plasma/KDE: System Settings \> Workspace Behavior -\> General
    Behavior \> \"Animation speed\" is set all the way to right to
    \"Instant\".
- In Windows 10: Settings \> Ease of Access \> Display \> Show
    animations in Windows.
- In Windows 11: Settings \> Accessibility \> Visual Effects \>
    Animation Effects
- In macOS: System Preferences \> Accessibility \> Display \> Reduce
    motion.
- In iOS: Settings \> Accessibility \> Motion.
- In Android 9+: Settings \> Accessibility \> Remove animations.
- In Firefox `about:config`: Add a number preference called
    `ui.prefersReducedMotion` and set its value to either `0` for full
    animation or to `1` to indicate a preference for reduced motion.
    Changes to this preference take effect immediately.

Examples
--------

This example uses a scaling animation for the purpose of demonstrating
`prefers-reduced-motion`. If you enable the setting for reducing motion
in the accessibility preferences on your device, the
`prefers-reduced-motion` media query will detect your preference and the
CSS within the reduced motion rules, with the same
[specificity](specificity.md) but coming later in the [CSS source
order](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance#source_order),
will take precedence. As a result, the
[animation](using_css_animations.md) on the box will tone
down to the `dissolve` animation, which is a more muted animation that
is not a vestibular motion trigger.

### Toning down the animation scaling

#### HTML

[html]

```html
<div class="animation">animated box</div>
```

#### CSS

[css]

```css
.animation {
  animation: pulse 1s linear infinite both;
  background-color: purple;
}

/* Tone down the animation to avoid vestibular motion triggers. */
@media (prefers-reduced-motion) {
  .animation {
    animation: dissolve 4s linear infinite both;
    background-color: green;
    text-decoration: overline;
  }
}
```

#### Result

You can enable the setting for reducing motion on [your
device](#user_preferences) to view the change in animation scaling. This
example uses the background color and the line over the text to visually
highlight when the keyframe animation switches in response to the
setting being enabled or disabled.

Specifications
--------------

  ---------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------

  [Media Queries Level 5\
  [\#
  prefers-reduced-motion]](https://drafts.csswg.org/mediaqueries-5/#prefers-reduced-motion)

  ---------------------------------------------------------------------------------------------------

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

`prefers-reduced-motion`

74

79

63

No

62

10.1

74

74

64

53

10.3

11.0

See also
--------

- [`Sec-CH-Prefers-Reduced-Motion`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-Prefers-Reduced-Motion)
    HTTP Header [User Agent Client
    Hint](https://developer.mozilla.org/en-US/docs/Web/HTTP/Client_hints#user-agent_client_hints)
- [An introduction to the reduced motion media
    query](https://css-tricks.com/introduction-reduced-motion-media-query/)
    on CSS-Tricks (2019)
- [Responsive design for
    motion](https://webkit.org/blog/7551/responsive-design-for-motion/)
    on WebKit Blog (2017)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion>
