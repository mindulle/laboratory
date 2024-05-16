\<track\>: The Embed Text Track element
=======================================

The `<track>` [HTML](../index) element is used as a child of the media
elements, [`<audio>`](audio) and [`<video>`](video). It lets you specify
timed text tracks (or time-based data), for example to automatically
handle subtitles. The tracks are formatted in [WebVTT
format](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
(`.vtt` files) --- Web Video Text Tracks.

Try it
------

  --------------------------------------------- -----------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None
  Permitted content                             None; it is a [void element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element).
  Tag omission                                  As it is a void element, the start tag must be present and the end tag must not be present.
  Permitted parents                             A media element, [`<audio>`](audio) or [`<video>`](video).
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLTrackElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`default`](#default)

:   This attribute indicates that the track should be enabled unless the
    user\'s preferences indicate that another track is more appropriate.
    This may only be used on one `track` element per media element.

[`kind`](#kind)

:   How the text track is meant to be used. If omitted the default kind
    is `subtitles`. If the attribute contains an invalid value, it will
    use `metadata` (Versions of Chrome earlier than 52 treated an
    invalid value as `subtitles`). The following keywords are allowed:

    -   `subtitles`
        -   Subtitles provide translation of content that cannot be
            understood by the viewer. For example speech or text that is
            not English in an English language film.
        -   Subtitles may contain additional content, usually extra
            background information. For example the text at the
            beginning of the Star Wars films, or the date, time, and
            location of a scene.
    -   `captions`
        -   Closed captions provide a transcription and possibly a
            translation of audio.
        -   It may include important non-verbal information such as
            music cues or sound effects. It may indicate the cue\'s
            source (e.g. music, text, character).
        -   Suitable for users who are deaf or when the sound is muted.
    -   `descriptions`
        -   Textual description of the video content.
        -   Suitable for users who are blind or where the video cannot
            be seen.
    -   `chapters`
        -   Chapter titles are intended to be used when the user is
            navigating the media resource.
    -   `metadata`
        -   Tracks used by scripts. Not visible to the user.

[`label`](#label)

:   A user-readable title of the text track which is used by the browser
    when listing available text tracks.

[`src`](#src)

:   Address of the track (`.vtt` file). Must be a valid URL. This
    attribute must be specified and its URL value must have the same
    origin as the document --- unless the [`<audio>`](audio) or
    [`<video>`](video) parent element of the `track` element has a
    [`crossorigin`](../attributes/crossorigin) attribute.

[`srclang`](#srclang)

:   Language of the track text data. It must be a valid [BCP
    47](https://r12a.github.io/app-subtags/) language tag. If the `kind`
    attribute is set to `subtitles`, then `srclang` must be defined.

Usage notes
-----------

### Track data types

The type of data that `track` adds to the media is set in the `kind`
attribute, which can take values of `subtitles`, `captions`,
`descriptions`, `chapters` or `metadata`. The element points to a source
file containing timed text that the browser exposes when the user
requests additional data.

A media element cannot have more than one `track` with the same `kind`,
`srclang`, and `label`.

### Detecting cue changes

The underlying
[`TextTrack`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrack),
indicated by the [`track`] property, receives a
`cuechange` event every time the currently-presented cue is changed.
This happens even if the track isn\'t associated with a media element.

If the track *is* associated with a media element, using the
[`<track>`](track) element as a child of the [`<audio>`](audio) or
[`<video>`](video) element, the `cuechange` event is also sent to the
[`HTMLTrackElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement).

[js]

```js
let textTrackElem = document.getElementById("texttrack");

textTrackElem.addEventListener("cuechange", (event) => {
  let cues = event.target.track.activeCues;
});
```

Examples
--------

[html]

```html
<video controls poster="/images/sample.gif">
  <source src="sample.mp4" type="video/mp4" />
  <source src="sample.ogv" type="video/ogv" />
  <track kind="captions" src="sampleCaptions.vtt" srclang="en" />
  <track kind="descriptions" src="sampleDescriptions.vtt" srclang="en" />
  <track kind="chapters" src="sampleChapters.vtt" srclang="en" />
  <track kind="subtitles" src="sampleSubtitles_de.vtt" srclang="de" />
  <track kind="subtitles" src="sampleSubtitles_en.vtt" srclang="en" />
  <track kind="subtitles" src="sampleSubtitles_ja.vtt" srclang="ja" />
  <track kind="subtitles" src="sampleSubtitles_oz.vtt" srclang="oz" />
  <track kind="metadata" src="keyStage1.vtt" srclang="en" label="Key Stage 1" />
  <track kind="metadata" src="keyStage2.vtt" srclang="en" label="Key Stage 2" />
  <track kind="metadata" src="keyStage3.vtt" srclang="en" label="Key Stage 3" />
  <!-- Fallback -->
  …
</video>
```

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-track-element]](https://html.spec.whatwg.org/multipage/media.html#the-track-element)

  --------------------------------------------------------------------------------------------------

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

`track`

23

12

31

10

12.1

6

4.4Doesn\'t work for fullscreen video.

25Doesn\'t work for fullscreen video.

31

12.1

6

1.5Doesn\'t work for fullscreen video.

`default`

23

12

31

10

12.1

6

4.4

25

31

12.1

6

1.5

`kind`

23

12

31

10

12.1

6

4.4

25

31

14

6

1.5

`label`

23

12

31

10

12.1

6

4.4

25

31

14

6

1.5

`src`

23

12

31

10

12.1

6

4.4

25

31

14

6

1.5

`srclang`

23

12

31

10

12.1

6

4.4

25

31

14

6

1.5

See also
--------

- [WebVTT text track
    format](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
- [`HTMLMediaElement.textTracks`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/textTracks)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track>>
