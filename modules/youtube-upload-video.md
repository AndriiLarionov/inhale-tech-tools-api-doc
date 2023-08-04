---
description: Upload video to YouTube channel
---

# 📹 YouTube: Upload Video

The module uses Google OAuth 2.0 connection to get access token and pass it with [other parameters](youtube-upload-video.md#mappable-parameters) to request to upload a video using YouTube Data V3 API.

{% hint style="warning" %}
**Note:** Video will be uploaded to the root channel of your Google account.&#x20;
{% endhint %}

Once uploading started, unique temporary _video uploading ID_ is created, which is sent in [response ](youtube-upload-video.md#interface)with _status_ field (generally equals "in process") in **5** seconds delay.

You can check video uploading status using the [YouTube: Get Video status](youtube-get-video-status.md) module.

The delay is defined in purpose to reduce speed of small videos processing to let Make.com easily handle requests.

After video processing finished (does not matter if video processed successfully or failed with error) server sends updates status request GET request to webhook URL if it is provided.

{% hint style="info" %}
**Note:** _video uploading ID_ will be deleted after **10** mins if the video was successfully transferred to YouTube.
{% endhint %}

### Mappable parameters

<details>

<summary>Video file URL</summary>

Is a URL of video file, which will be uploaded to YouTube.&#x20;

**Pay attention** URL must lead to the file itself, not an html page, which contains the video.



Name: **videoUrl**

Type: **text**

Required: **true**

</details>

<details>

<summary><strong>Webhook URL</strong></summary>

Used as a callback URL. Server will send GET request to that URL after video uploaded.



Name: **videoUrl**

Type: **text**

Required: **true**

</details>

<details>

<summary>Title</summary>

Video title.



Name: **videoUrl**

Type: **text**

Required: **true**

</details>

<details>

<summary>Description</summary>

Vide description.



Name: **description**

Type: **text**

Required: **false**

</details>

<details>

<summary>Tags</summary>

...



Name: **videoUrl**

Type: **text**

Required: **true**

</details>

<details>

<summary>Playlist ID</summary>

...



Name: **videoUrl**

Type: **text**

Required: **false**

</details>

### Interface / Response body

<details>

<summary>Video uploading ID</summary>

...



Name: **uploadingID**

Type: **text**

</details>

<details>

<summary>Status</summary>

Video uploading status.



Name: **status**

Type: **text**

</details>

