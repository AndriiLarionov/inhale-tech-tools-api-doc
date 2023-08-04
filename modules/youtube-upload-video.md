---
description: Upload video to YouTube channel
---

# 📹 YouTube: Upload Video

The module requires Google OAuth 2.0 connection to get access token and pass it with [other parameters](youtube-upload-video.md#mappable-parameters) to upload a video using YouTube Data V3 API.

{% hint style="info" %}
**Note:** Video will be uploaded to the root channel of Google account, which you used to create OAuth 2.0 connection with.
{% endhint %}

Once uploading started, unique temporary _video uploading ID_ is created, which is sent in [response ](youtube-upload-video.md#interface)with _status_ field (generally equals "in process") in **5** seconds delay.

You can check video uploading status using the [YouTube: Get Video status](youtube-get-video-status.md) module.

The delay is defined in purpose to reduce speed of small videos processing to let Make.com easily handle requests.

If _webhook URL_ is provided, server sends GET request to _webhook URL_ with _youtubeLink_ attached to the params of the URL once video processing finished.

{% hint style="info" %}
**Note:** _video uploading ID_ will be deleted after **10** mins if the video was successfully transferred to YouTube.
{% endhint %}

### Parameters

<details>

<summary>Video file URL</summary>

Is a URL of video file, which will be uploaded to YouTube. **Pay attention** URL must lead to the file itself, not an html page, which contains the video.

Name: **videoUrl**\
Type: **text**\
Required: **true**

</details>

<details>

<summary><strong>Webhook URL</strong></summary>

Used as a callback URL. Server will send GET request to that URL after video processing finished.

Name: **webhookUrl**\
Type: **text**\
Required: **false**

</details>

<details>

<summary>Title</summary>

Video title.

Name: **title**\
Type: **text**\
Required: **true**

</details>

<details>

<summary>Description</summary>

Vide description.

Name: **description**\
Type: **text**\
Required: **false**

</details>

<details>

<summary>Tags</summary>

Tags must be a string containing tags separated with comma. Example: "tag1,tag2,tag3"

Name: **tags**\
Type: **text**\
Required: **false**

</details>

<details>

<summary>Playlist ID</summary>

To get playlist ID go to YouTube Studio and take the ID from URL: https://studio.youtube.com/playlist/**\<PLAYLIST\_ID>**/videos

Name: **playlistId**\
Type: **text**\
Required: **false**

</details>

### Interface / Response body

<details>

<summary>Video uploading ID</summary>

...

Name: **uploadingID**\
Type: **text**

</details>

<details>

<summary>Status</summary>

Video uploading status. Could contain one of these values: "in process" / "error" / "processed".

Name: **status**\
Type: **text**

</details>

### Errors

<table><thead><tr><th width="143">Status Code</th><th>Reasons</th></tr></thead><tbody><tr><td>400</td><td><ul><li>Validation error (title).</li><li>User exceeded max videos per day.</li><li>YouTube channel restrictions.</li></ul></td></tr><tr><td>403</td><td><ul><li>Google OAuth 2.0 client exceeded daily quota limit for uploading videos.</li></ul></td></tr><tr><td>500</td><td><ul><li>Internal Server error.</li></ul></td></tr></tbody></table>
