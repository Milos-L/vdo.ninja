# How do I control bitrate/quality?

The bitrate controls are accessible via a URL parameter, along with width/height. Something like [https://VDO.Ninja/?view=yyyyy\&bitrate=10000 ](https://vdo.ninja/?view=yyyyy\&bitrate=10000)will let the viewer request different bitrates. The value is in kilobits per second and the default bitrate is 2500.

Read more here: [`&videobitrate`](../advanced-settings/view-parameters/bitrate.md), [`&audiobitrate`](../advanced-settings/view-parameters/audiobitrate.md) , [`&width`](../source-settings/and-width.md), [`&height`](../source-settings/and-height.md), [`&quality`](../source-settings/quality.md)``

The viewer sets the bitrates generally, although you can set maximum allowed bitrates as the publisher of a stream. See the advanced settings in the wiki for more help here.

Bitrate controls work best in Chromium-based browsers. Firefox and Safari have limited support.

You can improve audio quality in the same way, by increasing the [`&audiobitrate`](../advanced-settings/view-parameters/audiobitrate.md), but you can get better results by just disabling noise and echo cancellation instead.