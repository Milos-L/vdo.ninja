---
description: Record functionality for guests
---

# \&record

Sender-Side Option! ([`&push`](../../source-settings/push.md))

## Options

Example: `&record=1000`

<table><thead><tr><th width="195">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>0</code></td><td>No video recorded; audio tentatively recorded as 32bit PCM lossless</td></tr><tr><td>(negative integer)</td><td>No video recorded; audio recorded as {integer} kbps OPUS file. Eg: -120 - Audio only at 120 kbps</td></tr><tr><td>(positive integer)</td><td>Recorded video bitrate in kbps</td></tr><tr><td><code>false</code> | <code>off</code></td><td>Will disable the user from being able to record a video. Buttons for recording are hidden/deleted and the recording function is disabled when used; so the director won't even be able to trigger it remotely</td></tr></tbody></table>

## Details

### Recorded file properties

**`File format`**` ``- WebM.` &#x20;

**`File Codec:`**` ``H264 or VP8 for video; OPUS or PCM for audio.` &#x20;

Usually up to the browser.

Default bitrate will record at around 4000 kbps, but it will still prompt still for value if not set.

The Director of a room will be notified if a user is recording and they can start/stop the recording.\
The Director of a room can trigger the record function remotely, even if the \&record parameter has not been added.

The video/audio will be saved in real-time to the guest's local download folder.

Do not force-close the browser or turn off the computer while it is recording; you may lose the file or have a partial capture.

The recording should stop automatically when the guest hangs-ups manually. I try my best to do the same when the browser is closed, but it's best to still purposefully stop recording first.

It will automatically capture with stereo audio and echo cancellation off, if available.

You can use [https://isolated.vdo.ninja/convert](https://isolated.vdo.ninja/convert) to convert from WebM file formats to OPUS or WAV file formats, **without transcoding and without downloads**. [More about converting from WebM to MP4 or WAV here](and-record.md#converting-and-playing-back-webm).

### Recording as the director

When recording as the director, the button and option to record each guest is available by default. It's hidden behind Advanced controls. You have the option to record locally, to your own disk, or record remotely, directly to the remote guest's local storage.

When recording to the guest's local storage, quality should be near pristine, given as its not being sent via the Internet first. Recording locally, the video may have dynamic resolutions and varying quality, due to the low latency transmission. ([`&chunked`](../../newly-added-parameters/and-chunked.md)-mode excepted)

Anyone can also access the recording options via right-clicking a video. This option is available as of VDO.Ninja [v22](../../releases/v22.md).

![](<../../.gitbook/assets/image (102) (1) (1).png>)![](<../../.gitbook/assets/image (101) (1).png>)

### Bitrate Thresholds

| Threshold      | Inbound Audio | Recorded audio |
| -------------- | ------------- | -------------- |
| 4000           | 128 kpbs      | 128 kpbs       |
| 2500           | 80 kbps       | 128 kpbs       |
| Less than 2500 | 32 kbps       | 32 kbps        |

### When using [`&chunked`](../../newly-added-parameters/and-chunked.md) mode

When the sender of a stream is using the `&chunked` mode, recording their video will save the inbound video directly to disk without transcoding. Not needing to transcode the saved video in the browser is only possible with the `&chunked` mode. Of course, you also don't have the option to increase the bitrate or change codecs when using this mode; at least not as the viewer.

The chunked mode (as of June 2022) is still a maturing feature. Please report any issues and provide feedback.

### Converting and playing back WebM

WebM is a universal container of sorts when used within a Chromium browser, but it doesn't always work well for VLC or popular video editors. FFmpeg can be used to convert to other formats though, including MP4 and WAV, typically without transcoding.

To make converting from WebM to other formats easier, a version of FFmpeg is hosted within VDO.Ninja for this. It can be located here at [https://vdo.ninja/convert](https://vdo.ninja/convert), with several of the most common conversion options ready to go, such as WebM-PCM to WAV-PCM.

Due to memory limits and other browser limitations, this FFmpeg tool can only process files under about 2-gigabytes in size. For larger files, you may need to download and use a desktop version of [FFmpeg](https://ffmpeg.org/download.html) instead.

FFmpeg command lines are provided if you choose to run FFmpeg yourself locally, but if that is still to complicated, you can grab [Handbrake ](https://handbrake.fr/)for free; it's a GUI-based option that is fairly accessible.

Lastly, sometimes a video recorded by VDO.Ninja will have a variable resolution or/and frame rate, which can cause problems with some video editors. For example, the quality might be stuck low, or it might freeze after a few seconds. In these cases, you may need to transcode the video to a fixed resolution and frame rate using FFmpeg (or Handbrake) first, before using.. Transcoding is very slow in the browser, so I'd recommend you download Handbrake or FFmpeg for this task.

{% embed url="https://vdo.ninja/convert" %}
FFmpeg in the browser; up to 4-gb file sizes
{% endembed %}

### Please note:

{% hint style="info" %}
When recording with PCM, ([`&pcm`](and-pcm.md)) the inbound audio bitrate will be at 256-kbps. (regardless of video bitrate)
{% endhint %}

{% hint style="warning" %}
* If recording with an Nvidia/AMD graphics card installed on your computer, ensure your drivers are up to date or try recording with VP8-codec instead. Hardware-encoding might reduce CPU load, but it can also result in discolored video if the driver is buggy.
* Safari browsers and iOS devices may struggle with media recording.
* Enabling Safari's _MediaRecorder_ under E_xperimental webKit Features_ may be needed. As well, users may be asked to download a file once the recording ends, for the webM media file to be saved correctly to disk.
{% endhint %}

## Related

{% content-ref url="and-recordcodec.md" %}
[and-recordcodec.md](and-recordcodec.md)
{% endcontent-ref %}

{% content-ref url="and-autorecord.md" %}
[and-autorecord.md](and-autorecord.md)
{% endcontent-ref %}

{% content-ref url="and-pcm.md" %}
[and-pcm.md](and-pcm.md)
{% endcontent-ref %}