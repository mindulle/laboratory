\<video\>: The Video Embed element
==================================

The `<video>` [HTML](../index) element embeds a media player which
supports video playback into the document. You can use `<video>` for
audio content as well, but the [`<audio>`](audio) element may provide a
more appropriate user experience.

Try it
------

The above example shows simple usage of the `<video>` element. In a
similar manner to the [`<img>`](img) element, we include a path to the
media we want to display inside the `src` attribute; we can include
other attributes to specify information such as video width and height,
whether we want it to autoplay and loop, whether we want to show the
browser\'s default video controls, etc.

The content inside the opening and closing `<video></video>` tags is
shown as a fallback in browsers that don\'t support the element.

Attributes
----------

Like all other HTML elements, this element supports the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`autoplay`](#autoplay)

:   A Boolean attribute; if specified, the video automatically begins to
    play back as soon as it can do so without stopping to finish loading
    the data.

    **Note:** Sites that automatically play audio (or videos with an
    audio track) can be an unpleasant experience for users, so should be
    avoided when possible. If you must offer autoplay functionality, you
    should make it opt-in (requiring a user to specifically enable it).
    However, this can be useful when creating media elements whose
    source will be set at a later time, under user control. See our
    [autoplay
    guide](https://developer.mozilla.org/en-US/docs/Web/Media/Autoplay_guide)
    for additional information about how to properly use autoplay.
    

    To disable video autoplay, `autoplay="false"` will not work; the
    video will autoplay if the attribute is there in the `<video>` tag
    at all. To remove autoplay, the attribute needs to be removed
    altogether.

    In some browsers (e.g. Chrome 70.0) autoplay doesn\'t work if no
    `muted` attribute is present.

[`controls`](#controls)

:   If this attribute is present, the browser will offer controls to
    allow the user to control video playback, including volume, seeking,
    and pause/resume playback.

[`controlslist`](#controlslist) [Experimental]

:   The
    [`controlslist`](https://wicg.github.io/controls-list/explainer.html)
    attribute, when specified, helps the browser select what controls to
    show for the `video` element whenever the browser shows its own set
    of controls (that is, when the `controls` attribute is specified).

    The allowed values are `nodownload`, `nofullscreen` and
    `noremoteplayback`.

    Use the [`disablepictureinpicture`](#disablepictureinpicture)
    attribute if you want to disable the Picture-In-Picture mode (and
    the control).

[`crossorigin`](#crossorigin)

:   This
    [enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
    attribute indicates whether to use CORS to fetch the related video.
    [CORS-enabled resources](../cors_enabled_image) can be reused in the
    [`<canvas>`](canvas) element without being *tainted*. The allowed
    values are:

    [`anonymous`](#anonymous)

    :   Sends a cross-origin request without a credential. In other
        words, it sends the `Origin:` HTTP header without a cookie,
        X.509 certificate, or performing HTTP Basic authentication. If
        the server does not give credentials to the origin site (by not
        setting the `Access-Control-Allow-Origin:` HTTP header), the
        resource will be *tainted*, and its usage restricted.

    [`use-credentials`](#use-credentials)

    :   Sends a cross-origin request with a credential. In other words,
        it sends the `Origin:` HTTP header with a cookie, a certificate,
        or performing HTTP Basic authentication. If the server does not
        give credentials to the origin site (through
        `Access-Control-Allow-Credentials:` HTTP header), the resource
        will be *tainted* and its usage restricted.

    When not present, the resource is fetched without a CORS request
    (i.e. without sending the `Origin:` HTTP header), preventing its
    non-tainted use in [`<canvas>`](canvas) elements. If invalid, it is
    handled as if the enumerated keyword `anonymous` was used. See [CORS
    settings attributes](../attributes/crossorigin) for additional
    information.

[`disablepictureinpicture`](#disablepictureinpicture) [Experimental]

:   Prevents the browser from suggesting a Picture-in-Picture context
    menu or to request Picture-in-Picture automatically in some cases.

[`disableremoteplayback`](#disableremoteplayback) [Experimental]

:   A Boolean attribute used to disable the capability of remote
    playback in devices that are attached using wired (HDMI, DVI, etc.)
    and wireless technologies (Miracast, Chromecast, DLNA, AirPlay,
    etc.).

    In Safari, you can use
    [`x-webkit-airplay="deny"`](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/AirPlayGuide/OptingInorOutofAirPlay/OptingInorOutofAirPlay.html)
    as a fallback.

[`height`](#height)

:   The height of the video\'s display area, in [CSS
    pixels](https://drafts.csswg.org/css-values/#px) (absolute values
    only; [no
    percentages](https://html.spec.whatwg.org/multipage/embedded-content.html#dimension-attributes)).

[`loop`](#loop)

:   A Boolean attribute; if specified, the browser will automatically
    seek back to the start upon reaching the end of the video.

[`muted`](#muted)

:   A Boolean attribute that indicates the default setting of the audio
    contained in the video. If set, the audio will be initially
    silenced. Its default value is `false`, meaning that the audio will
    be played when the video is played.

[`playsinline`](#playsinline)

:   A Boolean attribute indicating that the video is to be played
    \"inline\", that is within the element\'s playback area. Note that
    the absence of this attribute *does not* imply that the video will
    always be played in fullscreen.

[`poster`](#poster)

:   A URL for an image to be shown while the video is downloading. If
    this attribute isn\'t specified, nothing is displayed until the
    first frame is available, then the first frame is shown as the
    poster frame.

[`preload`](#preload)

:   This enumerated attribute is intended to provide a hint to the
    browser about what the author thinks will lead to the best user
    experience regarding what content is loaded before the video is
    played. It may have one of the following values:

    -   `none`: Indicates that the video should not be preloaded.
    -   `metadata`: Indicates that only video metadata (e.g. length) is
        fetched.
    -   `auto`: Indicates that the whole video file can be downloaded,
        even if the user is not expected to use it.
    -   *empty string*: Synonym of the `auto` value.

    The default value is different for each browser. The spec advises it
    to be set to `metadata`.

     
    **Note:**

    -   The `autoplay` attribute has precedence over `preload`. If
        `autoplay` is specified, the browser would obviously need to
        start downloading the video for playback.
    -   The specification does not force the browser to follow the value
        of this attribute; it is a mere hint.

[`src`](#src)

:   The URL of the video to embed. This is optional; you may instead use
    the [`<source>`](source) element within the video block to specify
    the video to embed.

[`width`](#width)

:   The width of the video\'s display area, in [CSS
    pixels](https://drafts.csswg.org/css-values/#px) (absolute values
    only; [no
    percentages](https://html.spec.whatwg.org/multipage/embedded-content.html#dimension-attributes)).

Events
------

  Event Name                                                                                                                                 Fired When
  ------------------------------------------------------------------------------------------------------------------------------------------ ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [`audioprocess`](https://developer.mozilla.org/en-US/docs/Web/API/ScriptProcessorNode/audioprocess_event) [Deprecated]   The input buffer of a [`ScriptProcessorNode`](https://developer.mozilla.org/en-US/docs/Web/API/ScriptProcessorNode) is ready to be processed.
  [`canplay`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/canplay_event)                                               The browser can play the media, but estimates that not enough data has been loaded to play the media up to its end without having to stop for further buffering of content.
  [`canplaythrough`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/canplaythrough_event)                                 The browser estimates it can play the media up to its end without stopping for content buffering.
  [`complete`](https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext/complete_event)                                          The rendering of an [`OfflineAudioContext`](https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext) is terminated.
  [`durationchange`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/durationchange_event)                                 The `duration` attribute has been updated.
  [`emptied`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/emptied_event)                                               The media has become empty; for example, this event is sent if the media has already been loaded (or partially loaded), and the [`load()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/load) method is called to reload it.
  [`ended`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/ended_event)                                                   Playback has stopped because the end of the media was reached.
  [`error`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/error_event)                                                   An error occurred while fetching the media data, or the type of the resource is not a supported media format.
  [`loadeddata`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/loadeddata_event)                                         The first frame of the media has finished loading.
  [`loadedmetadata`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/loadedmetadata_event)                                 The metadata has been loaded.
  [`loadstart`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/loadstart_event)                                           Fired when the browser has started to load the resource.
  [`pause`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/pause_event)                                                   Playback has been paused.
  [`play`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/play_event)                                                     Playback has begun.
  [`playing`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/playing_event)                                              Playback is ready to start after having been paused or delayed due to lack of data.
  [`progress`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/progress_event)                                             Fired periodically as the browser loads a resource.
  [`ratechange`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/ratechange_event)                                         The playback rate has changed.
  [`seeked`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/seeked_event)                                                 A *seek* operation completed.
  [`seeking`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/seeking_event)                                               A *seek* operation began.
  [`stalled`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/stalled_event)                                               The user agent is trying to fetch media data, but data is unexpectedly not forthcoming.
  [`suspend`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/suspend_event)                                               Media data loading has been suspended.
  [`timeupdate`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/timeupdate_event)                                         The time indicated by the `currentTime` attribute has been updated.
  [`volumechange`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/volumechange_event)                                     The volume has changed.
  [`waiting`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/waiting_event)                                               Playback has stopped because of a temporary lack of data.

Usage notes
-----------

Browsers don\'t all support the same video formats; you can provide
multiple sources inside nested [`<source>`](source) elements, and the
browser will then use the first one it understands.

[html]

```html
<video controls>
  <source src="myVideo.webm" type="video/webm" />
  <source src="myVideo.mp4" type="video/mp4" />
  <p>
    Your browser doesn't support HTML video. Here is a
    <a href="myVideo.mp4">link to the video</a> instead.
  </p>
</video>
```

We offer a substantive and thorough [guide to media file
types](https://developer.mozilla.org/en-US/docs/Web/Media/Formats) and
the [guide to the codecs supported for
video](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Video_codecs).
Also available is a guide to [audio codecs that can be used with
them](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Audio_codecs).

Other usage notes:

- If you don\'t specify the `controls` attribute, the video won\'t
    include the browser\'s default controls; you can create your own
    custom controls using JavaScript and the
    [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)
    API. See [Creating a cross-browser video
    player](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery/cross_browser_video_player)
    for more details.
- To allow precise control over your video (and audio) content,
    `HTMLMediaElement`s fire many different
    [events](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement#events).
    In addition to providing controllability, these events let you
    monitor the progress of both download and playback of the media, as
    well as the playback state and position.
- You can use the
    [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position)
    property to adjust the positioning of the video within the
    element\'s frame, and the
    [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)
    property to control how the video\'s size is adjusted to fit within
    the frame.
- To show subtitles/captions along with your video, you can use some
    JavaScript along with the [`<track>`](track) element and the
    [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
    format. See [Adding captions and subtitles to HTML
    video](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery/Adding_captions_and_subtitles_to_HTML5_video)
    for more information.
- You can play audio files using a `<video>` element. This can be
    useful if, for example, you need to perform audio with a
    [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
    transcript, since the [`<audio>`](audio) element doesn\'t allow
    captions using WebVTT.
- To test the fallback content on browsers that support the element,
    you can replace `<video>` with a non-existing element like
    `<notavideo>`.

A good general source of information on using HTML `<video>` is the
[Video and audio
content](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content)
beginner\'s tutorial.

### Styling with CSS

The `<video>` element is a replaced element --- its
[`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
value is `inline` by default, but its default width and height in the
viewport is defined by the video being embedded.

There are no special considerations for styling `<video>`; a common
strategy is to give it a `display` value of `block` to make it easier to
position, size, etc., and then provide styling and layout information as
required. [Video player styling
basics](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery/Video_player_styling_basics)
provides some useful styling techniques.

### Detecting track addition and removal

You can detect when tracks are added to and removed from a `<video>`
element using the
[`addtrack`](https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList/addtrack_event)
and
[`removetrack`](https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList/removetrack_event)
events. However, these events aren\'t sent directly to the `<video>`
element itself. Instead, they\'re sent to the track list object within
the `<video>` element\'s
[`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)
that corresponds to the type of track that was added to the element:

[`HTMLMediaElement.audioTracks`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/audioTracks)

:   An
    [`AudioTrackList`](https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList)
    containing all of the media element\'s audio tracks. You can add a
    listener for `addtrack` to this object to be alerted when new audio
    tracks are added to the element.

[`HTMLMediaElement.videoTracks`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/videoTracks)

:   Add an `addtrack` listener to this
    [`VideoTrackList`](https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList)
    object to be informed when video tracks are added to the element.

[`HTMLMediaElement.textTracks`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/textTracks)

:   Add an `addtrack` event listener to this
    [`TextTrackList`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList)
    to be notified when new text tracks are added to the element.

For example, to detect when audio tracks are added to or removed from a
`<video>` element, you can use code like this:

[js]

```js
const elem = document.querySelector("video");

elem.audioTracks.onaddtrack = (event) => {
  trackEditor.addTrack(event.track);
};

elem.audioTracks.onremovetrack = (event) => {
  trackEditor.removeTrack(event.track);
};
```

This code watches for audio tracks to be added to and removed from the
element, and calls a hypothetical function on a track editor to register
and remove the track from the editor\'s list of available tracks.

You can also use
[`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
to listen for the
[`addtrack`](https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList/addtrack_event)
and
[`removetrack`](https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList/removetrack_event)
events.

### Server support for video

If the MIME type for the video is not set correctly on the server, the
video may not show or show a gray box containing an X (if JavaScript is
enabled).

If you use Apache Web Server to serve Ogg Theora videos, you can fix
this problem by adding the video file type extensions to \"video/ogg\"
MIME type. The most common video file type extensions are \".ogm\",
\".ogv\", or \".ogg\". To do this, edit the \"mime.types\" file in
\"/etc/apache\" or use the `"AddType"` configuration directive in
`httpd.conf`.

```text
AddType video/ogg .ogm
AddType video/ogg .ogv
AddType video/ogg .ogg
```

If you serve your videos as WebM, you can fix this problem for the
Apache Web Server by adding the extension used by your video files
(\".webm\" is the most common one) to the MIME type \"video/webm\" via
the \"mime.types\" file in \"/etc/apache\" or via the \"AddType\"
configuration directive in `httpd.conf`.

```text
AddType video/webm .webm
```

Your web host may provide an easy interface to MIME type configuration
changes for new technologies until a global update naturally occurs.

Examples
--------

### Single source

This example plays a video when activated, providing the user with the
browser\'s default video controls to control playback.

#### HTML

[html]

```html
<!-- Simple video example -->
<!-- 'Big Buck Bunny' licensed under CC 3.0 by the Blender foundation. Hosted by archive.org -->
<!-- Poster from peach.blender.org -->
<video
  controls
  src="https://archive.org/download/BigBuckBunny_124/Content/big_buck_bunny_720p_surround.mp4"
  poster="https://peach.blender.org/wp-content/uploads/title_anouncement.jpg?x11217"
  width="620">
  Sorry, your browser doesn't support embedded videos, but don't worry, you can
  <a href="https://archive.org/details/BigBuckBunny_124">download it</a>
  and watch it with your favorite video player!
</video>
```

#### Result

Until the video starts playing, the image provided in the `poster`
attribute is displayed in its place. If the browser doesn\'t support
video playback, the fallback text is displayed.

### Multiple sources

This example builds on the last one, offering three different sources
for the media; this allows the video to be watched regardless of which
video codecs are supported by the browser.

#### HTML

[html]

```html
<!-- Using multiple sources as fallbacks for a video tag -->
<!-- 'Elephants Dream' by Orange Open Movie Project Studio, licensed under CC-3.0, hosted by archive.org -->
<!-- Poster hosted by Wikimedia -->
<video
  width="620"
  controls
  poster="https://upload.wikimedia.org/wikipedia/commons/e/e8/Elephants_Dream_s5_both.jpg">
  <source
    src="https://archive.org/download/ElephantsDream/ed_hd.ogv"
    type="video/ogg" />
  <source
    src="https://archive.org/download/ElephantsDream/ed_hd.avi"
    type="video/avi" />
  <source
    src="https://archive.org/download/ElephantsDream/ed_1024_512kb.mp4"
    type="video/mp4" />

  Sorry, your browser doesn't support embedded videos, but don't worry, you can
  <a href="https://archive.org/download/ElephantsDream/ed_1024_512kb.mp4">
    download the MP4
  </a>
  and watch it with your favorite video player!
</video>
```

#### Result

First
[Ogg](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Containers#ogg)
is tried. If that can\'t be played, then AVI is tried. Finally,
[MP4](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Containers#mpeg-4_mp4)
is tried. A fallback message is displayed if the video element isn\'t
supported, but not if all sources fail.

Some media file types let you provide more specific information using
the
[`codecs`](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/codecs_parameter)
parameter as part of the file\'s type string. A relatively simple
example is `video/webm; codecs="vp8, vorbis"`, which says that the file
is a
[WebM](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Containers#webm)
video using
[VP8](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Video_codecs#vp8)
for its video and
[Vorbis](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Audio_codecs#vorbis)
for audio.

Accessibility concerns
----------------------

Videos should provide both captions and transcripts that accurately
describe its content (see [Adding captions and subtitles to HTML
video](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery/Adding_captions_and_subtitles_to_HTML5_video)
for more information on how to implement these). Captions allow people
who are experiencing hearing loss to understand a video\'s audio content
as the video is being played, while transcripts allow people who need
additional time to be able to review audio content at a pace and format
that is comfortable for them.

It\'s worth noting that while you can caption audio-only media, you can
only do so when playing audio in a [`<video>`](video) element, since the
video region of the element is used to present the captions. This is one
of the special scenarios in which it\'s useful to play audio in a video
element.

If automatic captioning services are used, it is important to review the
generated content to ensure it accurately represents the source video.

In addition to spoken dialog, subtitles and transcripts should also
identify music and sound effects that communicate important information.
This includes emotion and tone:

```text
14
00:03:14 --> 00:03:18
[Dramatic rock music]

15
00:03:19 --> 00:03:21
[whispering] What's that off in the distance?

16
00:03:22 --> 00:03:24
It's… it's a…

16 00:03:25 --> 00:03:32
[Loud thumping]
[Dishes clattering]
```

Captions should not obstruct the main subject of the video. They can be
positioned using [the `align` VTT cue
setting](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API#cue_settings).

- [Web Video Text Tracks Format
    (WebVTT)](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
- [WebAIM: Captions, Transcripts, and Audio
    Descriptions](https://webaim.org/techniques/captions/)
- [MDN Understanding WCAG, Guideline 1.2
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.2_%E2%80%94_providing_text_alternatives_for_time-based_media)
- [Understanding Success Criterion 1.2.1 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv-av-only-alt.html)
- [Understanding Success Criterion 1.2.2 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv-captions.html)

Technical summary
-----------------

+-----------------------------------+-----------------------------------+
| [Content                          | [Flow                             |
| c                                 | content](../                      |
| ategories](../content_categories) | content_categories#flow_content), |
|                                   | phrasing content, embedded        |
|                                   | content. If it has a              |
|                                   | [`controls`](video#controls)      |
|                                   | attribute: interactive content    |
|                                   | and palpable content.             |
+-----------------------------------+-----------------------------------+
| Permitted content                 | If the element has a              |
|                                   | [`src`](video#src) attribute:     |
|                                   | zero or more [`<track>`](track)   |
|                                   | elements, followed by transparent |
|                                   | content that contains no media    |
|                                   | elements--that is no              |
|                                   | [`<audio>`](audio) or             |
|                                   | [`<video>`](video).               |
|                                   |                                   |
|                                   | Else: zero or more                |
|                                   | [`<source>`](source) elements,    |
|                                   | followed by zero or more          |
|                                   | [`<track>`](track) elements,      |
|                                   | followed by transparent content   |
|                                   | that contains no media            |
|                                   | elements--that is no              |
|                                   | [`<audio>`](audio) or             |
|                                   | [`<video>`](video).               |
+-----------------------------------+-----------------------------------+
| Tag omission                      | None, both the starting and       |
|                                   | ending tag are mandatory.         |
+-----------------------------------+-----------------------------------+
| Permitted parents                 | Any element that accepts embedded |
|                                   | content.                          |
+-----------------------------------+-----------------------------------+
| Implicit ARIA role                | [No corresponding                 |
|                                   | role](https://www.w3.org/TR/html>>  |
|                                   | -aria/#dfn-no-corresponding-role) |
+-----------------------------------+-----------------------------------+
| Permitted ARIA roles              | [`ap                              |
|                                   | plication`](https://developer.moz>> |
|                                   | illa.org/en-US/docs/Web/Accessibi |
|                                   | lity/ARIA/Roles/application_role) |
+-----------------------------------+-----------------------------------+
| DOM interface                     | [`HTMLVideoElement`](             |
|                                   | https://developer.mozilla.org/en->> |
|                                   | US/docs/Web/API/HTMLVideoElement) |
+-----------------------------------+-----------------------------------+

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-video-element]](https://html.spec.whatwg.org/multipage/media.html#the-video-element)

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

`video`

3

12

3.5

9

10.5

3.1

4.4

18

4

14

3

1.0

`aspect_ratio_computed_from_attributes`

79

79

71

No

66

14

79

79

79

57

14

12.0

`autoplay`

3

12

3.5

9

10.5

3.1

4.4

18

4

14

10Only available for videos that have [no sound or have the audio track
disabled](https://developer.apple.com/library/content/releasenotes/General/WhatsNewInSafari/Articles/Safari_10_0.html).

1.0

`controls`

3

12

3.5

9

10.5

3.1

4.4

18

4

14

3

1.0

`crossorigin`

33

≤18

74

12--74With `crossorigin="use-credentials"`, cookies aren\'t sent during
seek. See [bug 1532722](https://bugzil.la/1532722).

No

20

10

4.4.3

33

79

14--79With `crossorigin="use-credentials"`, cookies aren\'t sent during
seek. See [bug 1532722](https://bugzil.la/1532722).

20

10

2.0

`height`

3

12

3.5

9

10.5

3.1

4.4

18

4

14

3

1.0

`loop`

3

12

11

9

10.5

3.1

4.4

18

14

14

6

1.0

`muted`

30

12

11

10

Yes

5

4.4

30

14

18

No

2.0

`poster`

3

12

3.6

9

10.5

3.1

4.4

18

4

14

3

1.0

`preload`

3Defaults to `metadata` in Chrome 64.

12

4

9

YesDefaults to `metadata` in Opera 51.

3.1

YesDefaults to `metadata` in Chrome 64.

YesDefaults to `metadata` in Chrome 64.

4

YesDefaults to `metadata` in Opera 51.

3

YesDefaults to `metadata` in Samsung Internet 9.0.

`src`

3

12

3.5

9

10.5

3.1

4.4

18

4

14

3

1.0

`width`

3

12

3.5

9

10.5

3.1

4.4

18

4

14

3

1.0

See also
--------

- [Guide to media types and formats on the
    web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats)
  - [Media container formats (file
        types)](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Containers)
  - [Web video codec
        guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Video_codecs)
  - [Web audio codec
        guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Audio_codecs)
- Positioning and sizing the picture within its frame:
    [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position)
    and
    [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)
- [`<audio>`](audio)
- [Using HTML audio and
    video](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content)
- [Manipulating video using
    canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Manipulating_video_using_canvas)
- [Configuring servers for Ogg
    media](https://developer.mozilla.org/en-US/docs/Web/HTTP/Configuring_servers_for_Ogg_media)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video>>
