---
description: Sets the "desired target" bitrate in kbps
---

# \&videobitrate

Viewer-Side Option! ([`&view`](view.md), [`&scene`](scene.md), [`&room`](../../general-settings/room.md))

## Aliases

* `&bitrate`
* `&vb`

## Options

| Value           | Description     |
| --------------- | --------------- |
| (integer value) | bitrate in kbps |

## Details

{% hint style="info" %}
Default value will target around around **2500** to **4000**.
{% endhint %}

The maximum achievable bitrate is around 60,000-kbps (60mbps)

**Lowering** the bitrate can sometimes **reduce CPU load**, **bandwidth**, and **stuttering** issues

You might want to increase the bitrate for game streams, to ensure smooth frame rates.

{% hint style="danger" %}
Not compatible with **Firefox**.
{% endhint %}

## Related

{% content-ref url="audiobitrate.md" %}
[audiobitrate.md](audiobitrate.md)
{% endcontent-ref %}