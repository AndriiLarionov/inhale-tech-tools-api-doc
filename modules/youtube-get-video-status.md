---
description: Returns video status by video uploading ID
---

# ✅ YouTube: Get Video status

### Parameters

<details>

<summary>Uploading ID</summary>

You can get video uploading ID from [YouTube: Upload Video](youtube-upload-video.md) module.

Name: **uploadingId**\
Type: **text**\
Required: **true**

</details>

### Interface / Response body

<details>

<summary>Status</summary>

Video uploading status. Contains of these values: "in process" / "error" / "processed".

Name: **status**\
Type: **text**

</details>

### Errors

<table><thead><tr><th width="143">Status Code</th><th>Reasons</th></tr></thead><tbody><tr><td>404</td><td><ul><li>Such uploading ID does not exist.</li><li>Uploading ID has been deleted as <strong>10</strong> min after video uploading passed.</li></ul></td></tr></tbody></table>
