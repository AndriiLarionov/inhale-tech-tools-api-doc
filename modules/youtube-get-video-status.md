---
description: Returns video status by video uploading ID
---

# ✅ YouTube: Get Video status

## Parameters

**Uploading ID**

You can get video uploading ID from [YouTube: Upload Video](youtube-upload-video.md) module.

{% code overflow="wrap" %}
```javascript
{
    Name: "uploadingId"
    Type: "text"
    Required: true
}
```
{% endcode %}

## Interface / Response body

**Status**

Video uploading status. Could contain one of these values: "in process" / "error" / "processed".

{% code overflow="wrap" %}
```javascript
{
    Name: "status"
    Type: "text"
}
```
{% endcode %}

## Errors

<table><thead><tr><th width="143">Status Code</th><th>Reasons</th></tr></thead><tbody><tr><td>404</td><td><ul><li>Such uploading ID does not exist.</li><li>Uploading ID has been deleted as <strong>10</strong> min after video uploading passed.</li></ul></td></tr></tbody></table>
