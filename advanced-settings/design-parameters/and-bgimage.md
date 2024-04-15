---
description: Can be used to set the default image avatar, when using &style=0 or &style=6
---

# \&bgimage

General Option! ([`&push`](../../source-settings/push.md), [`&room`](../../general-settings/room.md), [`&view`](../view-parameters/view.md), [`&scene`](../view-parameters/scene.md), [`&solo`](../mixer-scene-parameters/and-solo.md))

## Aliases

* `&bgimg`
* `&avatarimg`

## Options

Example: `&bgimage=https%3A%2F%2Fvdo.ninja%2Fmedia%2Fold_icon.png`

<table><thead><tr><th width="371">Value</th><th>Description</th></tr></thead><tbody><tr><td>(Encoded URL)</td><td>URL or base64 data image/svg</td></tr></tbody></table>

## Details

`&bgimage` can be used to set the default image avatar, when using [`&style=0`](style.md) or [`&style=6`](style.md). This only impacts what the person with the parameter added sees and must be either a URL or a base64 data image/svg. URL-encoded values.

[`https://vdo.ninja/?push=aSmexM6&style=0&vd=0&webcam&bgimage=https%3A%2F%2Fvdo.ninja%2Fmedia%2Fold_icon.png`](https://vdo.ninja/?push=aSmexM6\&style=0\&vd=0\&webcam\&bgimage=https%3A%2F%2Fvdo.ninja%2Fmedia%2Fold\_icon.png)

![](<../../.gitbook/assets/image (11) (1) (4).png>)

You can encode your URL here:\
[https://www.urlencoder.org/](https://www.urlencoder.org/)

If you want to change the background image / avatar on the sender's side for all viewers, use [`&avatar`](../video-parameters/and-avatar.md).

## `&bgimage2` and `&bgimage3`

`&bgimage2` and `&bgimage3` work in conjunction with the existing `&bgimage` parameter. You pass an URL-encoded image URL to each, and when a guest speaks, it will switch their background image between the 3 possible images, based on their loudness.

eg:

```
vdo.ninja/alpha/?view=stream2,stream2&avatarimg=./media/avatar1.png&avatarimg2=./media/avatar2.png&avatarimg3=./media/avatar3.png
```

I've included some hand-drawn avatar sample images to test with; they are the default values for `&bgimage`, `&bgimage2`, and `&bgimage3`.

The images will only show when there is no active video and is essentially the same as using [`&meterstyle=4`](meterstyle.md) with some custom CSS to specify the behaviour, but it is not stream ID specific however.

## Related

{% content-ref url="style.md" %}
[style.md](style.md)
{% endcontent-ref %}

{% content-ref url="../video-parameters/and-avatar.md" %}
[and-avatar.md](../video-parameters/and-avatar.md)
{% endcontent-ref %}

{% content-ref url="../newly-added-parameters/and-waitimage.md" %}
[and-waitimage.md](../newly-added-parameters/and-waitimage.md)
{% endcontent-ref %}

{% content-ref url="and-background.md" %}
[and-background.md](and-background.md)
{% endcontent-ref %}